# WebElementExtensions

`WebElementExtensions` is a collection of extension methods for Selenium's IWebElement interface. It is designed to make it easier to work with Selenium's IWebElement interface by providing a set of extension methods that make it easier to interact with elements on a page.

## **Methods**

### GetDriverFromElement [:fontawesome-solid-lock:](../../Getting%20Started/conventions.md/#private)

The `GetDriverFromElement` method is a private method used in almost all the methods in this class to get the WebDriver instance from an IWebElement object.

=== "Method Signature"
	```csharp
	private static IWebDriver GetDriverFromElement(this IWebElement element)
	```

=== "Parameters"
	
	| Name | Type | Description |
	| ---- | ---- | ----------- |
	| `element` | IWebElement | The element to get the driver from. |

=== "Return Value"

	The method returns the WebDriver instance associated with the element.


### GetInterceptingElement [:fontawesome-solid-lock:](../../Getting%20Started/conventions.md/#private)

`GetInterceptingElement` is a private method used in [`IClick`](#iclick) which extracts the identifier of the element that is intercepting the click from an exception message.

=== "Method Signature"
	```csharp
	private static string GetInterceptingElement(Exception ex)
	```
=== "Parameters"

	| Name | Type | Description |
	| ---- | ---- | ----------- |
	| `ex` | Exception | The exception thrown when the click is intercepted. |

=== "Return Value"

	The method returns the identifier of the element that is intercepting the click.


### MoveInterceptingElement [:fontawesome-solid-lock:](../../Getting%20Started/conventions.md/#private)

The `MoveInterceptingElement` method is an extension method that moves an intercepting element out of the way. It is used in the [`IClick`](#iclick) method to move draggable elements that are obstructing the click.

=== "Method Signature"
	```csharp
	private static void MoveInterceptingElement(this IWebElement interceptingElement, IWebDriver driver)
	```
=== "Parameters"

	| Name | Type | Description |
	| ---- | ---- | ----------- |
	| `interceptingElement` | IWebElement | The element that is obstructing the click. |

### IClick [:fontawesome-solid-globe:](../../Getting%20Started/conventions.md/#public)

----

The `IClick` method is an extension method that clicks on an element. It is equivalent to calling the `Click` method on an IWebElement object. `IClick` - **Interception Click** handler that manages intercepted exceptions.

=== "Method Signature"
	```csharp
	public static void IClick(this IWebElement element)
	```

=== "Parameters"

	| Name | Type | Description |
	| ---- | ---- | ----------- |
	| `element` | IWebElement | The element to click on. |

=== "Functionality"

	1. **Retries**: The method attempts to click the element up to 5 times (`maxRetries`), incrementing the retry count with each attempt.
	1. **Exception Handling**:
		- Catches `ElementClickInterceptedException` when the click is obstructed.
		- Identifies the intercepting element using [GetInterceptingElement](#getinterceptingelement) and takes specific actions based on its type:
			- **Modal Frames**: Switches to the modal frame and clicks the close button.
			- **IFrames: **Clicks the close button for the iframe.
			- **Overlay Elements**: Clicks on an overlay close button.
			- **Draggable Elements**: Moves the intercepting element out of the way using [MoveInterceptingElement](#moveinterceptingelement), retrying if necessary.
			- **Scrollable Elements**: Scrolls the calendar or similar elements to the left.
	1. **Error Handling**: If the maximum number of retries is exceeded, the exception is re-thrown to be handled elsewhere.
	1. **Scroll Handling**: Ensures the element is in view before attempting the click by scrolling to it if necessary.


=== "Usage"
	```csharp
	IWebElement element = driver.FindElement(By.Id("elementId"));
	element.IClick();
	```

### ScrollToTheLeft [:fontawesome-solid-globe:](../../Getting%20Started/conventions.md/#public) [:fontawesome-solid-flask:](../../Getting%20Started/conventions.md/#experimental)

---

The `ScrollToTheLeft` method is used to scroll to the leftmost of the page within the scrollable element on the webpage.

=== "Method Signature"
	```csharp
	public static void ScrollToTheLeft(this IWebElement element, IWebDriver driver)
	```

=== "Parameters"

	| Name | Type | Description |
	| ---- | ---- | ----------- |
	| `element` | IWebElement | The element to scroll. |

=== "Usage"
	```csharp
	IWebElement element = driver.FindElement(By.Id("elementId"));
	element.ScrollToTheLeft();
	```

### ScrollToTheRight [:fontawesome-solid-globe:](../../Getting%20Started/conventions.md/#public) [:fontawesome-solid-flask:](../../Getting%20Started/conventions.md/#experimental)

---

The `ScrollToTheRight` method is used to scroll to the rightmost of the page within the scrollable element on the webpage.

=== "Method Signature"
	```csharp
	public static void ScrollToTheRight(this IWebElement element)
	```

=== "Parameters"

	| Name | Type | Description |
	| ---- | ---- | ----------- |
	| `element` | IWebElement | The element to scroll. |


=== "Usage"
	```csharp
	IWebElement element = driver.FindElement(By.Id("elementId"));
	element.ScrollToTheRight();
	```

### IGetHexColor [:fontawesome-solid-globe:](../../Getting%20Started/conventions.md/#public)

---

The `IGetHexColor` method is an extension method that retrieves the hex color of the element. It is equivalent to calling the `GetCssValue` method on an IWebElement object. It has two overload methods, one that returns the hex color as a string and another that validates the hex color with an expected value.

=== "Method Signature 1"
	```csharp
	public static string IGetHexColor(this IWebElement element, string colorLocator)
	```
=== "Method Signature 2"
	```csharp
	public static void IGetHexColor(this IWebElement element, string colorLocator, string expectedHex)
	```

=== "Parameters"
	
	`expectedHex` is only in the second method signature.
	
	| Name | Type | Description |
	| ---- | ---- | ----------- |
	| `element` | IWebElement | The element to get the color from. |
	| `colorLocator` | string | The CSS locator for the color. |
	| `expectedHex` | string | The expected hex color value. |

=== "Functionality"

	1. **Get Color**: Retrieves the color of the element using the CSS locator.
	1. **Hex Conversion**: Converts the color to a hex value.
	1. **Validation**: Compares the hex value with the expected hex value if provided.

=== "Usage 1"
	```csharp
	IWebElement element = driver.FindElement(By.Id("elementId"));
	string hexColor = element.IGetHexColor("color");
	```

=== "Usage 2"
	```csharp
	IWebElement element = driver.FindElement(By.Id("elementId"));
	element.IGetHexColor("color", "#000000");
	```

### Highlight [:fontawesome-solid-globe:](../../Getting%20Started/conventions.md/#public)

---

The `Highlight` method is an extension method that highlights an element on the page. It is used to visually identify the element on the page.

=== "Method Signature"
	```csharp
	public static void Highlight(this IWebElement element)
	```

=== "Parameters"

	| Name | Type | Description |
	| ---- | ---- | ----------- |
	| `element` | IWebElement | The element to highlight. |

=== "Functionality"

	1. **JavaScript Execution**: Executes a JavaScript script to highlight the element.
	1. **Styling**: Applies a red border around the element to highlight it.

=== "Usage"
	```csharp
	IWebElement element = driver.FindElement(By.Id("elementId"));
	element.Highlight();
	```

### Unhighlight [:fontawesome-solid-globe:](../../Getting%20Started/conventions.md/#public)

---

The `Unhighlight` method is an extension method that removes the highlight from an element on the page. It is used to remove the visual identification of the element.

=== "Method Signature"
	```csharp
	public static void Unhighlight(this IWebElement element)
	```

=== "Parameters"

	| Name | Type | Description |
	| ---- | ---- | ----------- |
	| `element` | IWebElement | The element to unhighlight. |

=== "Functionality"

	1. **JavaScript Execution**: Executes a JavaScript script to remove the highlight from the element.
	1. **Styling**: Removes the red border around the element.

=== "Usage"
	```csharp
	IWebElement element = driver.FindElement(By.Id("elementId"));
	element.Unhighlight();
	```

### ScrollTo [:fontawesome-solid-globe:](../../Getting%20Started/conventions.md/#public)

---

The `ScrollTo` method is an extension method that scrolls to an element on the page. It is used to bring the element into view.

=== "Method Signature"
	```csharp
	public static void ScrollTo(this IWebElement element)
	```

=== "Parameters"

	| Name | Type | Description |
	| ---- | ---- | ----------- |
	| `element` | IWebElement | The element to scroll to. |

=== "Functionality"

	1. **JavaScript Execution**: Executes a JavaScript script to scroll to the element.
	1. **Scrolling**: Scrolls the page to bring the element into view.


=== "Usage"
	```csharp
	IWebElement element = driver.FindElement(By.Id("elementId"));
	element.ScrollTo();
	```

### Scroll [:fontawesome-solid-globe:](../../Getting%20Started/conventions.md/#public)

---

The `Scroll` method is an extension method that scrolls the page by a specified number of pixels. It is used to scroll the page up or down by a specific amount.

=== "Method Signature"
	```csharp
	public static void Scroll(this IWebElement element, string direction, int distance)
	```

=== "Parameters"

	| Name | Type | Description |
	| ---- | ---- | ----------- |
	| `element` | IWebElement | The element to scroll. |
	| `direction` | string | The direction to scroll in (`up` or `down`). |
	| `distance` | int | The number of pixels to scroll by. |

=== "Functionality"

	1. **JavaScript Execution**: Executes a JavaScript script to scroll the page.
	1. **Scrolling**: Scrolls the page up or down by the specified number of pixels.
	1. **Direction**: Determines the direction of the scroll based on the input parameter.

=== "Usage"
	```csharp
	IWebElement element = driver.FindElement(By.Id("elementId"));
	element.Scroll("down", 500);
	```

=== "Example 2"
	```csharp
	IWebElement element = driver.FindElement(By.Id("elementId"));
	element.Scroll("up", 500);
	```

### DateEntry [:fontawesome-solid-globe:](../../Getting%20Started/conventions.md/#public)

---

The `DateEntry` method is an extension method that enters a date into a date picker element. It is used to automate the entry of dates into date picker elements.

=== "Method Signature"
	```csharp
	public static void DateEntry(this IWebElement element, string date)
	```

=== "Parameters"

	| Name | Type | Description |
	| ---- | ---- | ----------- |
	| `element` | IWebElement | The date picker element. |
	| `date` | string | The date to enter in the format `MM/dd/yyyy`. |

=== "Functionality"

	1. **JavaScript Execution**: Executes a JavaScript script to enter the date into the date picker.
	1. **Date Entry**: Enters the date into the date picker element.
	1. **Date Format**: The date should be in the format `MM/dd/yyyy`.

=== "Usage"
	```csharp
	IWebElement element = driver.FindElement(By.Id("elementId"));
	element.DateEntry("12/31/2022");
	```

### ClearAndEnter [:fontawesome-solid-globe:](../../Getting%20Started/conventions.md/#public) [:fontawesome-solid-flask:](../../Getting%20Started/conventions.md/#experimental)

---

The `ClearAndEnter` method is an extension method that clears the existing text in an input field and enters new text. It is used to automate the clearing and entering of text into input fields.

=== "Method Signature"
	```csharp
	public static void ClearAndEnter(this IWebElement element, string text)
	```

=== "Parameters"

	| Name | Type | Description |
	| ---- | ---- | ----------- |
	| `element` | IWebElement | The input field element. |
	| `text` | string | The text to enter into the input field. |

=== "Functionality"

	1. **Clearing**: Clears the existing text in the input field.
	1. **Entering**: Enters the new text into the input field.

=== "Usage"
	```csharp
	IWebElement element = driver.FindElement(By.Id("elementId"));
	element.ClearAndEnter("Text to enter");
	```

### ClickLeft [:fontawesome-solid-globe:](../../Getting%20Started/conventions.md/#public)

---

The `ClickLeft` method is an extension method that clicks on the left side of an element. It is used to simulate a click on the left side of an element.

=== "Method Signature"
	```csharp
	public static void ClickLeft(this IWebElement element, int percentage)
	```

=== "Parameters"

	| Name | Type | Description |
	| ---- | ---- | ----------- |
	| `element` | IWebElement | The element to click on. |
	| `percentage` | int | The percentage of the element's width to click on. |

=== "Functionality"

	1. **Actions**: Creates an Actions object to perform the click action.
	1. **Click Location**: Simulates a click on the left side of the element.
	1. **Percentage**: Determines the location of the click based on the percentage of the element's width.

=== "Usage"
	```csharp
	IWebElement element = driver.FindElement(By.Id("elementId"));
	element.ClickLeft(20);
	```

### Hover [:fontawesome-solid-globe:](../../Getting%20Started/conventions.md/#public)

---

The `Hover` method is an extension method that hovers over an element. It is used to simulate a mouse hover action on an element.

=== "Method Signature"
	```csharp
	public static void Hover(this IWebElement element)
	```

=== "Parameters"

	| Name | Type | Description |
	| ---- | ---- | ----------- |
	| `element` | IWebElement | The element to hover over. |

=== "Functionality"

	1. **Actions**: Creates an Actions object to perform the hover action.
	1. **Hovering**: Hovers over the element.

=== "Usage"
	```csharp
	IWebElement element = driver.FindElement(By.Id("elementId"));
	element.Hover();
	```

### CtrlClick [:fontawesome-solid-globe:](../../Getting%20Started/conventions.md/#public)

---

The `CtrlClick` method is an extension method that performs a Ctrl+Click action on an element. It is used to simulate a Ctrl+Click action on an element which opens the hyperlink of an element in a new tab.

=== "Method Signature"
	```csharp
	public static void CtrlClick(this IWebElement element)
	```

=== "Parameters"

	| Name | Type | Description |
	| ---- | ---- | ----------- |
	| `element` | IWebElement | The element to Ctrl+Click on. |

=== "Functionality"

	1. **Actions**: Creates an Actions object to perform the Ctrl+Click action.
	1. **Ctrl+Click**: Performs the Ctrl+Click action on the element.
	1. **New Tab**: Opens the hyperlink of the element in a new tab.

=== "Usage"
	```csharp
	IWebElement element = driver.FindElement(By.Id("elementId"));
	element.CtrlClick();
	```
