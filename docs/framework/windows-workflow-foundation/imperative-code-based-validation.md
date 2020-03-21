---
title: Imperative codebasierte Validierung
ms.date: 03/30/2017
ms.assetid: ae12537c-455e-42b1-82f4-cea4c46c023e
ms.openlocfilehash: f3b07d0ab06b3753286c929b90e713a6941684ad
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143095"
---
# <a name="imperative-code-based-validation"></a>Imperative codebasierte Validierung

Die imperative codebasierte Validierung stellt eine einfache Möglichkeit für eine Aktivität dar, eine Eigenvalidierung bereitzustellen. Dies ist für Aktivitäten verfügbar, die von <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> und <xref:System.Activities.NativeActivity> abgeleitet werden. Der Validierungscode, der sämtliche Validierungsfehler und -warnungen bestimmt, wird der Aktivität hinzugefügt.  
  
## <a name="using-code-based-validation"></a>Verwenden von codebasierter Validierung

Die codebasierte Validierung wird von Aktivitäten unterstützt, die von <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> und <xref:System.Activities.NativeActivity> abgeleitet werden. Der Validierungscode kann in der <xref:System.Activities.CodeActivity.CacheMetadata%2A>-Überschreibung eingefügt und die Validierungsfehler oder -warnungen dem Metadatenargument hinzugefügt werden. Im folgenden Beispiel wird den Metadaten ein Validierungsfehler hinzugefügt, wenn das `Cost`-Element größer als das `Price`-Element ist.  
  
> [!NOTE]
> Beachten Sie, dass `Cost` und `Price` keine Argumente der Aktivität sind, sondern Eigenschaften darstellen, die zur Entwurfszeit festgelegt werden. Daher können ihre Werte in der <xref:System.Activities.CodeActivity.CacheMetadata%2A>-Überschreibung überprüft werden. Der Wert der Daten, die ein Argument durchlaufen, kann zur Entwurfszeit nicht überprüft werden, weil der Datenfluss erst zur Laufzeit erfolgt. Aktivitätsargumente können jedoch mit dem `RequiredArgument`-Attribut und Überladungsgruppen überprüft werden, um ihre Bindung sicherzustellen. Mit diesem Beispielcode wird das `RequiredArgument`-Attribut auf das `Description`-Argument überprüft, und wenn es nicht gebunden ist, wird ein Validierungsfehler generiert. Erforderliche Argumente werden in [Erforderlichen Argumenten und Überlastgruppen](required-arguments-and-overload-groups.md)behandelt.  
  
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
  
 Standardmäßig wird den Metadaten ein Validierungsfehler hinzugefügt, wenn der <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A> aufgerufen wird. Verwenden Sie zum Hinzufügen einer Validierungswarnung die <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A>-Überladung, die einen <xref:System.Activities.Validation.ValidationError> akzeptiert, und geben Sie an, dass der <xref:System.Activities.Validation.ValidationError> eine Warnung darstellt, indem sie die <xref:System.Activities.Validation.ValidationError.IsWarning%2A>-Eigenschaft festlegen.  
  
 Eine Validierung wird ausgeführt, wenn ein Workflow im Workflow-Designer geändert und Validierungsfehler oder -warnungen im Workflow-Designer angezeigt werden. Die Validierung findet auch zur Laufzeit statt, wenn ein Workflow aufgerufen wird. Wenn Validierungsfehler auftreten, löst die Standardvalidierungslogik eine <xref:System.Activities.InvalidWorkflowException> aus. Weitere Informationen zum Aufrufen der Validierung und zum Zugriff auf Validierungswarnungen oder -fehler finden Sie unter [Aufrufen von Aktivitätsvalidierung](invoking-activity-validation.md).  
  
 Von <xref:System.Activities.CodeActivity.CacheMetadata%2A> ausgelöste Ausnahmen werden nicht als Validierungsfehler behandelt. Diese Ausnahmen werden im Aufruf von <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> nicht verarbeitet und müssen vom Aufrufer behandelt werden.  
  
 Codebasierte Validierung ist nützlich beim Validieren der Aktivität, die den Code enthält. Es besteht jedoch keine Sichtbarkeit für die anderen Aktivitäten im Workflow. Die Validierung deklarativer Einschränkungen bietet die Möglichkeit, die Beziehungen zwischen einer Aktivität und anderen Aktivitäten im Workflow zu überprüfen, und wird im Thema [Deklarative Einschränkungen](declarative-constraints.md) behandelt.
