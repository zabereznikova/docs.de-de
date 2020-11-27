---
title: Aufrufen der Aktivitätsvalidierung
ms.date: 03/30/2017
ms.assetid: 22bef766-c505-4fd4-ac0f-7b363b238969
ms.openlocfilehash: 95e6b22fe9814133df080b1faadcc4be32b60bf9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279804"
---
# <a name="invoking-activity-validation"></a><span data-ttu-id="37abc-102">Aufrufen der Aktivitätsvalidierung</span><span class="sxs-lookup"><span data-stu-id="37abc-102">Invoking Activity Validation</span></span>

<span data-ttu-id="37abc-103">Die Aktivitätsvalidierung stellt eine Methode bereit, um Fehler in der Konfiguration einer Aktivität vor der Ausführung zu identifizieren und zu melden.</span><span class="sxs-lookup"><span data-stu-id="37abc-103">Activity validation provides a method to identify and report errors in any activity’s configuration prior to its execution.</span></span> <span data-ttu-id="37abc-104">Eine Validierung wird ausgeführt, wenn ein Workflow im Workflow-Designer geändert und Validierungsfehler oder -warnungen im Workflow-Designer angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="37abc-104">Validation occurs when a workflow is modified in the workflow designer and any validation errors or warnings are displayed in the workflow designer.</span></span> <span data-ttu-id="37abc-105">Die Validierung findet auch zur Laufzeit statt, wenn ein Workflow aufgerufen wird. Wenn Validierungsfehler auftreten, löst die Standardvalidierungslogik eine <xref:System.Activities.InvalidWorkflowException> aus.</span><span class="sxs-lookup"><span data-stu-id="37abc-105">Validation also occurs at run time when a workflow is invoked and if any validation errors occur, an <xref:System.Activities.InvalidWorkflowException> is thrown by the default validation logic.</span></span> <span data-ttu-id="37abc-106">Windows Workflow Foundation (WF) stellt die <xref:System.Activities.Validation.ActivityValidationServices> -Klasse bereit, die von Workflow Anwendungen und Tool Entwicklern verwendet werden kann, um eine Aktivität explizit zu validieren.</span><span class="sxs-lookup"><span data-stu-id="37abc-106">Windows Workflow Foundation (WF) provides the <xref:System.Activities.Validation.ActivityValidationServices> class that can be used by workflow application and tooling developers to explicitly validate an activity.</span></span> <span data-ttu-id="37abc-107">In diesem Thema wird beschrieben, wie Aktivitäten mit dem <xref:System.Activities.Validation.ActivityValidationServices>-Objekt validiert werden.</span><span class="sxs-lookup"><span data-stu-id="37abc-107">This topic describes how to use <xref:System.Activities.Validation.ActivityValidationServices> to perform activity validation.</span></span>  
  
## <a name="using-activityvalidationservices"></a><span data-ttu-id="37abc-108">Verwenden von ActivityValidationServices</span><span class="sxs-lookup"><span data-stu-id="37abc-108">Using ActivityValidationServices</span></span>  

 <span data-ttu-id="37abc-109">Das <xref:System.Activities.Validation.ActivityValidationServices>-Objekt verfügt über zwei <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>-Überladungen, mit denen die Validierungslogik einer Aktivität aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="37abc-109"><xref:System.Activities.Validation.ActivityValidationServices> has two <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> overloads that are used to invoke an activity’s validation logic.</span></span> <span data-ttu-id="37abc-110">Die erste Überladung akzeptiert die Stammaktivität, die validiert werden soll, und gibt eine Auflistung von Validierungsfehlern und -warnungen zurück.</span><span class="sxs-lookup"><span data-stu-id="37abc-110">The first overload takes the root activity to be validated and returns a collection of validation errors and warnings.</span></span> <span data-ttu-id="37abc-111">Im folgenden Beispiel wird eine benutzerdefinierte `Add`-Aktivität verwendet, die über zwei erforderliche Argumente verfügt.</span><span class="sxs-lookup"><span data-stu-id="37abc-111">In the following example, a custom `Add` activity is used that has two required arguments.</span></span>  
  
