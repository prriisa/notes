# JAVASCRIPT ADV NOTES

`Document Object Model`
everything you see in your website is a part of DOM.

there are multiple types of notes in a DOM tree. these are:-

1. Element
2. Text
3. Comment
4. Document
5. Attribute

> element can also have children in it whereas, other can't have.

## DOM MANIPULATION

- **selecting by**

    - getElementById

        ```javascript
        let abcd = document.getElementById("abcd");
        ```

    - getElementsByClass

        ```javascript
        let abcd = document.getElementsByClassName("abcd");
        ```
        - after logging, we get an array like structure.

    - quarySelector
        ```javascript
        let abcd = document.quarySelector("abcd");
        ```

    - quarySelectorAll
        ```javascript
        let abcd = document.quarySelectorAll("h1");
        ```

        - It will select the first coming element only.

        - after logging you will get an array like structure.

    > `getElementsByClass` and `quarySelectorAll` exactly returns an `HTML collection` which looks like an array but not generally an array.
    
    - the below thing will only select the lists of even index.

    ```javascript
    document.quarySelector("li:nth-child(2n)");
    ```



- **Text/Content Access**

    - **innerText**

        - if you want to change only Text content.

    ```javascript
    let h1 = document.quarySelector("h1");
    h1.innerText = "hello world"
    ```
    - **textContent**

        - it is same as innerText. but `faster` then innerText and also can tell about hidden elements.

    ```javascript
    let h1 = document.quarySelector("h1");
    h1.textContent = "hello world"
    ```
    - **innerHTML**

        - if you want to add HTML tags, then you can go through it.

    ```javascript
    let h1 = document.quarySelector("h1");
    h1.innerHTML = "<i>hello world</>"
    ```

- **Attribute Manipulation**

inside a tag, everything else written is attribute. for example;
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="style.css">
    <title>Document</title>
</head>
<body>
    <h1 id="heading">HELLO</h1>
    <script src="script.js"></script>
