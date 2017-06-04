---
title: "Imperative codebasierte Validierung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ae12537c-455e-42b1-82f4-cea4c46c023e
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Imperative codebasierte Validierung
Die imperative codebasierte Validierung stellt eine einfache Möglichkeit für eine Aktivität dar, eine Eigenvalidierung bereitzustellen. Dies ist für Aktivitäten verfügbar, die von <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> und <xref:System.Activities.NativeActivity> abgeleitet werden.Der Validierungscode wird der Aktivität hinzugefügt, der sämtliche Validierungsfehler und \-warnungen bestimmt.  
  
## Verwenden von codebasierter Validierung  
 Die codebasierte Validierung wird von Aktivitäten unterstützt, die von <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> und <xref:System.Activities.NativeActivity> abgeleitet werden.Der Validierungscode kann in der <xref:System.Activities.CodeActivity.CacheMetadata%2A>\-Überschreibung eingefügt, und Validierungsfehler oder \-warnungen können dem Metadatenargument hinzugefügt werden.Im folgenden Ausschnitt aus dem Beispiel [Grundlegende Validierung](../../../docs/framework/windows-workflow-foundation/samples/basic-validation.md) wird den Metadaten ein Validierungsfehler hinzugefügt, wenn das `Cost`\-Element größer als das `Price`\-Element ist.  
  
> [!NOTE]
>  Beachten Sie, dass `Cost` und `Price` keine Argumente der Aktivität sind, aber Eigenschaften darstellen, die zur Entwurfszeit festgelegt werden.Daher können ihre Werte in der <xref:System.Activities.CodeActivity.CacheMetadata%2A>\-Überschreibung überprüft werden.Der Wert der Daten, die ein Argument durchlaufen, kann zur Entwurfszeit nicht überprüft werden, weil der Datenfluss erst zur Laufzeit erfolgt. Aktivitätsargumente können jedoch mit dem `RequiredArgument`\-Attribut und Überladungsgruppen überprüft werden, um ihre Bindung sicherzustellen.Mit diesem Beispielcode wird das `RequiredArgument`\-Attribut auf das `Description`\-Argument überprüft, und wenn es nicht gebunden ist, wird ein Validierungsfehler generiert.Erforderliche Argumente werden in [Erforderliche Argumente und Überladungsgruppen](../../../docs/framework/windows-workflow-foundation//required-arguments-and-overload-groups.md) behandelt.  
  
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
  
 Standardmäßig wird den Metadaten ein Validierungsfehler hinzugefügt, wenn der <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A> aufgerufen wird.Verwenden Sie zum Hinzufügen einer Validierungswarnung die <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A>\-Überladung, die einen <xref:System.Activities.Validation.ValidationError> akzeptiert, und geben Sie an, dass der <xref:System.Activities.Validation.ValidationError> eine Warnung darstellt, indem sie die <xref:System.Activities.Validation.ValidationError.IsWarning%2A>\-Eigenschaft festlegen.  
  
 Eine Validierung wird ausgeführt, wenn ein Workflow im Workflow\-Designer geändert und Validierungsfehler oder \-warnungen im Workflow\-Designer angezeigt werden.Die Validierung tritt auch zur Laufzeit auf, wenn ein Workflow aufgerufen wird und Validierungsfehler auftreten; dann wird <xref:System.Activities.InvalidWorkflowException> von der Standardvalidierungslogik ausgelöst.[!INCLUDE[crabout](../../../includes/crabout-md.md)] zum Aufrufen der Validierung und zum Zugriff auf Validierungswarnungen oder \-fehler finden Sie unter [Aufrufen der Aktivitätsvalidierung](../../../docs/framework/windows-workflow-foundation//invoking-activity-validation.md).  
  
 Von <xref:System.Activities.CodeActivity.CacheMetadata%2A> ausgelöste Ausnahmen werden nicht als Validierungsfehler behandelt.Diese Ausnahmen werden im Aufruf von <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> nicht verarbeitet und müssen vom Aufrufer behandelt werden.  
  
 Codebasierte Validierung ist nützlich beim Überprüfen der Aktivität, die den Code enthält. Es besteht jedoch keine Sichtbarkeit für die anderen Aktivitäten im Workflow.Die Validierung von deklarativen Einschränkungen stellt eine Möglichkeit dar, die Beziehungen zwischen einer Aktivität und anderen Aktivitäten im Workflow zu validieren. Dieses Thema wird unter [Deklarative Einschränkungen](../../../docs/framework/windows-workflow-foundation//declarative-constraints.md) behandelt.