```csharp  
public sealed class Add : CodeActivity<int>  
{  
    [RequiredArgument]  
    public InArgument<int> Operand1 { get; set; }  
  
    [RequiredArgument]  
    public InArgument<int> Operand2 { get; set; }  
  
    protected override int Execute(CodeActivityContext context)  
    {  
        return Operand1.Get(context) + Operand2.Get(context);  
    }  
}  
```  
  
 <span data-ttu-id="37abc-112">Die `Add`-Aktivität wird in einem <xref:System.Activities.Statements.Sequence>-Objekt verwendet, die zwei erforderlichen Argumente werden jedoch nicht gebunden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="37abc-112">The `Add` activity is used inside a <xref:System.Activities.Statements.Sequence>, but its two required arguments are not bound, as shown in the following example.</span></span>  
  
```csharp  
Variable<int> Operand1 = new Variable<int>{ Default = 10 };  
Variable<int> Operand2 = new Variable<int>{ Default = 15 };  
Variable<int> Result = new Variable<int>();  
  
Activity wf = new Sequence  
{  
    Variables = { Operand1, Operand2, Result },  
    Activities =
    {  
        new Add(),  
        new WriteLine  
        {  
            Text = new InArgument<string>(env => "The result is " + Result.Get(env))  
        }  
    }  
};  
```  
  
 <span data-ttu-id="37abc-113">Dieser Workflow kann durch Aufrufen von <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="37abc-113">This workflow can be validated by calling <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>.</span></span> <span data-ttu-id="37abc-114"><xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> gibt eine Auflistung aller Validierungsfehler und -warnungen zurück, die in der Aktivität selbst oder in ihren untergeordneten Elementen enthalten sind, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="37abc-114"><xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> returns a collection of any validation errors or warnings contained by the activity and any children, as shown in the following example.</span></span>  
  
```csharp  
ValidationResults results = ActivityValidationServices.Validate(wf);  
  
if (results.Errors.Count == 0 && results.Warnings.Count == 0)  
{  
    Console.WriteLine("No warnings or errors");  
}  
else  
{  
    foreach (ValidationError error in results.Errors)  
    {  
        Console.WriteLine("Error: {0}", error.Message);  
    }  
    foreach (ValidationError warning in results.Warnings)  
    {  
        Console.WriteLine("Warning: {0}", warning.Message);  
    }  
}  
```  
  
 <span data-ttu-id="37abc-115">Wenn <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> für diesen Beispielworkflow aufgerufen wird, werden zwei Validierungsfehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="37abc-115">When <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> is called on this sample workflow, two validation errors are returned.</span></span>  
  
 <span data-ttu-id="37abc-116">**Fehler: Für das erforderliche Aktivitätsargument „Operand2“ wurde kein Wert angegeben.**</span><span class="sxs-lookup"><span data-stu-id="37abc-116">**Error: Value for a required activity argument 'Operand2' was not supplied.**</span></span>  
<span data-ttu-id="37abc-117">**Fehler: der Wert für das erforderliche Aktivitäts Argument "Operand1" wurde nicht angegeben.**</span><span class="sxs-lookup"><span data-stu-id="37abc-117">**Error: Value for a required activity argument 'Operand1' was not supplied.**</span></span>  <span data-ttu-id="37abc-118">Bei Aufruf dieses Workflows würde ein <xref:System.Activities.InvalidWorkflowException>-Objekt ausgelöst werden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="37abc-118">If this workflow was invoked, an <xref:System.Activities.InvalidWorkflowException> would be thrown, as shown in the following example.</span></span>  
  
```csharp  
try  
{  
    WorkflowInvoker.Invoke(wf);  
}  
catch (Exception ex)  
{  
    Console.WriteLine(ex);  
}  
```  
  
 <span data-ttu-id="37abc-119">**System.Activities.InvalidWorkflowException:**</span><span class="sxs-lookup"><span data-stu-id="37abc-119">**System.Activities.InvalidWorkflowException:**</span></span>  