</body>
</html>
```
here;

 `html` `lang` `charset` `name` `content` `rel` `href` `id` `src`
 all are attributes.
 
 - 
    - **getAttribute**

    from this , you can get the value of any attribute.
    ```javascript
    let a = document.quarySelector("a");
    console.log(a.getAttribute("href"));
    ```

    another way of getting the value of an attrubiete is like `console.log(img.src)`.

    - **setAttribute**

    from this, you can change the value of any attribute of html file.

    ```javascript
    let a = document.querySelector("a");
    a.setAttribute(name , value);
    ```
    
    - **removeAttribute**
    
    from this, you can remove any attribute.

    ```javascript
    let a = document.quarySelector("a");
    a.removeAttribute("href");
    ```

## DYNAMIC DOM MANIPULTION

- **createElement**
- **appendChild**
- **removeChild**
- **prepend**


with `createElement`, you can create element using javascript.
```javascript
let h1 = document.createElement("h1");
```

but by using only this your element will not be added in your webpage. if you want, then you have to `append` or `prepend` that element.

> append => addes in the end

> prepend => added in starting

```javascript
let h1 = document.createElement("h1");
h1.innerText("hello");
document.body.append(h1);
```
- `append` and `appendChild` are the same. 

- from `removeChild` or `remove`, you can remove any element.

## ADDING STYLE USING JAVASCRIPT

you just need to do a single thing, and that is:
```javascript
h1.style.color = 'red';
```
that simple dude!

### APPLYING A CLASS ON AN ELEMENT
you can `add` any font class on your element.

```javascript
h1.classList.add("<class-name>")
```

you can also `remove` any by-default applied font by doing:

```javascript
h1.classList.remove("<class-name>");
```

if your class is applied then `toggle` will remove it or if the class is not applied then toggle will apply it.

```javascript
h1.classList.toggle("<class-name>");
```

## EVENTS AND EVENTS HANDLING

means if you perform any action in your website like `click` `double click` `select` `point` `right click` `scroll` `cursor move` you should get any action in return.

- **EVENT BINDING**
    >event mtlb koi action hua

    > event listener mtlb aapne us action ka reaction diya.

    browser pe koi bhi harkat hui event raise hojaega.

    - **addEventListeners**

    ```javascript
    let h1 = document.quarySelector("h1");

    h1.addEventListener("event" , function);
    ```
    ## 📌 JavaScript Events Reference

    | Event Name | Use (Short Explanation) |
    |-----------|--------------------------|
    | `click` | Mouse click hone par |
    | `dblclick` | Double click hone par |
    | `mouseover` | Mouse element ke upar aaye |
    | `mouseout` | Mouse element se bahar jaye |
    | `mouseenter` | Mouse element me enter kare |
    | `mouseleave` | Mouse element se leave kare |
    | `mousedown` | Mouse button dabane par |
    | `mouseup` | Mouse button chhodne par |
    | `mousemove` | Mouse move hone par |
    | `contextmenu` | Right click hone par |
    | `keydown` | Keyboard key press hone par |
    | `keyup` | Keyboard key chhodne par |
    | `keypress` | Key press (deprecated) |
    | `submit` | Form submit hone par |
    | `change` | Input value change hone par |
    | `input` | Real-time input change |
    | `focus` | Input active hone par |
    | `blur` | Input se bahar aane par |
    | `reset` | Form reset hone par |
    | `load` | Page fully load hone par |
    | `DOMContentLoaded` | HTML load hone ke baad |
    | `scroll` | Page scroll hone par |
    | `resize` | Window size change hone par |
    | `drag` | Element drag karte waqt |
    | `dragstart` | Drag start hone par |
    | `drop` | Element drop hone par |
    | `copy` | Text copy hone par |
    | `cut` | Text cut hone par |
    | `paste` | Text paste hone par |
    | `play` | Audio/Video play hone par |
    | `pause` | Audio/Video pause hone par |
    | `ended` | Media end hone par |




    for example:
    ```javascript
    let h1 = document.quarySelector("h1");

    function click(){
        h1.style.color = "red";
    }

    h1.addEventListener("click" , click);
    ```

    - **removeEventListeners**

    ```javascript
    h1.removeEventListener("click" , click);
    ```
    ### COMMON EVENTS

    - **CLICK**

        ```javascript
        let h1 = document.quarySelector("h1");

        function click(){
            h1.style.color = "red";
        }

        h1.addEventListener("click" , click);
        ```

    - **INPUT**

        ```javascript
        let inp = document.quarySelector("input");

        inp.addEventListener("input", function(a){
            console.log(a.data);
        });
        ```

    - **CHANGE**

        yeh tab chalta hai jab aapke input select yah text area mai koi change aata h

        ```JAVASCRIPT
        let select = document.quarySelector("select");
        let h1 = document.querySelector("h1");

        select.addEventListener("change" , function(){
        h1.innerHTML = "device selected";
        });
        ```

        > you can also use these functions as methods like `h1.click()`.

    - **SUBMIT**

        YEH jab use hota hai jab hm koi bhi form create karte hai or usko submit karte hai toh submit krne k baad hm kese react kre uske liye use hota h.

        > jab bhi form submit hoga hmara function chalega.

        > to prevent your screen form reloading the thing you can uses is `evt.preventDefault()` where `evt` is the value returned by the function.

    - **MOUSEOVER**

        mtlb jab kisi element pai mouse aae toh usme function chl jaega.

        ```javascript
        let div = document.quarySelector("div");

        div.addEventListener("mouseover" , function(){
            div.style.backgroundColor = "yellow";
        });
        ```

    - **MOUSEOUT**

        jab hmara mouse us element pai se htega toh kya changes aaynge.

        ```javascript
        let div = document.quarySelector("div");

        div.addEventListener("mouseout" , function(){
            div.style.backgroundColor = "red";
        });
        ```

    - **MOUSEMOVE**

        mtlb hm jab screen p yah particular kisi element p cursor move krenge toh hm function chla skte hai.

        `clientX` `clientY` are the values of X-axis and Y-axis respectively.

        ```JAVASCRIPT
        let main = document.querySelector("#main");

        window.addEventListener("mousemove" , function(dets){
            main.style.top = dets.clientY + "px";
            main.style.left = dets.clientX + "px";
        });
        ```

    - **keydown**

        jb hm koi key press krte hai toh kya chnges ho.

    - **keyup**

        jb hm koi key release karte hai toh kya changes ho,

## EVENT OBJECT

jab bhi ham kisi element pai addEventListener lagate hai toh us function k andr jo hme value return mai ilti hai wo hmara event object hota hai.

- **TARGET**

```javascript
let div = document.quaryselector("div");

