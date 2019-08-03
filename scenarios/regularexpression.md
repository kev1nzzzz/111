# **高级教程**

## **正则表达式**

正则表达式（有时缩写为regexp，regex或re）是用于匹配文本中的模式的工具。在Python中，我们有re模块。正则表达式的应用程序是广泛的，但它们相当复杂，因此在考虑使用正则表达式执行某项任务时，请考虑替代方案，并作为最后的手段来使用正则表达式。

一个示例正则表达式是r"^(From|To|Cc).*?python-list@python.org"

解释：插入符号^匹配行开头的文本。(From|To|Cc)表示该行必须以|分隔。这称为OR运算符，如果该行以组中的任何单词开头，则正则表达式将匹配。

因此，以下行将与该正则表达式匹配： From: python-list@python.org To: !asp]<,. python-list@python.org

作为“正确的”匹配正则表达式的示例（如练习中的正则表达式），请参阅此内容：

原代码：

```r
# Example: 
import re
pattern = re.compile(r"\[(on|off)\]") # Slight optimization
print(re.search(pattern, "Mono: Playback 65 [75%] [-16.50dB] [on]"))
# Returns a Match object!
print(re.search(pattern, "Nada...:-("))
# Doesn't return anything.
# End Example

# Exercise: make a regular expression that will match an email
def test_email(your_pattern):
    pattern = re.compile(your_pattern)
    emails = ["john@example.com", "python-list@python.org", "wha.t.`1an?ug{}ly@email.com"]
    for email in emails:
        if not re.match(pattern, email):
            print("You failed to match %s" % (email))
        elif not your_pattern:
            print("Forgot to enter a pattern!")
        else:
            print("Pass")
pattern = r"" # Your pattern here!
test_email(pattern)
```

正确的匹配正则表达式示例：

```r
# Exercise: make a regular expression that will match an email
import re
def test_email(your_pattern):
    pattern = re.compile(your_pattern)
    emails = ["john@example.com", "python-list@python.org", "wha.t.`1an?ug{}ly@email.com"]
    for email in emails:
        if not re.match(pattern, email):
            print("You failed to match %s" % (email))
        elif not your_pattern:
            print("Forgot to enter a pattern!")
        else:
            print("Pass")
# Your pattern here!
pattern = r"\"?([-a-zA-Z0-9.`?{}]+@\w+\.\w+)\"?"
test_email(pattern)
```

输出结果：

```r
<script.py> output:
    Pass
    Pass
    Pass
```
