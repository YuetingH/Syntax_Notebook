<div align='center'><b><font size='5'> 
Markdown Syntax 
</font></b></div>

[TOC]

### **1. Title**

#### **A. Format of Centered Headline [HTML]**
- Set Centered Headline 
  &#x2002; `<div align='center'> Headline </div>`
- Set Font Size 
  &#x2002; `<font size='5'> Headline </font>`
- Set Title in Bold 
  &#x2002; `<b> Headline </b>`
  
- <font color="#87CEFA"> Quick Reference：</font>
  ```
     <div align='center'><b><font size='5'> Healine </font></b></div> 
  ```

#### **B. Level of Title** 
  - Level 1 Title  &#x2002; `# Title`     
  - Level 2 Title  &#x2002; `## Title`
  - Level 3 Title  &#x2002; `### Title` 
  - Level 4 Title  &#x2002; `#### Title` 
  - Level 5 Title  &#x2002; `##### Title` 
  - Level 6 Title  &#x2002; `###### Title`
  

### **2. Paragraph**

#### **A. List**
  
- Unordered List &#x2001; All methods work &#x2002; `- xxx` &#x2002; `+ xxx` &#x2002; `* xxx`

- Ordered List &#x2002; `1. xxx`  &#x2002; `2. xxx` 

- Nested List
  &#x2001; Use Tab to create blank space for nested list
  ```
  1. xxx  
    - xxx
    - xxx
  2. xxx 
  ```

#### **B. Horizontal Rules** &#x2001; 
  Either method works  &#x2002; `---`  &#x2002; `***` 

#### **C. Space**

- One-Space &#x2001; `&#xA0;` 
  
- Two-Space &#x2001; `&#x2002;`

- Four-Space &#x2001; `&#x2003;`

- Thin-Space &#x2001; `&#x2009;`

### **3. Text**  
#### **A. Plain Text**
 
- Type it as usual without any code. 
   
- Notice that every newline requires a blank line before it.

- If you want to type some punctuation which involves markdown syntax, simply add \ before the punctuation. That is, the escape character is \

#### **B. Special Character**

Check https://cn.bing.com/images/search?view=detailV2&ccid=gtfKjIkp&id=1715CB583BD421A086EC24C5821B0FAD6217E0D4&thid=OIP.gtfKjIkpjhxIrzG7lY0M7wHaFa&mediaurl=https%3A%2F%2Fimg-blog.csdn.net%2F20160920153340935&exph=439&expw=601&q=markdown+greek+alphabet&simid=607991249823556770&form=IRPRST&ck=2E4D840A409B234B04A7BA4535B326CF&selectedindex=3&qpvt=markdown+greek+alphabet&ajaxhist=0&ajaxserp=0&vt=0&sim=11&cdnurl=https%3A%2F%2Ftse1-mm.cn.bing.net%2Fth%2Fid%2FR-C.82d7ca8c89298e1c48af31bb958d0cef%3Frik%3D1OAXYq0PG4LFJA%26pid%3DImgRaw  


#### **C. Font [HTML]**

- Font Type
  
  - Papyrus：&#x2002; `<font face="Papyrus">Hello World</font>`
      
    &#x2003; &#x2003; &#x2003; &#x2003; <font face="Papyrus">Hello World</font>

  - Consolas: &#x2002; `<font face="Consolas">Hello World</font>`
  
    &#x2003; &#x2003; &#x2003; &#x2003; <font face="Consolas">Hello World</font>

  - Times New Roman: &#x2002; `<font face="Times New Roman">Hello World</font>`
  
    &#x2003; &#x2003; &#x2003; &#x2003; &#x2003;&#x2003; &#x2003; &#x2003; <font face="Times New Roman">Hello World</font>

  - Verdana: &#x2002; `<font face="Verdana">Hello World</font>`
  
    &#x2003; &#x2003; &#x2003; &#x2003; <font face="Verdana">Hello World</font>

  - Comic sans MS: &#x2002; `<font face="Comic sans MS">Hello World</font>`
  
    &#x2003; &#x2003; &#x2003; &#x2003; &#x2003; &#x2003; &#x2003; <font face="Comic sans MS">Hello World</font>