<span data-ttu-id="37abc-120">Beim **Verarbeiten der Workflow Struktur sind folgende Fehler aufgetreten:** 
 **"Add": der Wert für das erforderliche Aktivitäts Argument "operand2" wurde nicht angegeben.** 
 **"Add": der Wert für das erforderliche Aktivitäts Argument "Operand1" wurde nicht angegeben.**</span><span class="sxs-lookup"><span data-stu-id="37abc-120">**The following errors were encountered while processing the workflow tree:**
 **'Add': Value for a required activity argument 'Operand2' was not supplied.**
 **'Add': Value for a required activity argument 'Operand1' was not supplied.**</span></span>  <span data-ttu-id="37abc-121">Damit dieser Beispielworkflow gültig ist, müssen die zwei erforderlichen Argumente der `Add`-Aktivität gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="37abc-121">For this example workflow to be valid, the two required arguments of the `Add` activity must be bound.</span></span> <span data-ttu-id="37abc-122">Im folgenden Beispiel werden die zwei erforderlichen Argumente zusammen mit dem Ergebniswert an Workflowvariablen gebunden.</span><span class="sxs-lookup"><span data-stu-id="37abc-122">In the following example, the two required arguments are bound to workflow variables along with the result value.</span></span> <span data-ttu-id="37abc-123">In diesem Beispiel wird das <xref:System.Activities.Activity%601.Result%2A>-Argument zusammen mit den zwei erforderlichen Argumenten gebunden.</span><span class="sxs-lookup"><span data-stu-id="37abc-123">In this example the <xref:System.Activities.Activity%601.Result%2A> argument is bound along with the two required arguments.</span></span> <span data-ttu-id="37abc-124">Das <xref:System.Activities.Activity%601.Result%2A>-Argument muss nicht gebunden werden und verursacht keine Validierungsfehler, wenn es nicht gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="37abc-124">The <xref:System.Activities.Activity%601.Result%2A> argument is not required to be bound and does not cause a validation error if it is not.</span></span> <span data-ttu-id="37abc-125">Es ist die Aufgabe des Workflowautors, das <xref:System.Activities.Activity%601.Result%2A>-Objekt zu binden, wenn sein Wert noch an einer anderen Stelle im Workflow verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="37abc-125">It is the responsibility of the workflow author to bind <xref:System.Activities.Activity%601.Result%2A> if its value is used elsewhere in the workflow.</span></span>  
  
```csharp  
new Add  
{  
    Operand1 = Operand1,  
    Operand2 = Operand2,  
    Result = Result  
}  
```  
  
### <a name="validating-required-arguments-on-the-root-activity"></a><span data-ttu-id="37abc-126">Überprüfen der erforderlichen Argumente der Stammaktivität</span><span class="sxs-lookup"><span data-stu-id="37abc-126">Validating Required Arguments on the Root Activity</span></span>  

 <span data-ttu-id="37abc-127">Wenn die Stammaktivität eines Workflows über Argumente verfügt, werden diese erst gebunden, wenn der Workflow aufgerufen und die Parameter an den Workflow übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="37abc-127">If the root activity of a workflow has arguments, these are not bound until the workflow is invoked and parameters are passed to the workflow.</span></span> <span data-ttu-id="37abc-128">Deshalb wird der folgende Workflow erfolgreich validiert. Es wird jedoch eine Ausnahme ausgelöst, wenn der Workflow aufgerufen wird, ohne dass die erforderlichen Argumente übergeben werden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="37abc-128">The following workflow passes validation, but an exception is thrown if the workflow is invoked without passing in the required arguments, as shown in the following example.</span></span>  
  
