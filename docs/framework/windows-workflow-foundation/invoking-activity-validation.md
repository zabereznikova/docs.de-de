---
title: Aufrufen der Aktivitätsvalidierung
ms.date: 03/30/2017
ms.assetid: 22bef766-c505-4fd4-ac0f-7b363b238969
ms.openlocfilehash: 1241e6445cde20a192581e8132e563e0f7ca8d93
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182886"
---
# <a name="invoking-activity-validation"></a>Aufrufen der Aktivitätsvalidierung
Die Aktivitätsvalidierung stellt eine Methode bereit, um Fehler in der Konfiguration einer Aktivität vor der Ausführung zu identifizieren und zu melden. Eine Validierung wird ausgeführt, wenn ein Workflow im Workflow-Designer geändert und Validierungsfehler oder -warnungen im Workflow-Designer angezeigt werden. Die Validierung findet auch zur Laufzeit statt, wenn ein Workflow aufgerufen wird. Wenn Validierungsfehler auftreten, löst die Standardvalidierungslogik eine <xref:System.Activities.InvalidWorkflowException> aus. Windows Workflow Foundation (WF) stellt die <xref:System.Activities.Validation.ActivityValidationServices> Klasse bereit, die von Workflowanwendungs- und Toolingentwicklern verwendet werden kann, um eine Aktivität explizit zu überprüfen. In diesem Thema wird beschrieben, wie Aktivitäten mit dem <xref:System.Activities.Validation.ActivityValidationServices>-Objekt validiert werden.  
  
## <a name="using-activityvalidationservices"></a>Verwenden von ActivityValidationServices  
 Das <xref:System.Activities.Validation.ActivityValidationServices>-Objekt verfügt über zwei <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>-Überladungen, mit denen die Validierungslogik einer Aktivität aufgerufen wird. Die erste Überladung akzeptiert die Stammaktivität, die validiert werden soll, und gibt eine Auflistung von Validierungsfehlern und -warnungen zurück. Im folgenden Beispiel wird eine benutzerdefinierte `Add`-Aktivität verwendet, die über zwei erforderliche Argumente verfügt.  
  
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
  
 Die `Add`-Aktivität wird in einem <xref:System.Activities.Statements.Sequence>-Objekt verwendet, die zwei erforderlichen Argumente werden jedoch nicht gebunden, wie im folgenden Beispiel gezeigt.  
  
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
  
 Dieser Workflow kann durch Aufrufen von <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> überprüft werden. <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> gibt eine Auflistung aller Validierungsfehler und -warnungen zurück, die in der Aktivität selbst oder in ihren untergeordneten Elementen enthalten sind, wie im folgenden Beispiel gezeigt.  
  
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
  
 Wenn <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> für diesen Beispielworkflow aufgerufen wird, werden zwei Validierungsfehler zurückgegeben.  
  
 **Fehler: Für das erforderliche Aktivitätsargument „Operand2“ wurde kein Wert angegeben.**  
**Fehler: Der Wert für ein erforderliches Aktivitätsargument 'Operand1' wurde nicht bereitgestellt.**  Bei Aufruf dieses Workflows würde ein <xref:System.Activities.InvalidWorkflowException>-Objekt ausgelöst werden, wie im folgenden Beispiel gezeigt.  
  
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
  
 **System.Activities.InvalidWorkflowException:**  
**Bei der Verarbeitung der Workflowstruktur sind die folgenden Fehler aufgetreten:**
 **'Add': Wert für ein erforderliches Aktivitätsargument 'Operand2' wurde nicht bereitgestellt.** 
 **'Hinzufügen': Wert für ein erforderliches Aktivitätsargument 'Operand1' wurde nicht angegeben.**  Damit dieser Beispielworkflow gültig ist, müssen die zwei erforderlichen Argumente der `Add`-Aktivität gebunden werden. Im folgenden Beispiel werden die zwei erforderlichen Argumente zusammen mit dem Ergebniswert an Workflowvariablen gebunden. In diesem Beispiel wird das <xref:System.Activities.Activity%601.Result%2A>-Argument zusammen mit den zwei erforderlichen Argumenten gebunden. Das <xref:System.Activities.Activity%601.Result%2A>-Argument muss nicht gebunden werden und verursacht keine Validierungsfehler, wenn es nicht gebunden ist. Es ist die Aufgabe des Workflowautors, das <xref:System.Activities.Activity%601.Result%2A>-Objekt zu binden, wenn sein Wert noch an einer anderen Stelle im Workflow verwendet wird.  
  