div.addEventListener("click" , function(dets){
    console.log(dets);
});
```
jis element p kuch bhi action hua hai toh `dets.target` mai wohi element present hoga.

- **TYPE**

element p kis type ka event perform hua. `click` `mouseover` `mouseout` `submit`.

- **PREVENTDEFAULT**

    yeh submit hote time screen ko reresh hone se rokta hai.

## EVENT BUBBLING

MTLB jis element p event perform hoga agr us element p event listener nhi hua toh uske parent p listener dhunda jaega. or esa krte krte upr ki trf move krega.

let suppose we have created an `ul` inside the body tag and in ul we have created a number of `li` in it and applied event listener on ul so if we selected any li or apply any event on it then as per this `event bubbling` rule the event listener applied on ul will work.

*HTML*
```html
<body>
    <ul id = "main">
        <li>priya</li>
        <li>hema</li>
        <li>yashvi</li>
        <li>roshni</li>
        <li>gopi bahu</li>
        <li>fullo debi</li>
        <li>santara devi</li>
        <li>kalavati</li>
    </ul>
    <script src="script.js"></script>
</body>
```

*JAVASCRIPT*
```javascript
let ul = document.querySelector("#main");

ul.addEventListener("click" , function(dets){
    dets.target.classList.toggle("lt");
});
```
> EVENT BUBBLING KA MTLB HAI AGR KISI CHILD P EVENT PERFORM HOTA HAI TOH USKE TREE MAI JITNE BHI PARENT HAI UNPE JOBHI EVENT LISTENER LGE HAI WOH SB PERFORM HOTE HAI.

## EVENT CAPTURING

jab bhi aap click karte ho yah kooi bhi event raise karte ho to aapka event flow 2 phase mai chalta hai.

1. event top level element sai niche ki taraf aayega.(`capture phase`)
2. event raised element sai niche ki araf aayega.(`bubbling phase`)

hmesha phle phase 1 hi chlta hai pr wo by default off hota hai.

suppose we have a code

```html
<body>
    <div id="a">
        <div id="b">
            <div id="c">
                <button>click me</button>
            </div>
        </div>
    </div>
</body>
```
capture phase means agr hm button ko click krenge to as per js rule phle capturing phase chalega or wo check krega ki top level element mai capture phase on h ki nhi mtlb `a` mai phir check krega `b` mai or phir `c` mai then `button` mai or agr inme se kisi m bhi capture phase on nhi hoga toh by default bubbling phase chal jaega. or phle `button` ka event listener chlega phir `c` ka phir `b` ka or last mai `a` ka.

agr capturing phase on hua toh phle `div a` ka event listener chlega phir `b` ka phir `c` ka or phir last mai `button` ka

`for turning the capture phase on`

just type `, true` before last `)` brackets.

```javascript
div.addEventListener("clicked" , function(){
    alert("clicked");
}, true );
```
that simple dude!!

let's take an example.

```javascript
let a = document.quarySelector("#a");
let b = document.quarySelector("#b");
let c = document.quarySelector("#c");
let button = document.quarySelector("button");

a.addEventListener("clicked" , function(){
    console.log("a clicked");
}, true);

b.addEventListener("clicked" , function(){
    console.log("b clicked");
});

c.addEventListener("clicked" , function(){
    console.log("c clicked");
}, true);

button.addEventListener("clicked" , function(){
    console.log("button clicked");
});
```
as a result we get output,
```
a clicked
c clicked 
button clicked
b clicked
```

## FORMS AND FORMS VALIDATION

when we create a form, there are some basic criteria for getting an input. like , for name, minimum character should be 3.

### READING VALUES FROM INPUT, TEXTAREA, SELECT.
for reading valuues fro input you can use;

```javascript
let inp = document.quarySelector("input");

inp.addEventListener("clicked" , function(dets){
dets.preventdefault();
    console.log(inp.value);
})
```

### INLINE VALIDATION

you can add specific criterias in html part also, for example:-
    `required` `minlength` `maxlength` 

### PATTERN ATTRIBUTE

```html
    <input pattern="[a-z]{3-8}" type="text">
