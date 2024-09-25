# WaitHelpers

The `WaitHelpers` class provides various methods for waiting for certain conditions using Selenium WebDriver.

## **Methods**

### ImplicitWaitHandler [:octicons-lock-16:](../../getting-started/conventions.md/#private)

---

Handles the implicit wait for the WebDriver instance.

=== "Method Signature"
	```csharp
	private static void ImplicitWaitHandler(IWebDriver driver, Action action)
	```

=== "Parameters"

	| Name | Type | Description |
	| ---- | ---- | ----------- |
	| `driver` | IWebDriver | The WebDriver instance to use to search for the element. |
	| `action` | Action | The action to perform after setting the implicit wait. |

#### Usage

This method is a private method which is used to wrap around all actions internally in the below methods to set the implicit wait before performing the action and then reset the implicit wait after the action is performed.

=== "WaitForElementToBeVisible"
	```csharp
	ImplicitWaitHandler(driver, () =>
	{
		WebDriverWait wait = new WebDriverWait(driver, TimeSpan.FromSeconds(time));
		wait.Until(ExpectedConditions.ElementIsVisible(element));
	});
	```
=== "WaitForElementToBeClickable"
	```csharp
	ImplicitWaitHandler(driver, () =>
	{
		WebDriverWait wait = new WebDriverWait(driver, TimeSpan.FromSeconds(time));
		wait.Until(ExpectedConditions.ElementToBeClickable(element));
	});
	```

### WaitForElementToBeVisible [:octicons-globe-24:](../../getting-started/conventions.md/#public)

---

Waits for an element to be visible on the page.

=== "Method Signature"
	```csharp
	public static void WaitForElementToBeVisible(IWebDriver driver, By element, int time = 60)
	```