```csharp  
Activity wf = new Add();  
  
ValidationResults results = ActivityValidationServices.Validate(wf);  
// results has no errors or warnings, but when the workflow  
// is invoked, an InvalidWorkflowException is thrown.  
try  
{  
    WorkflowInvoker.Invoke(wf);  
}  
catch (Exception ex)  
{  
    Console.WriteLine(ex);  
}  
```  
  
 <span data-ttu-id="37abc-129">**System.ArgumentException: Die Argumenteinstellungen der Stammaktivität sind falsch.**</span><span class="sxs-lookup"><span data-stu-id="37abc-129">**System.ArgumentException: The root activity's argument settings are incorrect.**</span></span>  
<span data-ttu-id="37abc-130">**Korrigieren Sie entweder die Workflow Definition, oder geben Sie Eingabewerte an, um diese Fehler zu beheben:** 
 **"Add": der Wert für das erforderliche Aktivitäts Argument "operand2" wurde nicht angegeben.** 
 **"Add": der Wert für das erforderliche Aktivitäts Argument "Operand1" wurde nicht angegeben.**</span><span class="sxs-lookup"><span data-stu-id="37abc-130">**Either fix the workflow definition or supply input values to fix these errors:**
 **'Add': Value for a required activity argument 'Operand2' was not supplied.**
 **'Add': Value for a required activity argument 'Operand1' was not supplied.**</span></span>  <span data-ttu-id="37abc-131">Nachdem die richtigen Argumente übergeben wurden, wird der Workflow erfolgreich abgeschlossen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="37abc-131">After the correct arguments are passed, the workflow completes successfully, as shown in the following example.</span></span>  
  
```csharp  
Add wf = new Add();  
  
ValidationResults results = ActivityValidationServices.Validate(wf);  
// results has no errors or warnings, and the workflow completes  
// successfully because the required arguments were passed.  
try  
{  
    Dictionary<string, object> wfparams = new Dictionary<string, object>  
    {  
        { "Operand1", 10 },  
        { "Operand2", 15 }  
    };  
  
    int result = WorkflowInvoker.Invoke(wf, wfparams);  
    Console.WriteLine("Result: {0}", result);  
}  
catch (Exception ex)  
{  
    Console.WriteLine(ex);  
}  
```  
  
> [!NOTE]
> <span data-ttu-id="37abc-132">In diesem Beispiel wurde die Stammaktivität als `Add` und nicht wie im vorherigen Beispiel als `Activity` deklariert.</span><span class="sxs-lookup"><span data-stu-id="37abc-132">In this example, the root activity was declared as `Add` instead of `Activity` as in the previous example.</span></span> <span data-ttu-id="37abc-133">Deshalb kann die `WorkflowInvoker.Invoke`-Methode eine einzelne ganze Zahl zurückgeben, die die Ergebnisse der `Add`-Aktivität darstellt und kein Wörterbuch mit `out`-Argumenten.</span><span class="sxs-lookup"><span data-stu-id="37abc-133">This allows the `WorkflowInvoker.Invoke` method to return a single integer that represents the results of the `Add` activity instead of a dictionary of `out` arguments.</span></span> <span data-ttu-id="37abc-134">Die `wf`-Variable hätte auch als `Activity<int>` deklariert werden können.</span><span class="sxs-lookup"><span data-stu-id="37abc-134">The variable `wf` could also have been declared as `Activity<int>`.</span></span>  
  
 <span data-ttu-id="37abc-135">Bei der Validierung von Stammargumenten ist es die Aufgabe der Hostanwendung, sicherzustellen, dass alle erforderlichen Argumente beim Aufruf des Workflows übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="37abc-135">When validating root arguments, it is the responsibility of the host application to ensure that all required arguments are passed when the workflow is invoked.</span></span>  
  
### <a name="invoking-imperative-code-based-validation"></a><span data-ttu-id="37abc-136">Aufrufen der imperativen codebasierten Validierung</span><span class="sxs-lookup"><span data-stu-id="37abc-136">Invoking Imperative Code-Based Validation</span></span>

