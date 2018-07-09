```js

/*
TheNetNinja: How to use JS to: DOM
address: https://www.youtube.com/watch?v=FIORjGvT0kk&index=1&list=PL4cUxeGkcC9gfoKa5la9dsdCNpuey2s-V
- Change / remove HTML elements in the DOM
- Change and add CSS styles to elements
- Read and change element attributes (href, src, alt, custom)
- Create new HTML elements and insert them into the DOM/page
- Attach event listener to elements (click, keypress, submit)
*/

// 0. IMPORTANT: Add this to ensure all JS code to be run. Wrap this around all other code

document.addEventListener('DOMContentLoaded', function() {

});

// 1. How to select DOM elements
document.getElementById('page-banner');
document.getElementByClassName('title');
document.getElementByTagName('li');

document.querySelector('.button__red');
document.querySelectorAll('li');

// Special case 
document.forms['add_book'] << 'id'
e.target.dataset.target << 'data-set-name'

// 2. IMPORTANT: How to change NodeList to Array. (You will see this often because the DOM elements returned from querySelectorAll are not arrays)

Array.from(NodeListName).forEach(function(item) {
    console.log(item);
});

// 2.5 Event Bubbling: The events that happen to the children elements will bubble up to the parent element. Which means you can attached a eventListener to the parent and check if the events happen on any of the children.

const list = document.querySelector('.book-list');
list.addEventListener('click', function(e) {
    if (e.target.className == 'delete-button') {
        const li = e.target.parentElement;
        list.removeChild(li);
    }
})

// 3. How to select the text of the DOM Element
.textContent
.innerHTML
e.target.value

// 4. Some more variable or functions you can use
.nodeType
.nodeName
.hasChildNodes()
.cloneNode(true) // This will clone every children elements if it is set as true 
.parentNode // Comments are consider as Node too in DOM. So this might not return a HTML element every single time
.parentElement
.childNodes
.children
.nextSibling
.nextElementSibling
.previousSibling
.previousElementSibling

// 5. How to add event listener to DOM elements.
'keyup', 'change'

h2.addEventListener('click', function(e) {
    console.log(e.target);
})

// 6. IMPORTANT: How to prevent default behaviour
button.addEventListener('click', function(e) {
    e.preventDefault();
});

// 7. Get value from form input
const value = addForm.querySelector('input[type="text"]').value;

// 8. How to create DOM Element in 3 steps
// 8.1. Create the element
const li = document.createElement('li');
const bookName = document.createElement('span');

// 8.2. Insert text content
bookName.textContent = 'Book';

// 8.3. Append to document
li.appendChild(bookName);
li.appendChild(deleteBtn);
list.appendChild(li);

// 9. How to style element with JS
// 9.1.  Select the elements
// 9.2. .style.attrName

li.style.color = 'red';

// 9.3. Or by adding a class
li.classList.add('active');
li.classList.remove('active');


// 10. Other attributes
.setAttribute('class', 'active');
.getAttribute('class');
.hasAttribute('class'); // true / false
.removeAttribute('class');

// 11. Code for checkbox 
const hideBox = document.querySelector('#hide');
hideBox.addEventListener('change', function(e) {
    if (hideBox.checked) {
        list.style.display = 'none';
    } else {
        list.style.display = 'block';
    }
});

// 12. IMPORTANT: Code for search
const searchBar = document.forms['search-books'].querySelector('input');
searchBar.addEventListener('keyup', function(e) {
    const term = e.target.value.toLowerCase();
    const books = list.getElementsByTagName('li');

    Array.from(books).forEach(function(book) {
        const title = book.firstElementChild.textContent;

        if (title.toLowerCase().indexOf(term) != -1) {
            book.style.display = "block";
        }
    });
});

// 13. Switch tab using JS 
const tabs = document.querySelector('.tabs'); // Parent element for tabs 
const panels = document.querySelectorAll('.panel');

tabs.addEventListener('click', function(e) {
    if (e.target.tagName == 'LI') {
        const targetPanel = document.querySelector(e.target.dataset.target);
        panels.forEach(function(panel) {
            if (panel == targetPanel) {
                panel.classList.add('active');
            } else {
                panel.classList.remove('active');
            }
        });
    }
});



```