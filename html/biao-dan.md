> input 背景提示

```
<input placeholder="提示文字即可">


input::-webkit-input-placeholder {
    /* placeholder颜色  */
    color: #aab2bd;
    /* placeholder字体大小  */
    font-size: 12px;
    /* placeholder位置  */
    text-align: left;
}
```

> input 显示的内容

```
<input value="显示内容">
```


> action 执行请求的提交地址 onsubmit执行提交前的 js 函数。 method 请求方法

```
<form method="post" id="bug-report-form" action="url" onsubmit="return checkInput()" method="post">
</form>
```

**如果 action 没有写的话，默认提交到当前页面的url，并且 `<input>` 标签的name值作为key, 输入值作为value。**

**onsubmit 在提交之前会执行，并且并会根据函数的返回结果来确定 submit 是否执行** 

**给表单绑定 js 方法时，必须return false 才能终止 action 的进一步执行，return null照样会继续执行。**