<span data-ttu-id="37abc-137">Die imperative codebasierte Validierung stellt eine einfache Möglichkeit für eine Aktivität dar, eine Eigenvalidierung bereitzustellen. Dies ist für Aktivitäten verfügbar, die von <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> und <xref:System.Activities.NativeActivity> abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="37abc-137">Imperative code-based validation provides a simple way for an activity to provide validation about itself, and is available for activities that derive from <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, and <xref:System.Activities.NativeActivity>.</span></span> <span data-ttu-id="37abc-138">Der Validierungscode, der sämtliche Validierungsfehler und -warnungen bestimmt, wird der Aktivität hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="37abc-138">Validation code that determines any validation errors or warnings is added to the activity.</span></span> <span data-ttu-id="37abc-139">Wenn die Validierung für die Aktivität aufgerufen wird, sind diese Warnungen oder Fehler in der Auflistung enthalten, die durch den Aufruf von <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="37abc-139">When validation is invoked on the activity, these warnings or errors are contained in the collection returned by the call to <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>.</span></span> <span data-ttu-id="37abc-140">Im folgenden Beispiel wird eine `CreateProduct` -Aktivität definiert.</span><span class="sxs-lookup"><span data-stu-id="37abc-140">In the following example, a `CreateProduct` activity is defined.</span></span> <span data-ttu-id="37abc-141">Wenn `Cost` größer als `Price` ist, wird den Metadaten in der <xref:System.Activities.CodeActivity.CacheMetadata%2A>-Überschreibung ein Validierungsfehler hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="37abc-141">If the `Cost` is greater than the `Price`, a validation error is added to the metadata in the <xref:System.Activities.CodeActivity.CacheMetadata%2A> override.</span></span>  
  
```csharp  
public sealed class CreateProduct : CodeActivity  
{  
    public double Price { get; set; }  
    public double Cost { get; set; }  
  
    // [RequiredArgument] attribute will generate a validation error
    // if the Description argument is not set.  
    [RequiredArgument]  
    public InArgument<string> Description { get; set; }  
  
    protected override void CacheMetadata(CodeActivityMetadata metadata)  
    {  
        base.CacheMetadata(metadata);  
        // Determine when the activity has been configured in an invalid way.  
        if (this.Cost > this.Price)  
        {  
            // Add a validation error with a custom message.  
            metadata.AddValidationError("The Cost must be less than or equal to the Price.");  
        }  
    }  
  
    protected override void Execute(CodeActivityContext context)  
    {  
        // Not needed for the sample.  
    }  
}  
```  
  
 <span data-ttu-id="37abc-142">In diesem Beispiel wird ein Workflow mit der `CreateProduct`-Aktivität konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="37abc-142">In this example, a workflow is configured using the `CreateProduct` activity.</span></span> <span data-ttu-id="37abc-143">In diesem Workflow ist `Cost` größer als `Price`, und das erforderliche `Description`-Argument ist nicht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="37abc-143">In this workflow, the `Cost` is greater than the `Price`, and the required `Description` argument is not set.</span></span> <span data-ttu-id="37abc-144">Wenn die Validierung aufgerufen wird, werden die folgenden Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="37abc-144">When validation is invoked, the following errors are returned.</span></span>  
  
```csharp  
Activity wf = new Sequence  
{  
    Activities =
    {  
        new CreateProduct  
        {  
            Cost = 75.00,  
            Price = 55.00  
            // Cost > Price and required Description argument not set.  
        },  
        new WriteLine  
        {  
            Text = "Product added."  
        }  
    }  
};  
  
ValidationResults results = ActivityValidationServices.Validate(wf);  
  
if (results.Errors.Count == 0 && results.Warnings.Count == 0)  
{  
    Console.WriteLine("No warnings or errors");  
}  
else  
{  
    foreach (ValidationError error in results.Errors)  
    {  
        Console.WriteLine("Error: {0}", error.Message);  
    }  
    foreach (ValidationError warning in results.Warnings)  
    {  
        Console.WriteLine("Warning: {0}", warning.Message);  
    }  
}  
```  
  
 <span data-ttu-id="37abc-145">**Fehler: Die Kosten müssen kleiner oder gleich dem Preis sein.**</span><span class="sxs-lookup"><span data-stu-id="37abc-145">**Error: The Cost must be less than or equal to the Price.**</span></span>  
