# **基础知识学习**

## **模块和包**

### **什么是模块？**

在编程中，模块是具有特定功能的软件。
例如，在构建乒乓球游戏时，一个模块将负责游戏逻辑，另一个模块将负责在屏幕上绘制游戏。每个模块都是不同的文件，可以单独编辑。
模块让你能够有逻辑地组织你的 Python 代码段。把相关的代码分配到一个模块里能让你的代码更好用，更易懂。
模块能定义函数，类和变量，模块里也能包含可执行的代码。

### **编写模块**

Python中的模块只是扩展名为.py的Python文件。模块的名称将是文件的名称。Python模块可以定义和实现一组函数，类或变量。在上面的例子中，我们将有两个文件，我们将：

```r
mygame/
mygame/game.py
mygame/draw.py
```

Python脚本game.py将实现游戏。它将使用draw_game文件中的函数draw.py，或者换句话说，draw模块，它实现在屏幕上绘制游戏的逻辑。

使用该import命令从其他模块导入模块。在此示例中，game.py脚本可能如下所示：

```r
# game.py
# import the draw module
import draw

def play_game():
    ...

def main():
    result = play_game()
    draw.draw_game(result)

# this means that if this script is executed, then 
# main() will be executed
if __name__ == '__main__':
    main()
```

该draw模块可能如下所示：

```r
# draw.py

def draw_game():
    ...

def clear_screen(screen):
    ...
```

在此示例中，game模块导入load模块，使模块能够使用在该模块中实现的功能。该main函数将使用本地函数play_game来运行游戏，然后使用在draw模块中实现的函数绘制游戏结果draw_game。要使用该功能draw_game从draw模块，我们需要指定哪个模块的功能实现，使用点运算符。要从模块引用该draw_game函数game，我们需要导入draw模块然后才调用draw.draw_game()。

当import draw指令运行时，Python解释器将在具有.py前缀的模块的名称中查找执行脚本的目录中的文件，因此在我们的示例中它将尝试查找draw.py。如果它找到一个，它将导入它。如果没有，他将继续寻找内置模块。

您可能已经注意到，在导入模块时，会.pyc出现一个文件，这是一个已编译的Python文件。Python将文件编译为Python字节码，这样每次加载模块时都不必解析文件。如果.pyc文件存在，则会加载而不是.py文件，但此过程对用户是透明的。

### **将模块对象导入当前名称空间**

我们也可以draw_game使用该from命令将函数直接导入主脚本的命名空间。如下所示：

```r
# game.py
# import the draw module
from draw import draw_game

def main():
    result = play_game()
    draw_game(result)
```

您可能已经注意到，在此示例中，draw_game不在其导入模块的名称之前，因为我们在import命令中指定了模块名称。

使用此表示法的优点是，更容易使用当前模块中的函数，因为您不需要指定函数来自哪个模块。但是，任何命名空间都不能有两个具有完全相同名称的对象，因此该import命令可能会替换命名空间中的现有对象。

### **从模块导入所有对象**

我们也可以使用该import *命令从特定模块导入所有对象，如下所示：

```r
# game.py
# import the draw module
from draw import *

def main():
    result = play_game()
    draw_game(result)
```

这可能有点冒险，因为模块中的更改可能会影响导入它的模块，但它更短，也不需要您指定要从模块导入的对象。

### **自定义导入名称**

我们也可以用我们想要的任何名称加载模块。当我们想要有条件地导入模块以在其余代码中使用相同的名称时，这非常有用。

例如，如果您有两个draw名称略有不同的模块 - 您可以执行以下操作：

```r
# game.py
# import the draw module
if visual_mode:
    # in visual mode, we draw using graphics
    import draw_visual as draw
else:
    # in textual mode, we print out text
    import draw_textual as draw

def main():
    result = play_game()
    # this can either be visual or textual depending on visual_mode
    draw.draw_game(result)
```

### **模块初始化**

第一次将模块加载到正在运行的Python脚本中时，通过执行模块中的代码来初始化它。如果代码中的另一个模块再次导入同一个模块，它将不会被加载两次而只会加载一次 - 因此模块内的局部变量充当“单例” - 它们只被初始化一次。

这有用，因为这意味着您可以依赖此行为来初始化对象。例如：

