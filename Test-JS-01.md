# Entrance exam for mentor

## JSB
### Kiến thức về HTML
1. viết code html để liên kết file js & css từ page.html & index.html cấu trúc thư mục sau.
Cây thư mục của các file hiện tại   
```txt
project
├── assets
│   ├── css
│   │   ├── index.css
│   │   └── page.css
│   ├── js
│   │   ├── index.js
│   │   └── page.js
│   └── page.html
└── html
    └── index.html
```
---


2. Hãy nêu sự khác biệt giữa `<textarea>` & `<input>` elements


---

3. Làm một combobox như hình

<img src="Source/entrance-2.gif" height=200>


---

### Kiến thức về CSS 

1. Liệt kê 5 CSS pseudo class/element

---

2. Hãy nêu sự khác nhau của hệ màu RGBA so với RGB

---

3. Sử dụng thuộc tính CSS phù hợp khiến một hình ảnh (vuông) trở thành hình tròn.

```html
<div class="rounded">
</div>
```

```css
div{
    width: 500px;
    height: 500px;
    background-color:yellow;
}
```

---


8. Viết file css để căn giữa element div trong trường hợp sau

<img src="Source/entrance-4.png" height=200>

```html
<div class="container border">
    <div class="square border"></div>
</div>
```

```css
.border{
    border:1px solid red;
}
.container{
    width: 300px;
    height: 300px;
}
.square{
    width: 50px;
    height: 50px;
}
```
---

10. Chỉ sử dụng CSS, hãy di chuyển vị trí các ô trở nên sang như hình mẫu với cấu trúc HTML/CSS cho sẵn

<img src="Source/entrance-3.png" height=200>

```html
<div class="container border">
    <div class="rectangle red"></div>
    <div class="square green"></div>
    <div class="square green"></div>
    <div class="square yellow"></div>
    <div class="square yellow"></div>
    <div class="rectangle blue"></div>
</div>
```

```css
.red{
    background-color: red;
}
.yellow{
    background-color: yellow;
}
.green{
    background-color: green;
}
.blue{
    background-color: blue;
}
.container {
    position: relative;
    left: 0;
    top: 0;
    width: 600px;
    height: 600px;
}
.square{
    width: 200px;
    height: 200px;
}
.rectangle{
    width: 300px;
    height: 100px;
}
```

---

### Kiến thức về Javascript

1. Trả lời kết quả được in ra màn hình ở console của đoạn code sau? Giải thích dòng thứ 4. Làm sao để kiểm tra giá trị một biến có kiểu dữ liệu là Array

```js
let a = {};
let b = "";
let c = 0;
let d = [];
console.log(typeof a)
console.log(typeof b)
console.log(typeof c)
console.log(typeof d)
```

<details>
<summary>Đáp án</summary>

```
object
string
number
object
```

Giải thích. Array kế thừa từ object nên về cơ bản array cũng là object. typeof chỉ kiểm tra các kiểu dữ liệu nguyên thuỷ (primitives) (và một số khác). Còn lại thì sẽ trả về object (kể cả instance của một class nếu sử dụng typeof).
Sử dụng static method `Array.isArray()` 

</details>

---

2. Đoạn code sau in ra màn hình kết quả gì? Giải thích.
```js
let a = {
    b:{
        name:'Son',
        role:'ta'
    },
    c:{
        name:'Quang',
        role:'mentor'
    }
}
let b = a.b;
let c = a.c;
delete a
delete a.b
delete a.c
console.log(a)
console.log(b)
console.log(c)
```

<details>
<summary>Đáp án</summary>

```js
{}
{name: "Son", role: "ta"}
{name: "Quang", role: "mentor"}
```

Object là reference type nên khi khai báo, ta thực chất đang tạo một reference tới một vùng nhớ lưu giá trị. Điều này cũng đúng đối với việc khai báo key của property, nếu value là một obect thì sẽ cũng tạo reference. Sử dụng `delete` chỉ xoá reference tới ô nhớ đó chứ không phải giải phóng vùng nhớ. Khi gán b,c thực chất chúng ta đã lưu reference tới của object và lưu vào biến b,c.

</details>

---

3. Có bao nhiêu cách viết vòng lặp for? Nêu cấu trúc phù hợp với các loại vòng lặp?

<details>
<summary>Đáp án</summary>