<span data-ttu-id="37abc-146">**Fehler: Für das erforderliche Aktivitätsargument 'Description' wurde kein Wert angegeben.**</span><span class="sxs-lookup"><span data-stu-id="37abc-146">**Error: Value for a required activity argument 'Description' was not supplied.**</span></span>
> [!NOTE]
> <span data-ttu-id="37abc-147">Autoren benutzerdefinierter Aktivitäten können in der <xref:System.Activities.CodeActivity.CacheMetadata%2A>-Überschreibung einer Aktivität Validierungslogik bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="37abc-147">Custom activity authors can provide validation logic in an activity's <xref:System.Activities.CodeActivity.CacheMetadata%2A> override.</span></span> <span data-ttu-id="37abc-148">Von <xref:System.Activities.CodeActivity.CacheMetadata%2A> ausgelöste Ausnahmen werden nicht als Validierungsfehler behandelt.</span><span class="sxs-lookup"><span data-stu-id="37abc-148">Any exceptions that are thrown from <xref:System.Activities.CodeActivity.CacheMetadata%2A> are not treated as validation errors.</span></span> <span data-ttu-id="37abc-149">Diese Ausnahmen werden im Aufruf von <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> nicht verarbeitet und müssen vom Aufrufer behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="37abc-149">These exceptions will escape from the call to <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> and must be handled by the caller.</span></span>  
  
