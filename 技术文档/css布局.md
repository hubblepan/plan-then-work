### 2. 常见css

#### 2.1 文本单行显示

```
.single-text{
	overflow: hidden;
	text-overflow:ellipsis;
	white-space: nowrap;
}
```

#### 2.2 css 选择器

- `xxx`
- `xxxaaa`       具有 xxx 和 aaa 的元素
- `xxx aaa`     xxx元素的aaa后代元素 (后代)
- `xxx, aaa`   xxx元素 和 aaa元素
- `xxx>aaa`     xxx元素的aaa子元素（父子）
- `xxx+aaa`     xxx元素的首个aaa子元素
- `xxx~aaa`     父元素为 xxx 的所有子元素aaa
- `[ccc]`         具有属性ccc的元素
- `[ccc=value]`  属性 ccc=value 的元素
- `:active, :default, :disabled, :empty, :enabled, :hover, :focus， :link`
- `xxx:first-child, xxx:last-child, xxx:nth-child(n)`
- `<a>`标签选择器

### 3. 常见问题

#### 3.1 flex布局时， 子元素文本内容设置了单行属性， 但仍然超出父元素。

解决办法， 设置 子元素的 `width: 0`

#### 3.2 将行内元素设置为 `inline-block`时， 似乎会有一个边框

xxxxx

#### 3.3 scroll 相关

- 设置 scroll滚动

  ```
  #content {
  	overflow-y: auto;
  	overflow-x: hidden;
  }
  ```

  