=== "Parameters"

	| Name | Type | Description |
	| ---- | ---- | ----------- |
	| `driver` | IWebDriver | The WebDriver instance to use to search for the element. |
	| `element` | By | The locator for the element to wait for. |
	| `time` | int | The maximum time to wait for the element to be visible. [:octicons-goal-24:](../../getting-started/conventions.md/#default) = 60 seconds. |

#### Usage

=== "With timeout specified"

	```csharp
	WaitForElementToBeVisible(driver, By.Id("elementId"), 10);
	```
=== "Without timeout specified"
	
	```csharp
	WaitForElementToBeVisible(driver, By.Id("elementId")); //defaults to 60 seconds
	```
### WaitForInvisibilityOfElement [:octicons-globe-24:](../../getting-started/conventions.md/#public) [:octicons-skip-24:](../../getting-started/conventions.md/#deprecated)

---

Waits for an element to be invisible on the page.

=== "Method Signature"
	```csharp
	public static void WaitForInvisibilityOfElement(IWebDriver driver, By element, int time = 60)
	```

=== "Parameters"

	| Name | Type | Description |
	| ---- | ---- | ----------- |
	| `driver` | IWebDriver | The WebDriver instance to use to search for the element. |
	| `element` | By | The locator for the element to wait for. |
	| `time` | int | The maximum time to wait for the element to be invisible. [:octicons-goal-24:](../../getting-started/conventions.md/#default) = 60 seconds. |

#### Usage

=== "With timeout specified"

	```csharp
	WaitForInvisibilityOfElement(driver, By.Id("elementId"), 10);
	```
=== "Without timeout specified"
	
	```csharp
	WaitForInvisibilityOfElement(driver, By.Id("elementId")); //defaults to 60 seconds
	```

_Note:This method will be removed in a future version, use [WaitForInvisibilityOfElements](#waitforinvisibilityofelements) instead_

### WaitForElementToBeClickable [:octicons-globe-24:](../../getting-started/conventions.md/#public)

---

Waits for an element to be clickable (checks if element is enabled) on the page.

=== "Method Signature"
	```csharp
	public static void WaitForElementToBeClickable(IWebDriver driver, By element, int time = 60)
	```

=== "Parameters"

	| Name | Type | Description |
	| ---- | ---- | ----------- |
	| `driver` | IWebDriver | The WebDriver instance to use to search for the element. |
	| `element` | By | The locator for the element to wait for. |
	| `time` | int | The maximum time to wait for the element to be clickable. [:octicons-goal-24:](../../getting-started/conventions.md/#default) = 60 seconds. |

#### Usage

=== "With timeout specified"

	```csharp
	WaitForElementToBeClickable(driver, By.Id("elementId"), 10);
	```
=== "Without timeout specified"
	
	```csharp
	WaitForElementToBeClickable(driver, By.Id("elementId")); //defaults to 60 seconds
	```

### WaitForElementToExist [:octicons-globe-24:](../../getting-started/conventions.md/#public)

---

Waits for an element to exist on the page.

=== "Method Signature"
	```csharp
	public static void WaitForElementToExist(IWebDriver driver, By element, int time = 60)
	```

=== "Parameters"

	| Name | Type | Description |
	| ---- | ---- | ----------- |
	| `driver` | IWebDriver | The WebDriver instance to use to search for the element. |
	| `element` | By | The locator for the element to wait for. |
	| `time` | int | The maximum time to wait for the element to exist. [:octicons-goal-24:](../../getting-started/conventions.md/#default) = 60 seconds. |

#### Usage

=== "With timeout specified"

	```csharp
	WaitForElementToExist(driver, By.Id("elementId"), 10);
	```
=== "Without timeout specified"
	
	```csharp
	WaitForElementToExist(driver, By.Id("elementId")); //defaults to 60 seconds
	```

### WaitForInvisibilityOfElements [:octicons-globe-24:](../../getting-started/conventions.md/#public)

---

Waits for all elements matching the locator to be invisible on the page.

=== "Method Signature"
	```csharp
	public static void WaitForInvisibilityOfElements(IWebDriver driver, By element, int t = 80)
	```

=== "Parameters"

	| Name | Type | Description |
	| ---- | ---- | ----------- |
	| `driver` | IWebDriver | The WebDriver instance to use to search for the element. |
	| `element` | By | The locator for the elements to wait for. |
	| `t` | int | The maximum time to wait for the elements to be invisible. [:octicons-goal-24:](../../getting-started/conventions.md/#default) = 80 seconds. |

#### Usage

=== "With timeout specified"

	```csharp
	WaitForInvisibilityOfElements(driver, By.ClassName("elementClass"), 10);
	```
=== "Without timeout specified"
	
	```csharp
	WaitForInvisibilityOfElements(driver, By.ClassName("elementClass")); //defaults to 80 seconds
	```

### WaitForUrlToContain [:octicons-globe-24:](../../getting-started/conventions.md/#public)

---

Waits for the URL to contain the specified string.

=== "Method Signature"
	```csharp
	public static void WaitForUrlToContain(IWebDriver driver, string url, int time = 60)
	```

=== "Parameters"

	| Name | Type | Description |
	| ---- | ---- | ----------- |
	| `driver` | IWebDriver | The WebDriver instance to use to search for the element. |
	| `url` | string | The string to wait for in the URL. |
	| `time` | int | The maximum time to wait for the URL to contain the string. [:octicons-goal-24:](../../getting-started/conventions.md/#default) = 60 seconds. |

#### Usage

=== "With timeout specified"

	```csharp
	WaitForUrlToContain(driver, "example.com", 10);
	```
=== "Without timeout specified"
	
	```csharp
	WaitForUrlToContain(driver, "example.com"); //defaults to 60 seconds
	```

### WaitForNewTab [:octicons-globe-24:](../../getting-started/conventions.md/#public)

---

Waits for a new tab to be opened.

=== "Method Signature"
	```csharp
	public static void WaitForNewTab(IWebDriver driver, int tabCount, int time = 60)
	```

=== "Parameters"

	| Name | Type | Description |
	| ---- | ---- | ----------- |
	| `driver` | IWebDriver | The WebDriver instance to use to search for the element. |
	| `tabCount` | int | Initial number of tabs before performing an action that presumably opens a new tab. |
	| `time` | int | The maximum time to wait for a new tab to be opened. [:octicons-goal-24:](../../getting-started/conventions.md/#default) = 60 seconds. |

#### Usage

=== "With timeout specified"

	```csharp
	WaitForNewTab(driver, 1, 10);
	```
=== "Without timeout specified"
	
	```csharp
	WaitForNewTab(driver, 1); //defaults to 60 seconds
	```

### WaitForTabClose [:octicons-globe-24:](../../getting-started/conventions.md/#public)

---

Waits for a tab to be closed.

=== "Method Signature"
	```csharp
	public static void WaitForTabClose(IWebDriver driver, int tabCount, int time = 60)
	```

=== "Parameters"

	| Name | Type | Description |
	| ---- | ---- | ----------- |
	| `driver` | IWebDriver | The WebDriver instance to use to search for the element. |
	| `tabCount` | int | Initial number of tabs before performing an action that presumably closes a tab. |
	| `time` | int | The maximum time to wait for a tab to be closed. [:octicons-goal-24:](../../getting-started/conventions.md/#default) = 60 seconds. |

#### Usage

=== "With timeout specified"

	```csharp
	WaitForTabClose(driver, 2, 10);
	```

=== "Without timeout specified"
	
	```csharp
	WaitForTabClose(driver, 2); //defaults to 60 seconds
	```

### WaitForFileDownload [:octicons-globe-24:](../../getting-started/conventions.md/#public)

---

Waits for a file to be downloaded.

=== "Method Signature"
	```csharp
	public static void WaitForFileDownload(IWebDriver driver, string downloadPath, int initialFileCount, int time = 60)
	```

=== "Parameters"

	| Name | Type | Description |
	| ---- | ---- | ----------- |
	| `driver` | IWebDriver | The WebDriver instance to use to search for the element. |
	| `downloadPath` | string | The path where the file is expected to be downloaded. |
	| `initialFileCount` | int | Initial number of files in the download path before performing an action that presumably downloads a file. |
	| `time` | int | The maximum time to wait for a file to be downloaded. [:octicons-goal-24:](../../getting-started/conventions.md/#default) = 60 seconds. |

#### Usage

=== "With timeout specified"

	```csharp
	WaitForFileDownload(driver, "C:\\Downloads", 0, 10);
	```

=== "Without timeout specified"
	
	```csharp
	WaitForFileDownload(driver, "C:\\Downloads", 0); //defaults to 60 seconds
	```

### WaitForAnyElementToBeVisible [:octicons-globe-24:](../../getting-started/conventions.md/#public)

---

Waits for any elements identified with the given locator to be visible on the page.
_Note: Used only when there are multiple matching elements with the given locator, and we have to wait for an element whose index isn't 1 to be visible._

=== "Method Signature"
	```csharp
	public static void WaitForAnyElementToBeVisible(IWebDriver driver, By element, int time = 60)
	```

=== "Parameters"

	| Name | Type | Description |
	| ---- | ---- | ----------- |
	| `driver` | IWebDriver | The WebDriver instance to use to search for the element. |
	| `element` | By | The locator for the element to wait for. |
	| `time` | int | The maximum time to wait for the element to be visible. [:octicons-goal-24:](../../getting-started/conventions.md/#default) = 60 seconds. |

#### Usage

=== "With timeout specified"

	```csharp
	WaitForAnyElementToBeVisible(driver, By.ClassName("elementClass"), 10);
	```

=== "Without timeout specified"
	
	```csharp
	WaitForAnyElementToBeVisible(driver, By.ClassName("elementClass")); //defaults to 60 seconds
	```

### WaitForNoPendingRequests [:octicons-globe-24:](../../getting-started/conventions.md/#public) [:octicons-skip-24:](../../getting-started/conventions.md/#deprecated)

---

Waits for all pending network requests to complete.


=== "Method Signature"
	```csharp
	public static void WaitForNoPendingRequests(IWebDriver driver, int time)
	```

=== "Parameters"

	| Name | Type | Description |
	| ---- | ---- | ----------- |
	| `driver` | IWebDriver | The WebDriver instance to use to search for the element. |
	| `time` | int | The maximum time to wait for all pending network requests to complete. |

#### Usage

=== "Example"
	```csharp
	WaitForNoPendingRequests(driver, 60);
	```
_Note: This method doesn't work in [Onblick2.0](https://www.onblick.com){:target=_blank} as there are always pending signalr calls, so it is unused for now._

