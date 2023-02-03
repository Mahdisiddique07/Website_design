# Heading Project 1

## Main Homepage HTML

### HTML

```html
      <div class="expandingcards">
        <div class="container">
          <div class="pannel" style="background-image: url('../Images/RickOwens.jpg');">
            <h3>Rick Owens</h3>
          </div>
          <div class="pannel" style="background-image: url('../Images/YohjiYamamoto.png');">
            <h3>Yohji Yamamoto</h3>
          </div>
          <div class="pannel" style="background-image: url('../Images/BorisBidjan.jpeg');">
            <h3>Boris Bidjan</h3>
          </div>
          <div class="pannel" style="background-image: url('../Images/AnnDemeulemeester.png');">
            <h3>Ann Demeulemeester</h3>
          </div>
        </div>
      </div>
```
Our main page uses an expanding image to display the featured designers. 
As you can see we created a div class called 
1) expandingcards for more control on our css as we used a generalized commonly used div class called 
2) pannel for the images themselves.

### CSS

```css
.expandingcards {
    display: flex;
    align-items: center;
    justify-content: center;
}

.container {
    display: flex;
    width: 90vw;
}

.pannel {
    background-size: auto 100%;
    background-position: center;
    background-repeat: no-repeat;
    height: 80vh;
    border-radius: 50px;
    color: #fff;
    cursor: pointer;
    flex: 0.5;
    margin: 10px;
    position: relative;
    transition: flex 0.7s ease-in;
}

.pannel h3 {
    font-size: 24px;
    position: absolute;
    bottom: 20px;
    left: 20px;
    margin: 0;
    opacity: 0;
}

.pannel.active {
    flex: 2;
}

.pannel.active h3 {
    opacity: 1;
    transition: opacity 0.3s ease-in 0.4s;
}
```
As you can see on our css, we used class identification where the 
3) expandingcards is the main container while 
4) the .container creates the default width and 
5) .pannel with it's 0.5flex is the default unexpanded card for each designer and we gave our site a 0.7s transition as it expands the .pannel, 
6) h3 is for the names of the designer which handles all the styling for the text once the image has been expanded.

## JS

```javascript
const pannels = document.querySelectorAll(".pannel")

pannels.forEach(pannel => {
    pannel.addEventListener("click", () => {
        removeActiveClasses()
        pannel.classList.add("active")
    })
})

function removeActiveClasses() {
    pannels.forEach(pannel => {
        pannel.classList.remove("active")
    })
}
```
7) The object const pannels is our DOM object for the javascript which searches for any class named .pannel

## Top Nav

Html

```html
    <link rel="stylesheet" href="../CSS/common.css">
    <link rel="stylesheet" href="../CSS/homepage.css">
    <link rel='stylesheet' href='https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css'>
  <nav class="topnav centering">
      <a href="clothingpage.html">Clothing</a>
      <a href="shoespage.html">Shoes</a>
      <a href="accessoriespage.html">Accessories</a>
      <div id="hiddenaccount">
        <div id="links">
          <a href="accountpage.html">Account</a>
          <a href="createaccountpage.html"><span style="word-spacing: -4px; white-space: nowrap;">Create Account</span></a>
        </div>
        <button id="icon"><i class="fa fa-user-circle-o fa-2x" aria-hidden="true"></i></button>
      </div>
    </nav>
```
8) Our topnav consists of multiple &lt;a&gt; and
9) implementation of the project hidden search from udemy named hiddenaccount as show in the code above
10) We have an icon for the button for hiddenaccount and we have it by linking an offsite css file from the internet as shown as the 3rd css in the html code posted above

 CSS
 ```css
 .a1 { 
    text-decoration: none;
    color: black; 
    font-weight: bold; 
    letter-spacing: 0.5px; 
    font-size: 35px;
}

.topnav {
    overflow: hidden;
    background-color: black;
}

.topnav a {
    float: left;
    color: white;
    padding: 10px 16px;
    text-decoration: none;
    font-size: 15px;
    letter-spacing: 0.1px;
}

.topnav a:hover {
    background-color:#ddd;
    color: black;
}

.topnav a.currentpage {
    background-color: #ddd;
    color: black;
}

#hiddenaccount {
    float: right;
    display: flex;
    align-items: center;
    padding-right: 2.5px;
    width: 43px;
}

.bottomnav {
    text-align: center;
    padding: 20px;
}

.bottomnav a {
    margin: 0 20px;
    letter-spacing: 0px;
    font-size: 10px;
    font-family: arial;
    text-decoration: none;
    color: #585858;
}
```
11) the css code shown above is from our common.css which is used by every page on our website. 
12) As you can see our topnav &lt;a&gt; have  the hover selector action giving it a differentiating background and text color.

