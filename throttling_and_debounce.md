# Throttling And Debounce

Throttling and debouncing are techniques used in JavaScript to control the frequency of certain events like function calls, scroll events, or resize events. These techniques can help optimize performance, prevent excessive function calls, and improve user experience.

1. **Throttling**:

Throttling limits the rate at which a function is invoked. It ensures that the function can be executed only once within a specified time interval, even if the event triggering the function occurs multiple times during that interval.

Here's an example of throttling a function that logs mouse move events:

```javascript
// Throttling function
function throttle(func, delay) {
	let timeoutId;
	return function (...args) {
		if (!timeoutId) {
			// Execute the function immediately if timeoutId is not set
			func.apply(this, args);
			timeoutId = setTimeout(() => {
				timeoutId = null;
			}, delay);
		}
	};
}

// Example usage
function handleMouseMove(event) {
	console.log("Mouse coordinates:", event.clientX, event.clientY);
}

// Throttle the `handleMouseMove` function to execute at most once every 100ms
const throttledMouseMove = throttle(handleMouseMove, 100);

// Add event listener to listen for mouse move events
document.addEventListener("mousemove", throttledMouseMove);
```

In this example, the `handleMouseMove` function is throttled using the `throttle` function. It will only be called once every 100 milliseconds, even if the `mousemove` event is triggered more frequently.

2. **Debouncing**:

Debouncing delays the invocation of a function until after a specific time interval has passed since the last occurrence of the event. It ensures that the function is only called once after the event has stopped firing for the specified time.

Here's an example of debouncing a function that handles user input events:

```javascript
// Debouncing function
function debounce(func, delay) {
	let timeoutId;
	return function (...args) {
		clearTimeout(timeoutId);
		timeoutId = setTimeout(() => {
			func.apply(this, args);
		}, delay);
	};
}

// Example usage
function handleUserInput(event) {
	console.log("Input value:", event.target.value);
}

// Debounce the `handleUserInput` function to execute after 300ms of user input inactivity
const debouncedUserInput = debounce(handleUserInput, 300);

// Add event listener to listen for user input events (e.g., typing in an input field)
document
	.getElementById("inputField")
	.addEventListener("input", debouncedUserInput);
```

In this example, the `handleUserInput` function is debounced using the `debounce` function. It will only be called once after the user has stopped typing for 300 milliseconds.

Throttling and debouncing are powerful techniques that can be useful in various scenarios, such as reducing the number of expensive calculations, optimizing network requests, or improving the performance of UI interactions. The choice between throttling and debouncing depends on the specific use case and the desired behavior for handling events.
