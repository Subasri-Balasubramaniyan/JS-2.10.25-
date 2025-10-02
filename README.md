DOM Manipulation

The DOM represents the web page. You can create, edit, or remove elements.

Common Methods
let el = document.getElementById("text");
document.querySelector(".class");

Changing Content
el.innerHTML = "New Text";

Creating Elements
let div = document.createElement("div");
div.textContent = "Hello";
document.body.appendChild(div);

Class & Attributes
el.classList.add("highlight");
el.classList.remove("highlight");
el.setAttribute("title", "tooltip");

🔹BOM (Browser Object Model)

BOM gives access to the browser itself, beyond the page.

Window
console.log(window.innerWidth, window.innerHeight);

Alert / Confirm / Prompt
alert("Hello!");
let ok = confirm("Are you sure?");
let name = prompt("Enter your name:");

Location
console.log(location.href);
location.href = "https://google.com"; // redirect

Navigator
console.log(navigator.language);
console.log(navigator.onLine);

Screen
console.log(screen.width, screen.height);


⚠️ Note: BOM works only in browser, not in Node.js.

🔹Timers

Used for scheduling and repeating tasks.

setTimeout (one-time delay)
setTimeout(() => console.log("Runs after 2s"), 2000);

clearTimeout (cancel timeout)
let t = setTimeout(() => console.log("Not running"), 2000);
clearTimeout(t);

setInterval (repeat)
let count = 0;
let id = setInterval(() => {
  console.log("Tick", ++count);
}, 1000);

clearInterval (stop repeat)
clearInterval(id);

Full Example
<p id="status">Waiting...</p>
<button id="stopTimeout">Stop Timeout</button>
<button id="stopInterval">Stop Interval</button>

<script>
let status = document.getElementById("status");

let timeoutId = setTimeout(() => {
  status.textContent = "⏰ Timeout executed after 3s!";
}, 3000);

document.getElementById("stopTimeout").onclick = () => {
  clearTimeout(timeoutId);
  status.textContent = "❌ Timeout canceled!";
};

let count = 0;
let intervalId = setInterval(() => {
  count++;
  status.textContent = "🔄 Interval running... Count=" + count;
}, 1000);

document.getElementById("stopInterval").onclick = () => {
  clearInterval(intervalId);
  status.textContent = "✅ Interval stopped!";
};
</script>

✅ Summary

Error Handling → try, catch, finally, throw, custom errors.

Event Handling → addEventListener, event object, bubbling, delegation.

DOM Manipulation → select, create, edit, remove elements.

BOM → interact with browser (window, alert, location, navigator, screen).

Timers → schedule tasks with setTimeout, setInterval, and cancel them.