JS
```javascript
const icon = document.getElementById("icon")
const links = document.getElementById("links")
const hiddenaccount = document.getElementById("hiddenaccount")

icon.addEventListener("click", () => {
    links.classList.toggle("open")
    hiddenaccount.classList.toggle("open2")
})
```
Our Common.js contains the following
13) Constant variables icon, links, hiddenaccount using the DOM to find each identifier
14)the icon object is given an event listener where it listens for clicks and forces the open toggle for both links and hiddenaccount classes.
15) Our Navs, banners, company names, footer located in our common html,css,js are in every page as it's used by every single one, consolidated into one file.

## Product pages
16) our product pages uses the &lt;table&gt; tag to display each of our items
17) Each product is contained within it's own cell
### HTML
```html
    <main>
      <table>
        <tr>
          <td>
            <img src="../Images/yohji_blazer.jpg">
            <p>Yohji Yamamoto's</p>
            <p>Black Wool Blazer</p>
            <p class="discount">$1200</p>
            <p>$600</p>
          </td>
          <td>
            <img src="../Images/wrappedtrousers.jpg">
            <p>Yohji Yamamoto's</p>
            <p>Black Wool Wrapped Trousers</p>
            <p class="discount">$1100</p>
            <p>$550</p>
          </td>
          <td>
            <img src="../Images/boris_horse_jacket.jpg">
            <p>Boris Bidjan's</p>
            <p>Black Horse Leather Jacket</p>
            <p class="discount">$4500</p>
            <p>$3000</p>
          </td>
          <td>
            <img src="../Images/boris_turtleneck.jpg">
            <p>Boris Bidjan's</p>
            <p>Black Cashmere Turtleneck</p>
            <p class="discount">$500</p>
            <p>$320</p>
          </td>
          <td>
            <img src="../Images/rick_cropped_pants.jpg">
            <p>Rick Owens'</p>
            <p>Black Cropped Cargo Pants</p>
            <p class="discount">$1000</p>
            <p>$370</p>
          </td>
          <td>
            <img src="../Images/rick_blazer.jpg">
            <p>Rick Owens'</p>
            <p>Black Wool Blazer</p>
            <p class="discount">$2400</p>
            <p>$700</p>
          </td>
        </tr>
        <tr>
          <td>
            <img src="../Images/rick_wool_pants.jpg">
            <p>Rick Owens'</p>
            <p>Black Karloff Cropped Pants</p>
            <p class="discount">$1150</p>
            <p>$350</p>
          </td>
          <td>
            <img src="../Images/rick_string_jacket.jpg">
            <p>Rick Owens'</p>
            <p>Black Mega Laced Jacket</p>
            <p class="discount">$3000</p>
            <p>$1600</p>
          </td>
          <td>
            <img src="../Images/rick_burgundy_jacket.jpg">
            <p>Rick Owens'</p>
            <p>Burgundy Bomber Jacket</p>
            <p class="discount">$1800</p>
            <p>$580</p>
          </td>
          <td>
            <img src="../Images/ann_sweater.jpg">
            <p>Ann Demeulemeester's</p>
            <p>Black & White Wool Hoodie</p>
            <p class="discount">$1100</p>
            <p>$506</p>
          </td>
        </tr>
      </table>
    </main>
```
18) the &lt;img&gt; tag displays the picture of the product
19) each cell receives 4 &lt;p&gt; tags. Designer name, item name, discount, and our price in that order.
20) All of our html for every page uses &lt;main&gt; as the container for the main content of every page.
We have clothing, accessories, and shoes as their own separate pages containing the same similar structure.