Có 3 loại vòng lặp for: vòng lặp `for` cổ điển gồm 3 thành phần lặp n lần, vòng lặp `for in` và vòng lặp `for of`
```js
for(let i =0 ;i<5;i++){
    console.log(i)
}
let array = [1,2,3,4]
for (let element of array){
    console.log(element)
}
let obj = {
    name:'Mindx',
    company:'Illiat'
}
for(let key in obj){
    console.log(obj[key])
}
```

</details>

---

4. Sự khác nhau giữa break & continue

<details>
<summary>Đáp án</summary>

`break` kết thúc vòng lặp gần nhất, continue kết thúc lần lặp hiện tại, bắt đầu lần lặp mới. 

</details>

---

5. khác sự khác nhau giữa sự kiện input & change của text?

<details>
<summary>Đáp án</summary>
Khi sự kiện blur (mất focus) được kích hoạt, đồng thời xem xét giá trị của ô input có thay đổi hay không? Nếu có thì sự kiện change mới được trigger, nếu không thì sự kiện change không được kích hoạt. Input được kích hoạt khi sự kiện focus đang xảy ra (đang nhập liệu), kích hoạt mỗi khi người dùng nhấn phím bất kỳ.
</details>

---

6. Kết quả của đoạn code là gì? Giải thích
```js
function f (){
        let b = 9
        return ++b < 10 ? b : 'Yah'
    }
    let a = f()
    console.log(a)
```

<details>
<summary>Đáp án</summary>

```js
Yah
```
Lí do bởi vì toán tử ++ là toán tử tăng, và được đặt bên trái (pre-increment) nên biến b được tăng lên 1 (10). Khi so sánh bé hơn thì kết quả là false nên kết quả là 'Yah'

</details>

---

7. Đề xuất giải pháp thay thế cấu trúc if else sau đây để khiến code trở nên gọn gàng.
Chữ La Mã hàng đơn vị. Sửa đổi hàm `roman_unit`

```js
function roman_unit(decimal_number) {
        let decimal = parseInt(decimal_number)
        let roman_number = ""
        if (decimal_number == 1) {
            roman_number = "I"

        } else if (decimal_number == 2) {
            roman_number = "II"

        } else if (decimal_number == 3) {
            roman_number = "III"

        } else if (decimal_number == 4) {
            roman_number = "IV"

        } else if (decimal_number == 5) {
            roman_number = "V"

        } else if (decimal_number == 6) {
            roman_number = "VI"

        } else if (decimal_number == 7) {
            roman_number = "VII"

        } else if (decimal_number == 8) {
            roman_number = "VIII"

        } else if (decimal_number == 9) {
            roman_number = "IX"

        } else if (decimal_number == 10) {
            roman_number = "X"

        } else {
            roman_number = "?"
        }
        return roman_number
    }
    let result = roman_unit(9)
```

<details>
<summary>Đáp án</summary>

Sử dụng switch case hoặc object để chuyển đổi

</details>

---

8. Giải thích phương thức `element.insertAdjacentHTML()`. Viết một hàm 10 nút tương ứng, đi kèm với eventListener là in ra màn hình giá trị của nút đó (được cung cấp trong mảng) và chèn vào trong element có id là `container`.
```js
let animals = ['cat','rabbit','dog','fox','fish','racoon','tiger','bear','parrot','snake']
```

<details>
<summary>Đáp án</summary>

```js
let animals = ['cat','rabbit','dog','fox','fish','racoon','tiger','bear','parrot','snake']
function createButton(inner){
    return `
    <button>${inner}</button>
    `
}
let cont = document.getElementById("container")
cont.insertAdjacentHTML("beforeend",animals.map(createButton).join(""))
let btns = document.querySelectorAll("button")
btns.forEach(btn => {
    btn.addEventListener("click",(e)=>{
        console.log(e.target.innerHTML)
    })
})
```
</details>

---

9. Chỉnh sửa đoạn code sau trở lại cho chính xác. Giải thích 

```js
function bmi_calculator(weight_in_kg, height_in_cm) {
    let bmi = weight_in_kg / height_in_cm /height_in_cm * 10000  ;
    bmi = parseFloat(bmi.toFixed(2))
    let status = ""
    switch (true) {
        case 0 < bmi < 18.5:
            status = "Underweight"
            break
        case 18.5 < bmi < 25:
            status = "Normal"

            break
        case 25 < bmi < 30:
            status = "Overweight"

            break
        case bmi < 30:
            status = "Obese"

            break
        default:
            status = '?'
    }
    return {
        bmi:bmi,
        status:status
    }

}
let result = bmi_calculator(65, 170)
console.log(result)
// {bmi: 22.49, status: "Underweight"}
```

