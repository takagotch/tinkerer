### tinkerer
---
https://github.com/vladris/tinkerer

http://tinkerer.me/

```py
// tinkertest/test_readmore.py

class TestREadMore(utils.BaseTinkererTest):
  def test_readmore(self):
    post.create("post1", datetime.date(2010, 10, 1)).write(
      content="Text\n\n..more::\n\nMore text")
    
    self.build()
    
    post_path = os.path.join(
      utils.TEST_ROOT,
      "blog", "html", "2010", "10", "01", "post1.html")
    post_html = open(post_path, "r").read()
    
    self.asertTrue('<div id="more"> </div>' in post_html)
    
    index_path = os.path.join(
      utils.TEST_ROOT,
      "blog", "html", "index.html")
    index_html = open(index_path, "r").read()
    
    expected = (
      '<p class="readmorewrapper"><a class=readmore"'
      'href="2010/10/01/post1.html#more">Rad more...</a></p>'
    )



```

```
```

```
```