### CSS
```css
.discount {
    color: grey;
    text-decoration: line-through;
}

table, td {
    text-align: center;
    
}

table {
    width: auto;
    margin: auto;
    border-collapse: collapse;
}

td {
    border: 1px solid lightgrey;
    padding: 10px;
}
```
21) Our product sites share common.css, along with products.css as shown above
22) .discount class determines the text for the original price being grayed out and strike through as we display the sale value below it.
23) table,td slector aligns the text to center it
24) table selector auto sizes the tables, along with the margin while the border-collapse: collapse forces the cells to have their own borders
25) td selector defines the border thickness and padding for each item.

## Register & Account Pages

### HTML

```HTML
 <main>
        <p class="centering heading">Register</p>
        <div class="progresssteps">
            <div class="container">
                <div class="progress-container">
                <div class="progress" id="progress"></div>
                <div class="circle active current">1</div>
                <div class="circle">2</div>
                <div class="circle">3</div>
                </div>
            </div>
        </div>
        <form class="input" id="registration" action="registeringpage.html">
            <div class="register">
                <table>
                    <tr>
                        <td><label for="email">Email:</label></td>
                        <td><input type="email" name="email" id="email" size="30"></td>
                    </tr>
                    <tr>
                        <td><label for="password">Password:</label></td>
                        <td><input type="password" name="password" id="password" size="30"></td>
                    </tr>
                </table>
            </div>
            <div class="register inactive">
                <table>
                    <tr>
                        <td><label for="fname">First name:</label></td>
                        <td><input type="text" name="fname" id="fname" size="20"></td>
                    </tr>
                    <tr>
                        <td><label for="lname">Last name:</label></td>
                        <td><input type="text" name="lname" id="lname" size="20"></td>
                    </tr>
                    <tr>
                        <td><label for="gender">Gender:</label></td>
                        <td>
                            <select name="gender" id="gender">
                                <option></option>
                                <option value="male">Male</option>
                                <option value="male">Female</option>
                            </select>
                        </td>
                    </tr>
                    <tr>
                        <td><label for="dob">Date of Birth:</label></td>
                        <td><input type="date" name="dob" id="dob" size="30"></td>
                    </tr>
                    <tr>
                        <td><label for="address">Address:</label></td>
                        <td><input type="text" name="address" id="address" size="50"></td>
                    </tr>
                    <tr>
                        <td><label for="city">City:</label></td>
                        <td><input type="text" name="city" id="city" size="20"></td>
                    </tr>
                    <tr>
                        <td><label for="state">State:</label></td>
                        <td>
                            <select name="state" id="state">
                                <option></option>
                                <option value="Alabama">Alabama</option>
                                <option value="Alaska">Alaska</option>
                                <option value="Arizona">Arizona</option>
                                <option value="Arkansas">Arkansas</option>
                                <option value="California">California</option>
                                <option value="Colorado">Colorado</option>
                                <option value="Connecticut">Connecticut</option>
                                <option value="Delaware">Delaware</option>
                                <option value="District Of Columbia">District Of Columbia</option>
                                <option value="Florida">Florida</option>
                                <option value="Georgia">Georgia</option>
                                <option value="Hawaii">Hawaii</option>
                                <option value="Idaho">Idaho</option>
                                <option value="Illinois">Illinois</option>
                                <option value="Indiana">Indiana</option>
                                <option value="Iowa">Iowa</option>
                                <option value="Kansas">Kansas</option>
                                <option value="Kentucky">Kentucky</option>
                                <option value="Louisiana">Louisiana</option>
                                <option value="Maine">Maine</option>
                                <option value="Maryland">Maryland</option>
                                <option value="Massachusetts">Massachusetts</option>
                                <option value="Michigan">Michigan</option>
                                <option value="Minnesota">Minnesota</option>
                                <option value="Mississippi">Mississippi</option>
                                <option value="Missouri">Missouri</option>
                                <option value="Montana">Montana</option>
                                <option value="Nebraska">Nebraska</option>
                                <option value="Nevada">Nevada</option>
                                <option value="New Hampshire">New Hampshire</option>
                                <option value="New Jersey">New Jersey</option>
                                <option value="New Mexico">New Mexico</option>
                                <option value="New York">New York</option>
                                <option value="North Carolina">North Carolina</option>
                                <option value="ND">North Dakota</option>
                                <option value="Ohio">Ohio</option>
                                <option value="Oklahoma">Oklahoma</option>
                                <option value="Oregon">Oregon</option>
                                <option value="Pennsylvania">Pennsylvania</option>
                                <option value="Rhode Island">Rhode Island</option>
                                <option value="South Carolina">South Carolina</option>
                                <option value="South Dakota">South Dakota</option>
                                <option value="Tennessee">Tennessee</option>
                                <option value="Texas">Texas</option>
                                <option value="Utah">Utah</option>
                                <option value="Vermont">Vermont</option>
                                <option value="Virginia">Virginia</option>
                                <option value="Washington">Washington</option>
                                <option value="West Virginia">West Virginia</option>
                                <option value="Wisconsin">Wisconsin</option>
                                <option value="Wyoming">Wyoming</option>
                            </select>
                        </td>
                    </tr>
                    <tr>
                        <td><label for="zip">Zip code:</label></td>
                        <td><input type="text" name="zip" id="zip" maxlength="5" size="5"></td>
                    </tr>
                </table>
            </div>
            <div class="register inactive">
                <table id="summarize">
                    <tr>
                        <td>Email:</td>
                        <td id="emailinput"></td>
                    </tr>
                    <tr>
                        <td>First name:</td>
                        <td id="fnameinput"></td>
                    </tr>
                    <tr>
                        <td>Last name:</td>
                        <td id="lnameinput"></td>
                    </tr>
                    <tr>
                        <td>Gender:</td>
                        <td id="genderinput"></td>
                    </tr>
                    <tr>
                        <td>Date of birth:</td>
                        <td id="dobinput"></td>
                    </tr>
                    <tr>
                        <td>Address:</td>
                        <td id="addressinput"></td>
                    </tr>
                    <tr>
                        <td>City:</td>
                        <td id="cityinput"></td>
                    </tr>
                    <tr>
                        <td>State:</td>
                        <td id="stateinput"></td>
                    </tr>
                    <tr>
                        <td>Zip:</td>
                        <td id="zipinput"></td>
                    </tr>
                </table>
            </div>
        </form>
        <div class="progresssteps" style="flex-direction: column;">
            <div>
                <button class="btn" id="prev" disabled>Prev</button>
                <button class="btn" id="next">Next</button>
            </div>
            <button class="btn inactive" type="submit" form="registration" id="submit">Register</button>
        </div>  
    </main>

```
26) The following HTML is a sample of our Register page. It uses Tables, forms, divs to divide the registration into 3 different phases.
27) the #progress-container contains circles that display 3 different phases of the registration, each one being altered as the user presses next before finally landing in phase 3 where all data inserted is displayed as a table to confirm witht he user

