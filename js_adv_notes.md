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