```r
# draw.py

def draw_game():
    # when clearing the screen we can use the main screen object initialized in this module
    clear_screen(main_screen)
    ...

def clear_screen(screen):
    ...

class Screen():
    ...

# initialize main_screen as a singleton
main_screen = Screen()
```

### **扩展模块加载路径**

除了默认设置（本地目录和内置模块）之外，我们可以通过两种方式告诉Python解释器在哪里查找模块。您可以使用环境变量PYTHONPATH指定其他目录以查找模块，如下所示：

```r
PYTHONPATH=/foo python game.py
```

这将执行game.py，并将使脚本能够从foo目录和本地目录加载模块。

另一种方法是sys.path.append功能。您可以在运行import命令之前执行它：

```r
sys.path.append("/foo")
```

这会将foo目录添加到路径列表中以查找模块。

### **探索内置模块**

在此处查看 Python标准库中的内置模块的完整列表。

在Python中探索模块时，有两个非常重要的函数可以派上用场 - 函数dir和help函数。

如果我们要导入模块urllib，这使我们能够从URL创建读取数据，我们只import需要模块：

```r
# import the library
import urllib

# use it
urllib.urlopen(...)
```

我们可以使用以下dir函数查找每个模块中实现的功能：

```r
>>> import urllib
>>> dir(urllib)
['ContentTooShortError', 'FancyURLopener', 
'MAXFTPCACHE', 'URLopener', '__all__', '__builtins__', 

'__doc__', '__file__', '__name__', '__package__', 
'__version__', '_ftperrors', '_get_proxies', 
'_get_proxy_settings', '_have_ssl', '_hexdig', 
'_hextochr', '_hostprog', '_is_unicode', '_localhost', 

'_noheaders', '_nportprog', '_passwdprog', '_portprog', 
'_queryprog', '_safe_map', '_safe_quoters', 
'_tagprog', '_thishost', '_typeprog', '_urlopener', 
'_userprog', '_valueprog', 'addbase', 'addclosehook', 
'addinfo', 'addinfourl', 'always_safe', 'basejoin', 
'c', 'ftpcache', 'ftperrors', 'ftpwrapper', 
'getproxies', 
'getproxies_environment', 'getproxies_macosx_sysconf', 
'i', 'localhost', 'main', 'noheaders', 'os', 
'pathname2url', 'proxy_bypass', 
'proxy_bypass_environment', 'proxy_bypass_macosx_sysconf', 'quote', 
'quote_plus', 'reporthook', 'socket', 'splitattr', 
'splithost', 'splitnport', 'splitpasswd', 'splitport',
 
'splitquery', 'splittag', 'splittype', 'splituser', 
'splitvalue', 'ssl', 'string', 'sys', 'test', 'test1', 

'thishost', 'time', 'toBytes', 'unquote', 
'unquote_plus', 'unwrap', 'url2pathname', 'urlcleanup', 
'urlencode', 
'urlopen', 'urlretrieve']
```

当我们在我们想要使用的模块中找到函数时，我们可以help在Python解释器中使用函数更多地阅读它：

```r
help(urllib.urlopen)
```

### **写包**

包是名称空间，包含多个包和模块本身。它们只是目录，但有一点扭曲。

Python中的每个包都是一个必须包含一个名为的特殊文件的目录__init__.py。此文件可以为空，它表示它包含的目录是Python包，因此可以像导入模块一样导入它。

如果我们创建一个foo标记包名称的目录，我们就可以在该包中创建一个名为的模块bar。我们也不要忘记__init__.py在foo目录中添加文件。

要使用该模块bar，我们可以通过两种方式导入它：

```r
import foo.bar
```

另一种方式是：

```r
from foo import bar
```

在第一种方法中，foo每当我们访问模块时都必须使用前缀bar。在第二种方法中，我们不这样做，因为我们将模块导入到模块的命名空间中。

该__init__.py文件还可以通过覆盖__all__变量来决定包导出哪些模块作为API，同时保持其他模块内部，如下所示：

```r
__init__.py:

__all__ = ["bar"]
```

## **练习**

在本练习中，您将需要输出re模块中包含单词的所有函数的按字母顺序排序的列表find。

re模块：

```r
import re
```

正确代码示范：

```r
import re

# Your code goes here
find_members = []
for member in dir(re):
    if "find" in member:
        find_members.append(member)

print(sorted(find_members))
```

输出结果为：

```r
<script.py> output:
    ['findall', 'finditer']
```