- Font Size

    `<font size=2 >Hello World</font>`

- Font Colour

  - Blue: &#x2002; `<font color=#87CEFA >Hello World</font>`

    &#x2003; &#x2003; &#x2002;  <font color=#87CEFA >Hello World</font>

  - Orange: &#x2002; `<font color=#FFA042 >Hello World</font>`

    &#x2003; &#x2003; &#x2003; &#x2003;<font color=#FFA042 >Hello World</font>

  - Green: &#x2002; `<font color=#82D900 >Hello World</font>`

    &#x2003; &#x2003; &#x2002; &#x2002; <font color=#82D900 >Hello World</font>

  - Red: &#x2002; `<font color=#FF0000 >Hello World</font>`

    &#x2003; &#x2003; &#x2002; <font color=#FF0000 >Hello World</font>

  - Yellow: &#x2002; `<font color=#F9F900 >Hello World</font>`

    &#x2003; &#x2003; &#x2003; &#x2002;<font color=#F9F900 >Hello World</font>

- Font Background Colour

  - Blue: &#x2002; `<table><tr><td bgcolor=#87CEFA>Hello World</td></tr></table>`
      
    <table><tr><td bgcolor=#87CEFA>Hello World</td></tr></table>

  - Orange: &#x2002; `<table><tr><td bgcolor=#FFA042>Hello World</td></tr></table>`
      
    <table><tr><td bgcolor=#FFA042>Hello World</td></tr></table>

  - Green: &#x2002; `<table><tr><td bgcolor=#82D900>Hello World</td></tr></table>`
      
    <table><tr><td bgcolor=#82D900>Hello World</td></tr></table>

  - Red: &#x2002; `<table><tr><td bgcolor=#FF0000>Hello World</td></tr></table>`
      
    <table><tr><td bgcolor=#FF0000>Hello World</td></tr></table>

  - Yellow: &#x2002; `<table><tr><td bgcolor=#F9F900>Hello World</td></tr></table>`
      
    <table><tr><td bgcolor=#F9F900>Hello World</td></tr></table>
    

#### **D. Common Format of Character**
  
  Notice that blank space is not allowed in this section.
  - In bold: &#x2001; Either method works &#x2002; `**Hello World**`  &#x2002; `__Hello World__`

     &#x2003; &#x2003; &#x2003; &#x2003;**Hello World**

  - Italic: &#x2001; Either method works &#x2002; `*Hello World*` &#x2002; `_Hello World_`

     &#x2003; &#x2003; &#x2003; *Hello World*
  
  - In bold & Italic: &#x2001; Either method works &#x2002; `***Hello World***` &#x2002; `___Hello World___`

     &#x2003; &#x2003; &#x2003; &#x2003; &#x2003; &#x2003; &#x2002;***Hello World***

  - Strickout: &#x2001; `~~Hello World~~`

    &#x2003; &#x2003; &#x2003; &#x2003; &#x2002; ~~Hello World~~
  
  - Underline [HTML]: &#x2001; `<u>Hello World</u>`

    &#x2003; &#x2003; &#x2003; &#x2003; &#x2003; &#x2003; &#x2003; &#x2002; <u>Hello World</u>



### **4. Insert**
#### **A. Quotation**
  
- Quotation: &#x2001; `>xxx`
- Nested Quotation: 
  ```
  >xxx
  >>xxx
  >>>xxx
  ``` 

#### **B. Catalogue**

Add [TOC] whereever you want to insert catalogue 

#### **C. Code**
  
- Code in one line: &#x2001; \`xxx`
- Code Block: &#x2001;\```

  &#x2003; &#x2003; &#x2003; &#x2003; &#x2002; &#x2002; xxx

  &#x2003; &#x2003; &#x2003; &#x2003; &#x2002; &#x2002;\```

