现在来实现表单提交事件的相应，添加'HandleSubmit' 如下
```js
<form ref="" onSubmit={this.handleSubmit}   className="comment-form">
          <input ref={(value) => { this.textInput = value} } type="text" className="input" />
          <button type="submit" className="submit-btn" >提交</button>
        </form>
       ```

        名词注释
        submit 提交
        handle 处理
        form   表单

        handleSubmit = （e） => {
        	e.preventDefault() 

        }
由于使用了ES6 的胖箭头函数语法，所以使用中,就不需要了

 e.preventDefault() 的作用是，在表单页面中阻止跳转

 ##拿到inport的输入
 首先添加 ref 如下 ：
 ```js
 <input ref={value => this.comments = value} type="text" className="input" />
 ```

 上面， ref 的意思是'指针'。后面大括号中的内容，也就是
 ```js
 value => this.comment = value
 ```

 是一个胖箭头函数。其中 value 指代当前 input 这个节点对应的 Object。然后
 ```js
 this.comment = value 
 ```
 就是把 input 对象，赋值给一个成员变量,目的是在整个 class 之内， 可以随处访问

 这样，如果想在 handlesubmit 函数中拿到用户输入文本，就
 ```js
 handleSubmit = (e) => {
		e.preventDefault()
		console.log('this.comment.value')
	}
	```
	到这里，如何从 form 的输入框中拿到字符串，这个技巧我们就掌握了。同时这也就是一种最简单的方式，另外，还可以通过受控组件的方式来取值，那个比较麻烦我们暂时不用学。

	##修改state

	先来讨论 reder（）的本性：
	>一旦 state 变， reader（） 自动被重新执行

	## 清空 
	最后我们还需要在提交结束后 清空 input 里的字符串

	handleSubmit