### CSS
```css
:root {
    --line-border-fill: black;
    --line-border-empty: #e0e0e0;
}

.progresssteps {
    display: flex;
    align-items: center;
    justify-content: center;
    overflow: hidden;
    margin: 0;
}

.container {
    text-align: center;
}

.progress-container {
    display: flex;
    align-items: center;
    justify-content: space-between;
    position: relative;
    margin-bottom: 30px;
    max-width: 100%;
    width: 350px;
}

.progress-container::before {
    content: "";
    background-color: var(--line-border-empty);
    color: var(--line-border-empty);
    position: absolute;
    top: 50%;
    left: 0;
    transform: translateY(-50%);
    height: 4px;
    width: 100%;
    z-index: -1;
}

.progress {
    background-color: var(--line-border-fill);
    color: var(--line-border-fill);
    position: absolute;
    top: 50%;
    left: 0;
    transform: translateY(-50%);
    height: 4px;
    width: 0%;
    z-index: -1;
    transition: 0.4s ease;
}

.circle {
    background-color: white;
    color: #999;
    border-radius: 50%;
    height: 30px;
    width: 30px;
    display: flex;
    align-items: center;
    justify-content: center;
    border: 3px solid var(--line-border-empty);
    transition: 0.4s ease;
}

.circle.active {
    border-color: var(--line-border-fill);
    color: var(--line-border-fill);
}

.circle.current {
    font-weight: bolder;
    font-size: 20px;
    height: 40px;
    width: 40px;
}

.input {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    overflow: hidden;
    margin: 0;
    padding-bottom: 20px;
}

td {
    padding: 5px;
}

#summarize, #summarize td{ 
    border: 2px solid black;
    border-collapse: collapse;
}

.inactive {
    display: none;
}
```
28) As you can see above, our selectors uses a variation of display: flex/none and mainly our css makes sure that the content is displayed at the center of our screen