#### **D. Formula [Latex]**
- **Format**
  - Paragraph Fomat:
    
    - Inserted in text: &#x2001; `$ f(x) = a+b $`

    - Interline: &#x2001; `$$ f(x) = a+b $$`

  - Serial Number: &#x2001;`$$ f(x) = a - b \tag{1.1} $$`

- **Operation**
  
  - \+ \- \* \/ \= ^2 ' : &#x2001; type it as usual
  
  - $ \cdot $: &#x2001; `$ \cdot $`
  
  - $ \neq $: &#x2001; `$ \neq $`

  - $ \equiv $: &#x2001; `$ \equiv $`
  
  - $ \bmod $: &#x2001; `$ \bmod $`

  - $ \sqrt{x} $: &#x2001; `$ \sqrt{x} $`
  
    $ \sqrt[3]{x} $: &#x2001; `$ \sqrt[3]{x} $`
  
  - $ \frac{x}{m} $: &#x2001; `$ \frac{x}{m} $`
  
  - $ a_{12}^{t} $: &#x2001; `$ a_{12}^{t} $`

  - $ x''_{12} $: &#x2001; `$ x''_{12} $`

  - $ \overline{x+y} $: &#x2001; ` $ \overline{x+y} $ `

    $ \underline{x+y} $: &#x2001; `$ \underline{x+y} $`
    
  - $ \begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix} $: &#x2001; `$ \begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix} $`

    $ \begin{bmatrix} 0 & -1 \\ 1 & 0 \end{bmatrix} $: &#x2001; `$ \begin{bmatrix} 0 & -1 \\ 1 & 0 \end{bmatrix} $`

    $ \begin{vmatrix} a & b \\ c & d \end{vmatrix} $: &#x2001; `$ \begin{vmatrix} a & b \\ c & d \end{vmatrix} $`


#### **E. Table**
  ```
  | Fruit [align left]    | Price[align right]    |  Number[middle]  |
  | :------   | -----:   | :----: |
  | banana        | $1      |   5    |
  | apple        | $1      |   6    |
  | strawberry       | $1      |   7    |

  ```


  | Fruit [align left]    | Price[align right]    |  Number[middle]  |
  | :------   | -----:   | :----: |
  | banana        | $1      |   5    |
  | apple        | $1      |   6    |
  | strawberry       | $1      |   7    |

#### **F. Chart**
  - **Flow Chart**
  
    ```flow
    st=>start: Start
    op=>operation: Your Operation
    cond=>condition: Yes or No?
    e=>end
    
    st->op->cond
    cond(yes)->e
    cond(no)->op
    ```

  - **Sequence**
  
    ```sequence
    subject A->subject B: ask
    Note right of subject B: description of B
    Note left of subject A: description of A
    subject B-->subject A: respond
  
    ```



<form id="form1" name="form1" method="get" action="mailto:printfabcd@163.com">
  <label for="textfield">主题 </label> 
  <p> 
    <input type="text" name="subject" id="subject" value="dfd" /> 
</p> 
  <p> 
    <label for="textarea">内容： </label> 
    <textarea name="body" rows="8" id="body" value="ddddd"> </textarea> 
    <label for="Submit">发送 </label> 
    <input type="submit" name="Submit" value="提交" id="Submit" /> 
  </p> 
</form>


<div class="col-8 col-12-small">
								<form method="post" action="mailto:Y.Han202105@gmail.com">
									<div class="row gtr-uniform gtr-50">
										<div class="col-6 col-12-xsmall"><input type="text" name="name" id="name" placeholder="Name" /></div>
										<div class="col-6 col-12-xsmall"><input type="email" name="email" id="email" placeholder="Email" /></div>
										<div class="col-12"><textarea name="message" id="message" placeholder="Message" rows="4"></textarea></div>
									</div>
								</form>
								<ul class="actions">
									<li><input type="submit" value="Send Message" id="Submit"/></li>
								</ul>
							</div>