<details>
<summary>Đáp án</summary>
Thay đổi điều kiện sử dụng dấu &&. vd (0 < bmi && bmi < 18.5)
</details>

---

10. một element có thể có tối đa bao nhiêu listener cho 1 event cố định. Làm sao xoá listener (unsubscribe) khỏi 1 event? Cho ví dụ cụ thể.

<details>
<summary>Đáp án</summary>

Một element có thể có nhiều listener cho 1 event cố định. Thứ tự invoke lần lượt đúng như thứ tự khi subscribe event đó. Lưu ý rằng nếu các listener là async thì vẫn tuân theo quy tắc xử lý bất đồng bộ. 
Để xoá một eventListener cần phải lưu trữ lại reference tới function, và sử dụng hàm `removeEventListener`

```js
let btn = document.getElementById("btn")
let a = async () => {
    console.log("first")
}
btn.addEventListener("click", a)

btn.addEventListener("click",()=>{
    btn.removeEventListener("click",a)
    console.log("second")
})
```

</details>

---

## JSA
### Kiến thức git & github
1. Giải thích các lệnh cơ bản của git 

- git init
- git add
- git remote 
- git log
- git status
- git push
- git pull
- git fetch

---

2. Tạo một repository ở local machine (máy tính cá nhân) và lưu trữ source code lên remote repository ở github.

<details>
<summary>Đáp án</summary>

```sh
git init
git add .
git commit -m "inital commit"
git remote add origin [link]
git push --set-upstream origin/master
```
3. Tạo một commit. Quay lui HEAD về 2 commit trước đó.
```sh
git add .
git commit -m "[message]"
```
```sh
git reset --hard HEAD~~
```
4. Thêm/xoá/nhảy sang branch. Merge branch. Giải quyết conflict
```sh
git checkout -b [branch-name]
```
```sh
git branch -d [branch-name]
```
```sh
git add .
git commit -m "[message]"
git checkout [branch-name]
```
```sh
git add .
git commit -m "up-to-date"
git checkout master 
git merge [branch-name]
```
Nếu có xuất hiện conflict thì giải quyết conflict bằng cách xoá đi những thay đổi cũ, sau đó tạo một merge commit (như commit bình thường)

</details>

---

### Kiến thức về Javascript 

1. localStorage là gì? Các kiểu dữ liệu mà localStorage có thể lưu trữ? Làm sao lữu trữ dữ liệu dạng array/object?

<details>
<summary>Đáp án</summary>

`localStorage`  một property read-only của global giúp giúp ta truy cập tới Storage Object của bất kỳ document nhằm mục đích lưu trữ dữ liệu ở client vô thời hạn.`localStorage` lưu trữ dữ liệu `primitives`. Muốn lưu trữ các `Object`/`Array` trong javascript thì phải parse sang dạng `JSON`

</details>

---

2. Event Loops của Javascript là gì? Tại sao Javascript chạy được nhiều tác vụ bất đồng bộ khác nhau cùng 1 lúc (promise)?

<details>
<summary>Đáp án</summary>

