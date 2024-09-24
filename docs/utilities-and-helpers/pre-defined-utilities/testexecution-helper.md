# TestExecutionHelper

This abstract class is used to help with the execution of tests. It inherits [`ReportsGenerationClass`](./reports-generation-class.md) and in turn is inherited by all test classes. It provides a method to execute a test step and automatically log the result of the test step to both console and the report generated by [`ReportsGenerationClass`](./reports-generation-class.md).

Below are the members of this class:

## **Classes**

### NodeDetails [:fontawesome-solid-globe:](../../getting-started/conventions.md/#public)

---

Represents the details of a node, including its name, step details, parent node name, and child relationships.

=== "Class Definition"

	```csharp
	public class NodeDetails(string nodeName, string stepDetails, string parentNodeName = null, bool hasChild = false, bool isChild = false)
    {
        public string NodeName { get; set; } = nodeName;
        public string StepDetails { get; set; } = stepDetails;
        public string ParentNodeName { get; set; } = parentNodeName;
        public bool HasChild { get; set; } = hasChild;
        public bool IsChild { get; set; } = isChild;
    }
	```

=== "Parameters"

	| Name | Type | Description |
	| --- | --- | --- |
	| `nodeName` | string | The name of the node. |
	| `stepDetails` | string | The details of the step associated with the node. |
	| `parentNodeName` | string, optional | The name of the parent node, if any. Default is `null`. |
	| `hasChild` | bool, optional | A value indicating whether the node has child nodes. Default is `false`. |
	| `isChild` | bool, optional | A value indicating whether the node is a child node. Default is `false`. |

=== "Properties"

	| Name | Type | Description |
	| --- | --- | --- |
	| `NodeName` | string | Gets or sets the name of the node. |
	| `StepDetails` | string | Gets or sets the details of the step associated with the node. |
	| `ParentNodeName` | string | Gets or sets the name of the parent node, if any. Default is `null`. |
	| `HasChild` | bool | Gets or sets a value indicating whether the node has child nodes. Default is `false`. |
	| `IsChild` | bool | Gets or sets a value indicating whether the node is a child node. Default is `false`. |

#### Usage

The following code snippet demonstrates how to use the `NodeDetails` class:

=== "Example 1"
	```csharp
	NodeDetails nodeDetails = new NodeDetails
	(
		nodeName: "Node1",
		stepDetails: "Details for Step1",
		parentNodeName: "ParentNode",
		hasChild: true,
		isChild: false
	);
	```
=== "Example 2"
	```csharp
	NodeDetails nodeDetails = new NodeDetails
	(
		nodeName: "Node2",
		stepDetails: "Details for Step2"
	);
	```

---

## **Methods**

### ExecuteStep (without dictionary) [:fontawesome-solid-globe:](../../getting-started/conventions.md/#public) [:fontawesome-solid-ban:](../../getting-started/conventions.md/#deprecated)

---

This method is used to execute a test step and log the result of the test step to both console and the report generated by [`ReportsGenerationClass`](./reports-generation-class.md).

=== "Method Signature"

	```csharp
	public void ExecuteStep(Action stepAction, string stepName, string stepDetails)
	```

=== "Parameters"

	| Name | Type | Description |
	| --- | --- | --- |
	| `stepAction` | Action | The action to be executed in the test step. |
	| `stepName` | string | The name of the test step to be executed and logged to the report. |
	| `stepDetails` | string | The details of the test step to be logged to the current node in the report. |