### JS
```js
const progress = document.getElementById("progress")
const prev = document.getElementById("prev")
const next = document.getElementById("next")
const circles = document.querySelectorAll(".circle")
const registersteps = document.querySelectorAll(".register")
const submit = document.getElementById("submit")

let currentActive = 1

let email, fname, lname, gender, dob, address, city, state, zip 

next.addEventListener("click", () => {
    currentActive++

    if(currentActive > circles.length) {
        currentActive = 3
    }
    
    updateprogress()
    updateform()
})

prev.addEventListener("click", () => {
    currentActive--

    if(currentActive < 1) {
        currentActive = 1
    }

    updateprogress()
    updateform()
})

function getformdata() {
    email = document.getElementById("email").value
    fname = document.getElementById("fname").value
    lname = document.getElementById("lname").value
    gender = document.getElementById("gender").value
    dob = document.getElementById("dob").value
    address = document.getElementById("address").value
    city = document.getElementById("city").value
    state = document.getElementById("state").value
    zip = document.getElementById("zip").value
}

function updateprogress() {
    circles.forEach((circle, idx) => {
        if(idx < currentActive) {
            circle.classList.add("active")
        } else {
            circle.classList.remove("active")
        }
    })

    const actives = document.querySelectorAll(".active")

    progress.style.width = (actives.length - 1) / (circles.length - 1) * 100 + "%"

    if(currentActive === 1) {
        next.innerHTML = "Next"
        prev.disabled = true
        submit.classList.add("inactive")
    } else if(currentActive === circles.length){
        next.disabled = true
        submit.classList.remove("inactive")
    } else {
        next.innerHTML = "Next"
        prev.disabled = false
        next.disabled = false
        submit.classList.add("inactive")
    }
}

function updateform() {
    switch(currentActive) {
        case 1:
            registersteps.forEach((registerstep, idx) => {
                if(idx == 0) {
                    registerstep.classList.remove("inactive")
                    circles[0].classList.add("current")
                    circles[1].classList.remove("current")
                    circles[2].classList.remove("current")
                } else {
                    registerstep.classList.add("inactive")
                }
            })
            break
        case 2:
            registersteps.forEach((registerstep, idx) => {
                if(idx == 1) {
                    registerstep.classList.remove("inactive")
                    circles[0].classList.remove("current")
                    circles[1].classList.add("current")
                    circles[2].classList.remove("current")
                } else {
                    registerstep.classList.add("inactive")
                }
            })
            break
        case 3:
            registersteps.forEach((registerstep, idx) => {
                if(idx == 2) {
                    registerstep.classList.remove("inactive")
                    circles[0].classList.remove("current")
                    circles[1].classList.remove("current")
                    circles[2].classList.add("current")
                } else {
                    registerstep.classList.add("inactive")
                }
            })
            getformdata()
            document.getElementById("emailinput").innerHTML = email
            document.getElementById("fnameinput").innerHTML = fname
            document.getElementById("lnameinput").innerHTML = lname
            document.getElementById("genderinput").innerHTML = gender
            document.getElementById("dobinput").innerHTML = dob
            document.getElementById("addressinput").innerHTML = address
            document.getElementById("cityinput").innerHTML = city
            document.getElementById("stateinput").innerHTML = state
            document.getElementById("zipinput").innerHTML = zip
            break
    }
}
```
29) the function getFormData pulls all the data from the entire form with their respective names.
30) updateprogress() updates the circle phases in the progress container
31) updateform() updates the circle phases depending on the current phase of the registration, switching the active form data and the none active data of the form.
> Written with [StackEdit](https://stackedit.io/).