```csharp  
new Add  
{  
    Operand1 = Operand1,  
    Operand2 = Operand2,  
    Result = Result  
}  
```  
  
### <a name="validating-required-arguments-on-the-root-activity"></a>Überprüfen der erforderlichen Argumente der Stammaktivität  
 Wenn die Stammaktivität eines Workflows über Argumente verfügt, werden diese erst gebunden, wenn der Workflow aufgerufen und die Parameter an den Workflow übergeben werden. Deshalb wird der folgende Workflow erfolgreich validiert. Es wird jedoch eine Ausnahme ausgelöst, wenn der Workflow aufgerufen wird, ohne dass die erforderlichen Argumente übergeben werden, wie im folgenden Beispiel gezeigt.  
  
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
  
 **System.ArgumentException: Die Argumenteinstellungen der Stammaktivität sind falsch.**  
**Beheben Sie entweder die Workflowdefinition oder geben Sie Eingabewerte ein, um diese Fehler zu beheben:**
 **'Hinzufügen': Wert für ein erforderliches Aktivitätsargument 'Operand2' wurde nicht angegeben.** 
 **'Hinzufügen': Wert für ein erforderliches Aktivitätsargument 'Operand1' wurde nicht angegeben.**  Nachdem die richtigen Argumente übergeben wurden, wird der Workflow erfolgreich abgeschlossen, wie im folgenden Beispiel gezeigt.  
  
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
> In diesem Beispiel wurde die Stammaktivität als `Add` und nicht wie im vorherigen Beispiel als `Activity` deklariert. Deshalb kann die `WorkflowInvoker.Invoke`-Methode eine einzelne ganze Zahl zurückgeben, die die Ergebnisse der `Add`-Aktivität darstellt und kein Wörterbuch mit `out`-Argumenten. Die `wf`-Variable hätte auch als `Activity<int>` deklariert werden können.  
  
 Bei der Validierung von Stammargumenten ist es die Aufgabe der Hostanwendung, sicherzustellen, dass alle erforderlichen Argumente beim Aufruf des Workflows übergeben werden.  
  
### <a name="invoking-imperative-code-based-validation"></a>Aufrufen der imperativen codebasierten Validierung

Die imperative codebasierte Validierung stellt eine einfache Möglichkeit für eine Aktivität dar, eine Eigenvalidierung bereitzustellen. Dies ist für Aktivitäten verfügbar, die von <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> und <xref:System.Activities.NativeActivity> abgeleitet werden. Der Validierungscode, der sämtliche Validierungsfehler und -warnungen bestimmt, wird der Aktivität hinzugefügt. Wenn die Validierung für die Aktivität aufgerufen wird, sind diese Warnungen oder Fehler in der Auflistung enthalten, die durch den Aufruf von <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> zurückgegeben wurde. Im folgenden Beispiel wird eine `CreateProduct` -Aktivität definiert. Wenn `Cost` größer als `Price` ist, wird den Metadaten in der <xref:System.Activities.CodeActivity.CacheMetadata%2A>-Überschreibung ein Validierungsfehler hinzugefügt.  
  
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
  
 In diesem Beispiel wird ein Workflow mit der `CreateProduct`-Aktivität konfiguriert. In diesem Workflow ist `Cost` größer als `Price`, und das erforderliche `Description`-Argument ist nicht festgelegt. Wenn die Validierung aufgerufen wird, werden die folgenden Fehler zurückgegeben.  
  
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
  
 **Fehler: Die Kosten müssen kleiner oder gleich dem Preis sein.**  
**Fehler: Für das erforderliche Aktivitätsargument 'Description' wurde kein Wert angegeben.**
> [!NOTE]
> Autoren benutzerdefinierter Aktivitäten können in der <xref:System.Activities.CodeActivity.CacheMetadata%2A>-Überschreibung einer Aktivität Validierungslogik bereitstellen. Von <xref:System.Activities.CodeActivity.CacheMetadata%2A> ausgelöste Ausnahmen werden nicht als Validierungsfehler behandelt. Diese Ausnahmen werden im Aufruf von <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> nicht verarbeitet und müssen vom Aufrufer behandelt werden.  
  