=== "Functionality"

	1. **Log Step Start**:
		- Logs the start of the step using [`LogSubstep`](./reports-generation-class.md/#logsubstep).
		- Retrieves the current time in the "India Standard Time" timezone and logs the start time with the step name and details.
	1. **Execute Action**:
		- Executes the `stepAction` delegate.
	1. **Log Step Completion**:
		- If `stepDetails` is empty, assigns a default completion message.
		- Logs the completion of the step using [`LogSubstep`](./reports-generation-class.md/#logsubstep).
		- Retrieves the current time in the "India Standard Time" timezone and logs the end time with the step name and details.
	1. **Exception Handling**:
		- Catches any exceptions thrown during the execution of the `stepAction`.
		- Initializes exception details using [`InitializeExceptionDetails`](./shared-failure-context.md/#initializeexceptiondetails).
		- Logs the failure of the step using [`LogSubstep`](./reports-generation-class.md/#logsubstep) with `Status.Fail`.
		- Captures network calls using [`GetNetworkCalls`](./reports-generation-class.md/#getnetworkcalls).
		- Resets substeps using [`ResetSubsteps`](./reports-generation-class.md/#resetsubsteps).
		- Rethrows the exception using `ExceptionDispatchInfo.Capture(ex).Throw()`.

#### Usage

Say `MyClass.MyMethod()` is the action to be executed in the test step. The following code snippet demonstrates how to use the `ExecuteStep` method:

=== "Example"
```csharp
ExecuteStep(() => MyClass.MyMethod(),
			stepName: "MyMethod",
			stepDetails: "Demonstrates the usage of ExecuteStep method.");
```

### ExecuteStep [:fontawesome-solid-globe:](../../getting-started/conventions.md/#public)

---

This method is used to execute a test step and log the result of the test step to both console and the report generated by [`ReportsGenerationClass`](./reports-generation-class.md). An overload to the previous method taking a dictionary of string and [`NodeDetails`](#nodedetails) parameter to log subsequent steps as skipped after a test fails before completion.

=== "Method Signature"

	```csharp
	public void ExecuteStep(Action stepAction, string stepKey, Dictionary<string, NodeDetails> stepInfo)
	```

=== "Parameters"

	| Name | Type | Description |
	| --- | --- | --- |
	| `stepAction` | Action | The action to be executed in the test step. |
	| `stepKey` | string | The key to be used to log the test step in the report. |
	| `stepInfo` | Dictionary<string, NodeDetails> | The dictionary of all steps to be logged in the report. |

=== "Functionality"

	1. **Retrieve Step Information**:
		- Attempts to retrieve [`NodeDetails`](#nodedetails) for the given `stepKey` from the `stepInfo` dictionary.
		- Throws a `KeyNotFoundException` if the `stepKey` is not found.
	1. **Extract Step Details**:
		- Extracts `stepName`, `stepDetails`, `parentStepName`, `hasChild`, and `isChild` from the retrieved `NodeDetails`.
		- Determines the `currentNodeName` based on whether the step is a child.
	1. **Log Step Start**:
		- Logs the start of the step using [`LogSubstep`](./reports-generation-class.md/#logsubstep).
		- Retrieves the current time in the "India Standard Time" timezone and logs the start time with the step name and details.
	1. **Execute Action**:
		- Executes the `stepAction` delegate.
	1. **Log Step Completion**:
		- If `stepDetails` is empty, assigns a default completion message.
		- Logs the completion of the step using [`LogSubstep`](./reports-generation-class.md/#logsubstep).
		- Removes the completed step from the `stepInfo` dictionary using [`RemoveStep`](#removestep).
		- Retrieves the current time in the "India Standard Time" timezone and logs the end time with the step name and details.
	1. **Exception Handling**:
		- Catches any exceptions thrown during the execution of the `stepAction`.
		- Initializes exception details using [`InitializeExceptionDetails`](./shared-failure-context.md/#initializeexceptiondetails).
		- Logs the failure of the step using [`LogSubstep`](./reports-generation-class.md/#logsubstep) with `Status.Fail`.
		- Removes the failed step from the `stepInfo` dictionary using [`RemoveStep`](#removestep).
		- Logs the skipping of remaining steps using LogSubstep with `Status.Skip`.
		- Captures network calls using [`GetNetworkCalls`](./reports-generation-class.md/#getnetworkcalls).
		- Resets substeps using [`ResetSubsteps`](./reports-generation-class.md/#resetsubsteps).
		- Rethrows the exception using `ExceptionDispatchInfo.Capture(ex).Throw()`.

#### Usage

Say MyClass.MyMethod() is the action to be executed in the test step. The following code snippet demonstrates how to use the `ExecuteStep` method:

=== "Example"
```csharp
Dictionary<string, NodeDetails> stepInfo = new Dictionary<string, NodeDetails>
{
	{ "Step1", new NodeDetails { NodeName = "Step1", StepDetails = "Details for Step1" } },
	{ "Step2", new NodeDetails { NodeName = "Step2", StepDetails = "Details for Step2" } }
};

ExecuteStep(() => MyClass.MyMethod(),
			stepKey: "Step1",
			stepInfo: stepInfo);
```

### ExecuteStepAndSuppress [:fontawesome-solid-globe:](../../getting-started/conventions.md/#public)

---

This method is used to execute a test step and log the result of the test step to both console and the report generated by [`ReportsGenerationClass`](./reports-generation-class.md). It suppresses the exception thrown during the execution of the test step and continues with the execution of the subsequent steps.

=== "Method Signature"

	```csharp
	public void ExecuteStepAndSuppress(Action stepAction, string stepName, string stepDetails = null)
	```

=== "Parameters"

	| Name | Type | Description|
	| --- | --- | --- |
	| `stepAction` | Action | The action to be executed in the test step. |
	| `stepName` | string | The name of the test step to be executed and logged to the report. |
	| `stepDetails` | string | The details of the test step to be logged to the current node in the report. Default is `null`. |

=== "Functionality"

	1. **Log Step Start**:
		- Logs the start of the step using [`LogSubstep`](./reports-generation-class.md/#logsubstep).
		- Retrieves the current time in the "India Standard Time" timezone and logs the start time with the step name and details.
	1. **Execute Action**:
		- Executes the `stepAction` delegate.
	1. **Log Step Completion**:
		- If `stepDetails` is empty, logs a default completion message using [`LogSubstep`](./reports-generation-class.md/#logsubstep).
		- Otherwise, logs the provided `stepDetails` using [`LogSubstep`](./reports-generation-class.md/#logsubstep).
	1. **Exception Handling (Suppression)**:
		- Catches any exceptions thrown during the execution of the `stepAction`.
		- Captures network calls using [`GetNetworkCalls`](./reports-generation-class.md/#getnetworkcalls) with `stepName`.
		- Initializes exception details using [`InitializeExceptionDetails`](./shared-failure-context.md/#initializeexceptiondetails).
		- Logs the failure of the step using LogSubstep with `Status.Skip`.
		- Logs detailed failure information, including the failed method name, exception message, and stack trace, using [`LogSubstep`](./reports-generation-class.md/#logsubstep) with `Status.Skip`.
		- Resets exception details using [`ResetExceptionDetails`](./shared-failure-context.md/#resetexceptiondetails).
	1. **Log Step End**:
		- Retrieves the current time in the "India Standard Time" timezone and logs the end time with the step name and details.

#### Usage

Say MyClass.MyMethod() is the action to be executed in the test step. The following code snippet demonstrates how to use the `ExecuteStepAndSuppress` method:

=== "Example"
```csharp
ExecuteStepAndSuppress(() => MyClass.MyMethod(),
						stepName: "MyMethod",
						stepDetails: "Demonstrates the usage of ExecuteStepAndSuppress method.");
```

### RemoveStep [:fontawesome-solid-globe:](../../getting-started/conventions.md/#public)

---

This method is used to remove a step from the dictionary of steps to be logged in the report.

=== "Method Signature"

	```csharp
	public void RemoveStep(string stepKey, Dictionary<string, NodeDetails> stepInfo)
	```

=== "Parameters"

	| Name | Type | Description |
	| --- | --- | --- |
	| `stepKey` | string | The key of the step to be removed from the dictionary of steps to be logged in the report. |
	| `stepInfo` | Dictionary<string, NodeDetails> | The dictionary of all steps to be logged in the report. |

=== "Functionality"
	1. **Find Step to Remove**:
		- Retrieves the step to remove from the `stepInfo` dictionary based on the provided `stepKey`.
		- Uses `FirstOrDefault` to find the matching key-value pair.
	1. **Remove Step if No Children**:
		- If the step to remove is found and it has no children (`HasChild` is false), it removes the step from the `stepInfo` dictionary.
	1. **Check for Orphaned Parent**:
		- Counts the number of sibling steps for the parent node of the step being removed.
		- If there are no sibling steps and the step being removed is a child (`IsChild` is true), it attempts to remove the parent step from the `stepInfo` dictionary.

#### Usage

The following code snippet demonstrates how to use the `RemoveStep` method:

=== "Example"

	```csharp
	Dictionary<string, NodeDetails> stepInfo = new Dictionary<string, NodeDetails>
	{
		{ "step1", new NodeDetails { NodeName = "Step1", StepDetails = "Detail1", ParentNodeName = null, HasChild = true, IsChild = false } },
		{ "step2", new NodeDetails { NodeName = "Step2", StepDetails = "Detail2", ParentNodeName = "Step1", HasChild = false, IsChild = true } },
		// Add more steps as needed
	};

	RemoveStep("step2", stepInfo);
	```