```

### REGEX

regex is a fully different language which is a mixture of patterns of code.

```javascript
let inp = document.querySelector("#main");

inp.addEventListener("click" , function(dets){
    dets.preventDefault();
    const emailRegex = /^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/;
    emailRegex.test(inp.value);
});
```

you may get these rege code from ChatGPT and you may create your custom regex also.

## TIMERS AND INTERVALS

### SET TIMEOUT

`setTimeout` is a function which takes a function and time in mili seconds. 1 second = 1000 mili seconds. which means setTimeout given seconds mai given function ko chala dega.

```javascript
setTimeout(function(){
    console.log("hello");
}, 5000);
```
this will log `hello` on console window after 5 seconds.

### SET INTERVAL

`setInterval` is also a function which too takes a funcions and time in mili seconds. and repeat that funcion in the given time interval.

```javascript
setInterval(function(){
    console.log("hello");
}, 5000);
```

this will log `hello` on consle window in every 5 seconds.

### CLEAR TIMEOUT

this function is used to stop a timeout which in going to be run in an interval of time.

```javascript
let time = setTimeout(function(){
    console.log("hello");
}, 5000);

clearTimeout(time);
```

mtlb jo `time` timeout 5 second baad chalne wala tha wo aab nahi chalega.

### CLEAR INTERVAL

this function is also used to stop an interval setted in the above code.

```javascript
let time = setInterval(function(){
    console.log("hello");
}, 5000);

clearInterval(time);
```
mtlb jo `time` Interval har 5 second mai chalne wala tha wo aab nahi chalega.

## LOCAL STORAGE, SESSION STORAGE AND COOKIES

### LOCAL STORAGE
aapke browser k andr data store karna jo browser ke band hone k baad bhi store hi rhta hai delete nahi hoga.

- **TO STORE YOUR DATA**
    ```javascript
    localStorage.setItem("name" , "harsh");
    ```

- **TO FETCH YOUR STORED DATA**
    ```javascript
    localStorage.getItem("name");
    ```
- **TO REMOVE DATA**
    ```JAVASCRIPT
    localStorage.removeItem("name");
    ```
- **TO UPDATE YOUR STORED DATA**
    ```JAVASCRIPT
    localStorage.setItem("name" , "harshita");
    ```
- **TO DELETE ALL DATA**
    ```javascript
    localStorage.clear();
    ```

### SESSION STORAGE
yeh aapke data ko temporarily store karta hai matlab browser band hua or data gaya.

methods used in `sessionStorage` is same as `localStorage`.

> `localStorage` and `sessionStorage` stores approx 5MB data.

### COOKIES 
yeh bhi data store karta hai par yeh data aapke browser ki cookie naam ki property mai save ho jata hai jo property banayi gyi thi kam data store karne ke liye.

> `cookies` stores approx 4 KB data.

cookies mai tum jo bhi data store karonge woh reload hone ke baad automatically server par chala jaega.

to add a cookie in your website,
```javascript
document.cookie("name=priya");
```
this will create a cookie named `name` having value `priya`.

we can also delete our cookie after sometime. for this we have to make a key value named `max-age` the value given to it is the time in seconds.

```javascript
document.cookie = "username=priya; max-age=60; path=/";
```

> **if we try to save data in `localStorage` other than strings then we will face many difficulties**
 array will become a string itself and object will return a value [object, Object].

>is sai bachne k liye ham phle us data ko `JSON.stringify` sai string mai convert kardenge or firr jb hme usko use karna hoga toh usko `JSON.parse` sai waps us particular object type mai le aaynge.

## DARK OR LIGHT MODE DETECTOR
to detect the theme of user. you may use `window.matchMedia("(prefers-color-scheme: dark")`

if you want to add function like if the screen is dark then a dark class will be applied to body which changes the theme of the website into dark

```javascript
function setDarkOrLight() {
    if (window.matchMedia('(prefers-color-scheme: dark)').matches) {
        document.body.classList.add("dark");
        document.body.classList.remove("light");
    } else {
        document.body.classList.add("light"); 
        document.body.classList.remove("dark");
    };
};
```
> `localStorage` is able to store only string data not others because it's API is build only or strings.