## <a name="using-validationsettings"></a>Verwenden von ValidationSettings  
 Standardmäßig werden alle Aktivitäten in der Aktivitätsstruktur ausgewertet, wenn die Validierung durch <xref:System.Activities.Validation.ActivityValidationServices> aufgerufen wird. Mit <xref:System.Activities.Validation.ValidationSettings> kann die Validierung auf unterschiedliche Weise angepasst werden, indem die zugehörigen drei Eigenschaften konfiguriert werden. <xref:System.Activities.Validation.ValidationSettings.SingleLevel%2A> gibt an, ob das Validierungssteuerelement die gesamte Aktivitätsstruktur durchlaufen oder nur Validierungslogik auf die angegebene Aktivität anwenden soll. Der Standardwert ist `false`. <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> gibt zusätzliche Einschränkungszuordnungen eines Typs für eine Liste von Einschränkungen an. Es gibt für den Basistyp jeder Aktivität in der Aktivitätsstruktur, die validiert wird, eine Suche in <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A>. Wenn eine übereinstimmende Einschränkungsliste gefunden wird, werden alle Einschränkungen in der Liste für die Aktivität ausgewertet. <xref:System.Activities.Validation.ValidationSettings.OnlyUseAdditionalConstraints%2A> gibt an, ob das Validierungssteuerelement alle Einschränkungen oder nur die in <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> angegebenen Einschränkungen auswerten soll. Standardwert: `false`. <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> und <xref:System.Activities.Validation.ValidationSettings.OnlyUseAdditionalConstraints%2A> sind nützlich, wenn Workflowhostautoren zusätzliche Validierung für Workflows hinzufügen möchten, z. B. Richtlinieneinschränkungen für Tools wie FxCop. Weitere Informationen zu Einschränkungen finden Sie unter [Deklarative Einschränkungen](declarative-constraints.md).  
  
 Um <xref:System.Activities.Validation.ValidationSettings> zu verwenden, konfigurieren Sie die gewünschten Eigenschaften, und übergeben Sie diese in den Aufruf von <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>. In diesem Beispiel wird ein Workflow überprüft, der aus einem <xref:System.Activities.Statements.Sequence>- Objekt mit einer benutzerdefinierten `Add`-Aktivität besteht. Die `Add`-Aktivität verfügt über zwei erforderliche Argumente.  
  
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
  
 Die folgende `Add`-Aktivität wird in einem <xref:System.Activities.Statements.Sequence>-Objekt verwendet, die zwei erforderlichen Argumente werden jedoch nicht gebunden.  
  
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
  
 Im folgenden Beispiel wird die Validierung ausgeführt, während <xref:System.Activities.Validation.ValidationSettings.SingleLevel%2A> auf `true` festgelegt ist, sodass nur die <xref:System.Activities.Statements.Sequence>-Stammaktivität validiert wird.  
  
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
  
 In diesem Code wird die folgende Ausgabe angezeigt:  
  
 **Keine Warnungen oder Fehler** Obwohl für `Add` die Aktivität Argumente erforderlich sind, die nicht gebunden sind, ist die Validierung erfolgreich, da nur die Stammaktivität ausgewertet wird. Diese Art der Validierung ist nützlich, wenn nur bestimmte Elemente in einer Aktivitätsstruktur validiert werden, z. B. bei der Validierung einer Eigenschaftenänderung einer einzelnen Aktivität in einem Designer. Beachten Sie, dass beim Aufrufen dieses Workflows die vollständige Validierung, die im Workflow konfiguriert ist, ausgewertet wird, und dass <xref:System.Activities.InvalidWorkflowException> ausgelöst würde. Mit <xref:System.Activities.Validation.ActivityValidationServices> und <xref:System.Activities.Validation.ValidationSettings> wird nur eine Validierung konfiguriert, die explizit vom Host aufgerufen wurde, und keine Validierung, die beim Aufruf eines Workflows auftritt.