[Event Loop](https://www.youtube.com/watch?v=8aGhZQkoFbQ) là một vòng lặp vô tận trong Javascript Runtime dùng để lắng nghe các Event (khi các event được trigger).

</details>

---

3. Viết một regular expression có thể match được email. Ví dụ 

```txt
Letters to the Editor (Your complete mailing address is required):
letters@thehindu.co.in
Readers' Editor:
readerseditor@thehindu.co.in
Advertisements Queries (Print):
inetads@thehindu.co.in
Advertisements Queries (Online):
digital@thehindu.co.in
Advertisements Queries (International):
international@thehindu.co.in
Subscription Queries:
subs@thehindu.co.in
Comments on the website:
web.thehindu@thehindu.co.in
```
```txt
digital@thehindu.co.in;
inetads@thehindu.co.in;
international@thehindu.co.in;
letters@thehindu.co.in;
readerseditor@thehindu.co.in;
subs@thehindu.co.in;
web.thehindu@thehindu.co.in;
```

<details>
<summary>Đáp án</summary>

```js
const regex = /[a-zA-Z0-0.]+@[a-zA-Z0-0.]+/gm;
const str = `Letters to the Editor (Your complete mailing address is required):
letters@thehindu.co.in
Readers' Editor:
readerseditor@thehindu.co.in
Advertisements Queries (Print):
inetads@thehindu.co.in
Advertisements Queries (Online):
digital@thehindu.co.in
Advertisements Queries (International):
international@thehindu.co.in
Subscription Queries:
subs@thehindu.co.in
Comments on the website:
web.thehindu@thehindu.co.in`;
let m;

while ((m = regex.exec(str)) !== null) {
    // This is necessary to avoid infinite loops with zero-width matches
    if (m.index === regex.lastIndex) {
        regex.lastIndex++;
    }
    
    // The result can be accessed through the `m`-variable.
    m.forEach((match, groupIndex) => {
        console.log(`Found match, group ${groupIndex}: ${match}`);
    });
}
```

</details>

---

4. Cho đoạn code như sau. Kết quả khi tương tác với form là gì? Giải thích tại sao lại như vậy?. Đề xuất ít nhất 2 cách giải quyết trường hợp trên.

<details>
<summary>Đáp án</summary>

```html
<p id="help">Helpful notes will appear here</p>
<p>E-mail: <input type="text" id="email" name="email"></p>
<p>Name: <input type="text" id="name" name="name"></p>
<p>Age: <input type="text" id="age" name="age"></p>
```
```js
function showHelp(help) {
  document.getElementById('help').textContent = help;
}

function setupHelp() {
  var helpText = [
      {'id': 'email', 'help': 'Your e-mail address'},
      {'id': 'name', 'help': 'Your full name'},
      {'id': 'age', 'help': 'Your age (you must be over 16)'}
    ];

  for (var i = 0; i < helpText.length; i++) {
    var item = helpText[i];
    document.getElementById(item.id).onfocus = function() {
      showHelp(item.help);
    }
  }
}

setupHelp();
```

</details>

---

5. Implement lại hàm map/reduce/filter method của mảng thành hàm myMap/myReduce/myFilter.

<details>
<summary>Đáp án</summary>

```js
// Ít nhất làm đúng logic cơ bản là thế này
Array.prototype.myMap = function (callback) {
        let t = []
        for (let e of this){
            t.push(callback(e))
        }
        return t
    }
Array.prototype.myFilter = function (callback) {
    let t = []
    for (let e of this){
        if (callback(e)){
            t.push(e)
        }
    }
    return t
}
Array.prototype.myReduce = function (callback,accumulator) {
        let acc = accumulator || 0
        let t = []
        for (let e of this){
            acc = callback(acc,e)     
        }
        return acc
    }
```

</details>

---

6. Hãy cho biết kết quả đoạn code sau và giải thích.
```js
function resolveAfter2Seconds() {
  console.log("starting slow promise")
  return new Promise(resolve => {
    setTimeout(function() {
      resolve("slow")
      console.log("slow promise is done")
    }, 2000)
  })
}

function resolveAfter1Second() {
  console.log("starting fast promise")
  return new Promise(resolve => {
    setTimeout(function() {
      resolve("fast")
      console.log("fast promise is done")
    }, 1000)
  })
}

async function sequentialStart() {
  console.log('==SEQUENTIAL START==')
  const slow = await resolveAfter2Seconds()
  console.log(slow) 
  const fast = await resolveAfter1Second()
  console.log(fast) 
}

async function concurrentStart() {
  console.log('==CONCURRENT START with await==');
  const slow = resolveAfter2Seconds() 
  const fast = resolveAfter1Second() 
  console.log(await slow) 
  console.log(await fast) 
}

function concurrentPromise() {
  console.log('==CONCURRENT START with Promise.all==')
  return Promise.all([resolveAfter2Seconds(), resolveAfter1Second()]).then((messages) => {
    console.log(messages[0]) 
    console.log(messages[1])
}

async function parallel() {
  console.log('==PARALLEL with await Promise.all==')
  await Promise.all([
      (async()=>console.log(await resolveAfter2Seconds()))(),
      (async()=>console.log(await resolveAfter1Second()))()
  ])
}

sequentialStart()
setTimeout(concurrentStart, 4000)
setTimeout(concurrentPromise, 7000)
setTimeout(parallel, 10000) 
```

<details>
<summary>Đáp án</summary> 

"==SEQUENTIAL START=="   
"starting slow promise"  
"slow promise is done"  
"slow"  
"starting fast promise"  
"fast promise is done"  
"fast"  
"==CONCURRENT START with await=="  
"starting slow promise"  
"starting fast promise"  
"fast promise is done"  
"slow promise is done"  
"slow"  
"fast"  
"==CONCURRENT START with Promise.all=="  
"starting slow promise"  
"starting fast promise"  
"fast promise is done"  
"slow promise is done"  
"slow"  
"fast"  
"==PARALLEL with await Promise.all=="  
"starting slow promise"   
"starting fast promise"   
"fast promise is done"  
"fast"   
"slow promise is done"  
"slow"  

</details>

---

Từ câu tiếp theo trở đi sẽ sử dụng chung source code như sau. Đoạn code trên có thể chọn ngẫu nhiên 10 pokemon.
```js
const domain = 'https://pokeapi.co/api/v2'
const endpoint = 'pokemon'

async function getPokemonNames(pokemonID) {
    const start_time = new Date().valueOf()
    const pokemonName = [];
    for (let i = 0; i < pokemonID.length; i++) {
        pokemonName.push(await getPokemon( `${domain}/${endpoint}/${pokemonID[i]}`))
    }
    return pokemonName
}

function main(){
    const pokemonId = []
    for (let i = 0; i < 10; i++) {
        pokemonId.push(Math.floor(Math.random() * 600))
    }
    console.time('Operation')
    getPokemonNames(pokemonId)
    .then(pokemons => {
        console.log(pokemons)
        console.timeLog("Operation")
    })
}
async function getPokemon(url) {
    // 
}
main()
```

7. Viết hàm `getPokemon` để chương trình chạy đúng, lấy dữ liệu thông endoints bằng `fetch()`, sau đó trả về mảng gồm tên của từng 
Pokemon. Viết bằng 2 cách (async - await & promise).

<details>
<summary>Đáp án</summary> 

```js
function getPokemon(url) {
    return fetch(url)
        .then(response => response.json())
        .then(pokemon => {
            return pokemon.name
        })
}
async function getPokemon(url) {
    const response = await fetch(url)
    const pokemon = await response.json()
    const name = pokemon.name
    return name
}
```

</details>

---

8. Đoạn code ở trên có thời gian thực thi ước tính trên trình duyệt Brave (nhân Chrome) là khoảng 3500ms (Có thể sai số bởi vì tốc độ mạng, server,...). Có cách nào giảm thời gian thực thi xuống không? Nếu có thì hãy trình bày giải pháp và giải thích.

<details>
<summary>Đáp án</summary> 

Cập nhật hàm getPokemonNames sử dụng Promise.all. Promise all sẽ bắt đầu tất cả các project tại cùng 1 thời điểm => thời gian hoàn thành bằng thời gian dài nhất của các request. Đoạn code cũ, ta đợi từng request hoàn và tiếp tục gửi request => thời gian hoàn thành bằng tổng thời gian hoàn thành của request

```js
async function getPokemonNames(pokemonID) {
    const start_time = new Date().valueOf()
    const pokes = Promise.all(
        pokemonID.map(id=>{
            return getPokemon(`${domain}/${endpoint}/${id}`)
        })
    )
    return await pokes
}
```

</details>

---

9. Cập nhật hàm ở` main` để có thể kết thúc hàm công việc đang chạy (lấy dữ liệu) nếu thời gian chạy quá chậm  (> 2000ms)
Hàm main có thể dùng được viết lại như sau.

<details>
<summary>Đáp án</summary> 

```js
function main(){
    return new Promise((resolve,reject)=>{
        const pokemonId = []
        for (let i = 0; i < 10; i++) {
            pokemonId.push(Math.floor(Math.random() * 600))
        }
        console.time('Operation')
        getPokemonNames(pokemonId)
        .then(pokemons => {
            console.timeLog("Operation")
            resolve(pokemons)
        })
        setTimeout(()=>{
            reject(new Error("Too long"))
        },1000)
    })
    
}
```

</details>

---

## JSI
- DB / NoSQl / Firebase
1. Điểm yếu của noSQL? Firestore? 
2. onSnapshot?
3. querySnapshot?
- Authentication / Authorization / SMS / Email confirm / Firestore
2. Tìm hiểu về việc authentication
- Cloud functions
1. Viết một cloud function cho phép upload ảnh bằng lưu trữ bằng cloud storage. Kết quả trả về là public url của ảnh có thể truy cập ở mọi nơi. Viết bằng html/css/js
- dp. Trình bày ít nhất 3 cách viết hàm tính số fibonacci thứ n.