## <a name="using-validationsettings"></a><span data-ttu-id="37abc-150">Verwenden von ValidationSettings</span><span class="sxs-lookup"><span data-stu-id="37abc-150">Using ValidationSettings</span></span>  

 <span data-ttu-id="37abc-151">Standardmäßig werden alle Aktivitäten in der Aktivitätsstruktur ausgewertet, wenn die Validierung durch <xref:System.Activities.Validation.ActivityValidationServices> aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="37abc-151">By default, all activities in the activity tree are evaluated when validation is invoked by <xref:System.Activities.Validation.ActivityValidationServices>.</span></span> <span data-ttu-id="37abc-152">Mit <xref:System.Activities.Validation.ValidationSettings> kann die Validierung auf unterschiedliche Weise angepasst werden, indem die zugehörigen drei Eigenschaften konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="37abc-152"><xref:System.Activities.Validation.ValidationSettings> allows the validation to be customized in several different ways by configuring its three properties.</span></span> <span data-ttu-id="37abc-153"><xref:System.Activities.Validation.ValidationSettings.SingleLevel%2A> gibt an, ob das Validierungssteuerelement die gesamte Aktivitätsstruktur durchlaufen oder nur Validierungslogik auf die angegebene Aktivität anwenden soll.</span><span class="sxs-lookup"><span data-stu-id="37abc-153"><xref:System.Activities.Validation.ValidationSettings.SingleLevel%2A> specifies whether the validator should walk the entire activity tree or only apply validation logic to the supplied activity.</span></span> <span data-ttu-id="37abc-154">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="37abc-154">The default for this value is `false`.</span></span> <span data-ttu-id="37abc-155"><xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> gibt zusätzliche Einschränkungszuordnungen eines Typs für eine Liste von Einschränkungen an.</span><span class="sxs-lookup"><span data-stu-id="37abc-155"><xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> specifies additional constraint mapping from a type to a list of constraints.</span></span> <span data-ttu-id="37abc-156">Es gibt für den Basistyp jeder Aktivität in der Aktivitätsstruktur, die validiert wird, eine Suche in <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A>.</span><span class="sxs-lookup"><span data-stu-id="37abc-156">For the base type of each activity in the activity tree being validated there is a lookup into <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A>.</span></span> <span data-ttu-id="37abc-157">Wenn eine übereinstimmende Einschränkungsliste gefunden wird, werden alle Einschränkungen in der Liste für die Aktivität ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="37abc-157">If a matching constraint list is found, all constraints in the list are evaluated for the activity.</span></span> <span data-ttu-id="37abc-158"><xref:System.Activities.Validation.ValidationSettings.OnlyUseAdditionalConstraints%2A> gibt an, ob das Validierungssteuerelement alle Einschränkungen oder nur die in <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> angegebenen Einschränkungen auswerten soll.</span><span class="sxs-lookup"><span data-stu-id="37abc-158"><xref:System.Activities.Validation.ValidationSettings.OnlyUseAdditionalConstraints%2A> specifies whether the validator should evaluate all constraints or only those specified in <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A>.</span></span> <span data-ttu-id="37abc-159">Der Standardwert lautet `false`.</span><span class="sxs-lookup"><span data-stu-id="37abc-159">The default value is `false`.</span></span> <span data-ttu-id="37abc-160"><xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> und <xref:System.Activities.Validation.ValidationSettings.OnlyUseAdditionalConstraints%2A> sind nützlich, wenn Workflowhostautoren zusätzliche Validierung für Workflows hinzufügen möchten, z. B. Richtlinieneinschränkungen für Tools wie FxCop.</span><span class="sxs-lookup"><span data-stu-id="37abc-160"><xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> and <xref:System.Activities.Validation.ValidationSettings.OnlyUseAdditionalConstraints%2A> are useful for workflow host authors to add additional validation for workflows, such as policy constraints for tools such as FxCop.</span></span> <span data-ttu-id="37abc-161">Weitere Informationen zu Einschränkungen finden Sie unter [deklarative Einschränkungen](declarative-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="37abc-161">For more information about constraints, see [Declarative Constraints](declarative-constraints.md).</span></span>  
  
 <span data-ttu-id="37abc-162">Um <xref:System.Activities.Validation.ValidationSettings> zu verwenden, konfigurieren Sie die gewünschten Eigenschaften, und übergeben Sie diese in den Aufruf von <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="37abc-162">To use <xref:System.Activities.Validation.ValidationSettings>, configure the desired properties, and then pass it in the call to <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>.</span></span> <span data-ttu-id="37abc-163">In diesem Beispiel wird ein Workflow überprüft, der aus einem <xref:System.Activities.Statements.Sequence>- Objekt mit einer benutzerdefinierten `Add`-Aktivität besteht.</span><span class="sxs-lookup"><span data-stu-id="37abc-163">In this example, a workflow that consists of a <xref:System.Activities.Statements.Sequence> with a custom `Add` activity is validated.</span></span> <span data-ttu-id="37abc-164">Die `Add`-Aktivität verfügt über zwei erforderliche Argumente.</span><span class="sxs-lookup"><span data-stu-id="37abc-164">The `Add` activity has two required arguments.</span></span>  
  
```csharp  
public sealed class Add : CodeActivity<int>  
{  
    [RequiredArgument]  
    public InArgument<int> Operand1 { get; set; }  
  
    [RequiredArgument]  
    public InArgument<int> Operand2 { get; set; }  
  
    protected override int Execute(CodeActivityContext context)  
    {  
        return Operand1.Get(context) + Operand2.Get(context);  
    }  
}  
```  
  
 <span data-ttu-id="37abc-165">Die folgende `Add`-Aktivität wird in einem <xref:System.Activities.Statements.Sequence>-Objekt verwendet, die zwei erforderlichen Argumente werden jedoch nicht gebunden.</span><span class="sxs-lookup"><span data-stu-id="37abc-165">The following `Add` activity is used in a <xref:System.Activities.Statements.Sequence>, but its two required arguments are not bound.</span></span>  
  
```csharp  
Variable<int> Operand1 = new Variable<int> { Default = 10 };  
Variable<int> Operand2 = new Variable<int> { Default = 15 };  
Variable<int> Result = new Variable<int>();  
  
Activity wf = new Sequence  
{  
    Variables = { Operand1, Operand2, Result },  
    Activities =
    {  
        new Add(),  
        new WriteLine  
        {  
            Text = new InArgument<string>(env => "The result is " + Result.Get(env))  
        }  
    }  
};  
```  
  
 <span data-ttu-id="37abc-166">Im folgenden Beispiel wird die Validierung ausgeführt, während <xref:System.Activities.Validation.ValidationSettings.SingleLevel%2A> auf `true` festgelegt ist, sodass nur die <xref:System.Activities.Statements.Sequence>-Stammaktivität validiert wird.</span><span class="sxs-lookup"><span data-stu-id="37abc-166">For the following example, validation is performed with <xref:System.Activities.Validation.ValidationSettings.SingleLevel%2A> set to `true`, so only the root <xref:System.Activities.Statements.Sequence> activity is validated.</span></span>  
  
```csharp  
ValidationSettings settings = new ValidationSettings  
{  
    SingleLevel = true  
};  
  
ValidationResults results = ActivityValidationServices.Validate(wf, settings);  
  
if (results.Errors.Count == 0 && results.Warnings.Count == 0)  
{  
    Console.WriteLine("No warnings or errors");  
}  
else  
{  
    foreach (ValidationError error in results.Errors)  
    {  
        Console.WriteLine("Error: {0}", error.Message);  
    }  
    foreach (ValidationError warning in results.Warnings)  
    {  
        Console.WriteLine("Warning: {0}", warning.Message);  
    }  
}  
```  
  
 <span data-ttu-id="37abc-167">In diesem Code wird die folgende Ausgabe angezeigt:</span><span class="sxs-lookup"><span data-stu-id="37abc-167">This code displays the following output:</span></span>  
  
 <span data-ttu-id="37abc-168">**Keine Warnungen oder Fehler** Obwohl die- `Add` Aktivität über erforderliche Argumente verfügt, die nicht gebunden sind, ist die Validierung erfolgreich, da nur die Stamm Aktivität ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="37abc-168">**No warnings or errors** Even though the `Add` activity has required arguments that are not bound, validation is successful because only the root activity is evaluated.</span></span> <span data-ttu-id="37abc-169">Diese Art der Validierung ist nützlich, wenn nur bestimmte Elemente in einer Aktivitätsstruktur validiert werden, z. B. bei der Validierung einer Eigenschaftenänderung einer einzelnen Aktivität in einem Designer.</span><span class="sxs-lookup"><span data-stu-id="37abc-169">This type of validation is useful for validating only specific elements in an activity tree, such as validation of a property change of a single activity in a designer.</span></span> <span data-ttu-id="37abc-170">Beachten Sie, dass beim Aufrufen dieses Workflows die vollständige Validierung, die im Workflow konfiguriert ist, ausgewertet wird, und dass <xref:System.Activities.InvalidWorkflowException> ausgelöst würde.</span><span class="sxs-lookup"><span data-stu-id="37abc-170">Note that if this workflow is invoked, the full validation configured in the workflow is evaluated and an <xref:System.Activities.InvalidWorkflowException> would be thrown.</span></span> <span data-ttu-id="37abc-171">Mit <xref:System.Activities.Validation.ActivityValidationServices> und <xref:System.Activities.Validation.ValidationSettings> wird nur eine Validierung konfiguriert, die explizit vom Host aufgerufen wurde, und keine Validierung, die beim Aufruf eines Workflows auftritt.</span><span class="sxs-lookup"><span data-stu-id="37abc-171"><xref:System.Activities.Validation.ActivityValidationServices> and <xref:System.Activities.Validation.ValidationSettings> configure only validation explicitly invoked by the host, and not the validation that occurs when a workflow is invoked.</span></span>
