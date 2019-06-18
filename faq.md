**Q:** pip3 install

```md
ReadTimeoutError(self.\_pool, None, 'Read timed out.')
```

**A:**

1. 换源
2. 设置 `pip3` 获取第三方库的请求超时时间

```sh
pip3 install -U --timeout 1000 matplotlib
```

---

**Q:**

```md
SyntaxError: Non-ASCII character '\xe5' in file test.py on line 3, but no encoding declared; see http://python.org/dev/peps/pep-0263/ for details
```

**A:**

```py
#!/usr/bin/python
# coding=utf-8
print "你好吗"
```

OR

```py
#!/usr/bin/python
# -*- coding: utf-8 -*-
print "你好吗"
```

OR

```py
#!/usr/bin/python
# vim: set fileencoding=utf-8
print "你好吗"
```

---

**Q:**

```md
ImportError: No module named pandas
```

**A:** `pip install pandas`

---

**Q:**

```md
ModuleNotFoundError: No module named 'sklearn'
```

**A:** `pip install -U scikit-learn`
