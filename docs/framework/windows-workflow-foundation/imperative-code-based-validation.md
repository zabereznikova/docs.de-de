---
title: Imperative codebasierte Validierung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae12537c-455e-42b1-82f4-cea4c46c023e
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5b9919c2919bf670396dc4af7d17d7087f9b4908
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="imperative-code-based-validation"></a><span data-ttu-id="1031e-102">Imperative codebasierte Validierung</span><span class="sxs-lookup"><span data-stu-id="1031e-102">Imperative Code-Based Validation</span></span>
<span data-ttu-id="1031e-103">Die imperative codebasierte Validierung stellt eine einfache Möglichkeit für eine Aktivität dar, eine Eigenvalidierung bereitzustellen. Dies ist für Aktivitäten verfügbar, die von <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> und <xref:System.Activities.NativeActivity> abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="1031e-103">Imperative code-based validation provides a simple way for an activity to provide validation about itself, and is available for activities that derive from <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, and <xref:System.Activities.NativeActivity>.</span></span> <span data-ttu-id="1031e-104">Der Validierungscode, der sämtliche Validierungsfehler und -warnungen bestimmt, wird der Aktivität hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1031e-104">Validation code that determines any validation errors or warnings is added to the activity.</span></span>  
  
## <a name="using-code-based-validation"></a><span data-ttu-id="1031e-105">Verwenden von codebasierter Validierung</span><span class="sxs-lookup"><span data-stu-id="1031e-105">Using Code-Based Validation</span></span>  
 <span data-ttu-id="1031e-106">Die codebasierte Validierung wird von Aktivitäten unterstützt, die von <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> und <xref:System.Activities.NativeActivity> abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="1031e-106">Code-based validation is supported by activities that derive from <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, and <xref:System.Activities.NativeActivity>.</span></span> <span data-ttu-id="1031e-107">Der Validierungscode kann in der <xref:System.Activities.CodeActivity.CacheMetadata%2A>-Überschreibung eingefügt und die Validierungsfehler oder -warnungen dem Metadatenargument hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="1031e-107">Validation code can be placed in the <xref:System.Activities.CodeActivity.CacheMetadata%2A> override, and validation errors or warnings can be added to the metadata argument.</span></span> <span data-ttu-id="1031e-108">Im folgenden Beispiel entnommen der [grundlegende Validierung](../../../docs/framework/windows-workflow-foundation/samples/basic-validation.md) Beispiel, wenn die `Cost` ist größer als die `Price`, die Metadaten ein Validierungsfehler hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1031e-108">In the following example, taken from the [Basic Validation](../../../docs/framework/windows-workflow-foundation/samples/basic-validation.md) sample, if the `Cost` is greater than the `Price`, a validation error is added to the metadata.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1031e-109">Beachten Sie, dass `Cost` und `Price` keine Argumente der Aktivität sind, sondern Eigenschaften darstellen, die zur Entwurfszeit festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="1031e-109">Note that `Cost` and `Price` are not arguments to the activity, but are properties that are set at design time.</span></span> <span data-ttu-id="1031e-110">Daher können ihre Werte in der <xref:System.Activities.CodeActivity.CacheMetadata%2A>-Überschreibung überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="1031e-110">That is why their values can be validated in the <xref:System.Activities.CodeActivity.CacheMetadata%2A> override.</span></span> <span data-ttu-id="1031e-111">Der Wert der Daten, die ein Argument durchlaufen, kann zur Entwurfszeit nicht überprüft werden, weil der Datenfluss erst zur Laufzeit erfolgt. Aktivitätsargumente können jedoch mit dem `RequiredArgument`-Attribut und Überladungsgruppen überprüft werden, um ihre Bindung sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="1031e-111">The value of the data flowing through an argument cannot be validated at design time because the data does not flow until run time, but activity arguments can be validated to ensure that they are bound by using the `RequiredArgument` attribute and overload groups.</span></span> <span data-ttu-id="1031e-112">Mit diesem Beispielcode wird das `RequiredArgument`-Attribut auf das `Description`-Argument überprüft, und wenn es nicht gebunden ist, wird ein Validierungsfehler generiert.</span><span class="sxs-lookup"><span data-stu-id="1031e-112">This example code sees the `RequiredArgument` attribute for the `Description` argument, and if it is not bound then a validation error is generated.</span></span> <span data-ttu-id="1031e-113">Erforderliche Argumente sind in behandelt [erforderliche Argumente und Überladungsgruppen](../../../docs/framework/windows-workflow-foundation/required-arguments-and-overload-groups.md).</span><span class="sxs-lookup"><span data-stu-id="1031e-113">Required arguments are covered in [Required Arguments and Overload Groups](../../../docs/framework/windows-workflow-foundation/required-arguments-and-overload-groups.md).</span></span>  
  
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
  
 <span data-ttu-id="1031e-114">Standardmäßig wird den Metadaten ein Validierungsfehler hinzugefügt, wenn der <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A> aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="1031e-114">By default, a validation error is added to the metadata when <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A> is called.</span></span> <span data-ttu-id="1031e-115">Verwenden Sie zum Hinzufügen einer Validierungswarnung die <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A>-Überladung, die einen <xref:System.Activities.Validation.ValidationError> akzeptiert, und geben Sie an, dass der <xref:System.Activities.Validation.ValidationError> eine Warnung darstellt, indem sie die <xref:System.Activities.Validation.ValidationError.IsWarning%2A>-Eigenschaft festlegen.</span><span class="sxs-lookup"><span data-stu-id="1031e-115">To add a validation warning, use the <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A> overload that takes a <xref:System.Activities.Validation.ValidationError>, and specify that the <xref:System.Activities.Validation.ValidationError> represents a warning by setting the <xref:System.Activities.Validation.ValidationError.IsWarning%2A> property.</span></span>  
  
 <span data-ttu-id="1031e-116">Eine Validierung wird ausgeführt, wenn ein Workflow im Workflow-Designer geändert und Validierungsfehler oder -warnungen im Workflow-Designer angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1031e-116">Validation occurs when a workflow is modified in the workflow designer and any validation errors or warnings are displayed in the workflow designer.</span></span> <span data-ttu-id="1031e-117">Die Validierung findet auch zur Laufzeit statt, wenn ein Workflow aufgerufen wird. Wenn Validierungsfehler auftreten, löst die Standardvalidierungslogik eine <xref:System.Activities.InvalidWorkflowException> aus.</span><span class="sxs-lookup"><span data-stu-id="1031e-117">Validation also occurs at run time when a workflow is invoked and if any validation errors occur, an <xref:System.Activities.InvalidWorkflowException> is thrown by the default validation logic.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="1031e-118">Aufrufen der Validierung von und Zugreifen auf keine validierungswarnungen oder Fehler finden Sie unter [Aufrufen der Aktivitätsvalidierung](../../../docs/framework/windows-workflow-foundation/invoking-activity-validation.md).</span><span class="sxs-lookup"><span data-stu-id="1031e-118"> invoking validation and accessing any validation warnings or errors, see [Invoking Activity Validation](../../../docs/framework/windows-workflow-foundation/invoking-activity-validation.md).</span></span>  
  
 <span data-ttu-id="1031e-119">Von <xref:System.Activities.CodeActivity.CacheMetadata%2A> ausgelöste Ausnahmen werden nicht als Validierungsfehler behandelt.</span><span class="sxs-lookup"><span data-stu-id="1031e-119">Any exceptions that are thrown from <xref:System.Activities.CodeActivity.CacheMetadata%2A> are not treated as validation errors.</span></span> <span data-ttu-id="1031e-120">Diese Ausnahmen werden im Aufruf von <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> nicht verarbeitet und müssen vom Aufrufer behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="1031e-120">These exceptions will escape from the call to <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> and must be handled by the caller.</span></span>  
  
 <span data-ttu-id="1031e-121">Codebasierte Validierung ist nützlich beim Überprüfen der Aktivität, die den Code enthält. Es besteht jedoch keine Sichtbarkeit für die anderen Aktivitäten im Workflow.</span><span class="sxs-lookup"><span data-stu-id="1031e-121">Code-based validation is useful for validating the activity that contains the code, but it does not have visibility into the other activities in the workflow.</span></span> <span data-ttu-id="1031e-122">Deklarative Einschränkungen Überprüfung bietet die Möglichkeit, die Beziehungen zwischen einer Aktivität und andere Aktivitäten im Workflow zu überprüfen, und wird ausführlicher im die [deklarative Einschränkungen](../../../docs/framework/windows-workflow-foundation/declarative-constraints.md) Thema.</span><span class="sxs-lookup"><span data-stu-id="1031e-122">Declarative constraints validation provides the ability to validate the relationships between an activity and other activities in the workflow, and is covered in the [Declarative Constraints](../../../docs/framework/windows-workflow-foundation/declarative-constraints.md) topic.</span></span>
