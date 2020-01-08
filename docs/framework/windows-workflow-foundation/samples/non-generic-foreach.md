---
title: Nicht generisches ForEach-Element
ms.date: 03/30/2017
ms.assetid: 576cd07a-d58d-4536-b514-77bad60bff38
ms.openlocfilehash: 93a6b1d815ef6478974ceadf8ad935be2a3bdea5
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75338658"
---
# <a name="non-generic-foreach"></a><span data-ttu-id="84d2d-102">Nicht generisches ForEach-Element</span><span class="sxs-lookup"><span data-stu-id="84d2d-102">Non-Generic ForEach</span></span>
<span data-ttu-id="84d2d-103">Zur Toolbox von [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] gehört ein Satz von Ablaufsteuerungsaktivitäten, einschließlich <xref:System.Activities.Statements.ForEach%601>, die das Durchlaufen von <xref:System.Collections.Generic.IEnumerable%601>-Auflistungen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="84d2d-103">[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] ships in its toolbox a set of Control Flow activities, including <xref:System.Activities.Statements.ForEach%601>, which allows iterating through <xref:System.Collections.Generic.IEnumerable%601> collections.</span></span>  
  
 <span data-ttu-id="84d2d-104">Für <xref:System.Activities.Statements.ForEach%601> muss die <xref:System.Activities.Statements.ForEach%601.Values%2A>-Eigenschaft den Typ <xref:System.Collections.Generic.IEnumerable%601> aufweisen.</span><span class="sxs-lookup"><span data-stu-id="84d2d-104"><xref:System.Activities.Statements.ForEach%601> requires its <xref:System.Activities.Statements.ForEach%601.Values%2A> property to be of type <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="84d2d-105">Dies schließt Benutzer davon aus, Datenstrukturen zu durchlaufen, die die <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle implementieren (z. B. <xref:System.Collections.ArrayList>).</span><span class="sxs-lookup"><span data-stu-id="84d2d-105">This precludes users from iterating over data structures that implement <xref:System.Collections.Generic.IEnumerable%601> interface (for example, <xref:System.Collections.ArrayList>).</span></span> <span data-ttu-id="84d2d-106">Die nicht generische Version von <xref:System.Activities.Statements.ForEach%601> bewältigt diese Anforderung zulasten einer größeren Laufzeitkomplexität zum Sicherstellen der Kompatibilität der Typen der Werte in der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="84d2d-106">The non-generic version of <xref:System.Activities.Statements.ForEach%601> overcomes this requirement, at the expense of more run-time complexity for ensuring the compatibility of the types of the values in the collection.</span></span>  
  
 <span data-ttu-id="84d2d-107">In diesem Beispiel wird gezeigt, wie eine nicht generische <xref:System.Activities.Statements.ForEach%601>-Aktivität und der Designer implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="84d2d-107">This sample shows how to implement a non-generic <xref:System.Activities.Statements.ForEach%601> activity and its designer.</span></span> <span data-ttu-id="84d2d-108">Diese Aktivität kann zum Durchlaufen von <xref:System.Collections.ArrayList> verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="84d2d-108">This activity can be used to iterate through <xref:System.Collections.ArrayList>.</span></span>  
  
## <a name="foreach-activity"></a><span data-ttu-id="84d2d-109">ForEach-Aktivität</span><span class="sxs-lookup"><span data-stu-id="84d2d-109">ForEach Activity</span></span>  
 <span data-ttu-id="84d2d-110">Die C#/Visual Basic `foreach`-Anweisung zählt die Elemente einer Auflistung auf und führt eine eingebettete Anweisung für jedes Element der Auflistung aus.</span><span class="sxs-lookup"><span data-stu-id="84d2d-110">The C#/Visual Basic `foreach` statement enumerates the elements of a collection, executing an embedded statement for each element of the collection.</span></span> <span data-ttu-id="84d2d-111">Die entsprechenden [!INCLUDE[wf1](../../../../includes/wf1-md.md)]-Aktivitäten für `foreach` sind <xref:System.Activities.Statements.ForEach%601> und <xref:System.Activities.Statements.ParallelForEach%601>.</span><span class="sxs-lookup"><span data-stu-id="84d2d-111">The [!INCLUDE[wf1](../../../../includes/wf1-md.md)] equivalent activities of `foreach` are <xref:System.Activities.Statements.ForEach%601> and <xref:System.Activities.Statements.ParallelForEach%601>.</span></span> <span data-ttu-id="84d2d-112">Die <xref:System.Activities.Statements.ForEach%601>-Aktivität enthält eine Liste von Werten und einen Text.</span><span class="sxs-lookup"><span data-stu-id="84d2d-112">The <xref:System.Activities.Statements.ForEach%601> activity contains a list of values and a body.</span></span> <span data-ttu-id="84d2d-113">Zur Laufzeit wird die Liste durchlaufen, und der Text wird für jeden Wert in der Liste ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="84d2d-113">At runtime, the list is iterated and the body is executed for each value in the list.</span></span>  
  
 <span data-ttu-id="84d2d-114">In den meisten Fällen sollte die generische Version der Aktivität die bevorzugte Lösung sein, da die meisten Szenarien, in denen sie verwendet wird, damit abgedeckt werden und sie zur Kompilierzeit eine Typüberprüfung bietet.</span><span class="sxs-lookup"><span data-stu-id="84d2d-114">For most cases, the generic version of the activity should be the preferred solution, because it covers most of the scenarios in which it would be used, and provides type checking at compile time.</span></span> <span data-ttu-id="84d2d-115">Die nicht generische Version kann zum Durchlaufen von Typen, die die nicht generische <xref:System.Collections.IEnumerable>-Schnittstelle implementieren, verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="84d2d-115">The non-generic version can be used for iterating through types that implement the non-generic <xref:System.Collections.IEnumerable> interface.</span></span>  
  
## <a name="class-definition"></a><span data-ttu-id="84d2d-116">Klassendefinition</span><span class="sxs-lookup"><span data-stu-id="84d2d-116">Class Definition</span></span>  
 <span data-ttu-id="84d2d-117">Im folgenden Codebeispiel wird die Definition einer nicht generischen `ForEach`-Aktivität veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="84d2d-117">The following code example shows the definition of a non-generic `ForEach` activity.</span></span>  
  
```csharp  
[ContentProperty("Body")]  
public class ForEach : NativeActivity  
{  
    [RequiredArgument]  
    [DefaultValue(null)]  
    InArgument<IEnumerable> Values { get; set; }  
  
    [DefaultValue(null)]  
    [DependsOn("Values")]  
    ActivityAction<object> Body { get; set; }   
}  
```  
  
 <span data-ttu-id="84d2d-118">Text (optional)</span><span class="sxs-lookup"><span data-stu-id="84d2d-118">Body (optional)</span></span>  
 <span data-ttu-id="84d2d-119">Das <xref:System.Activities.ActivityAction>-Element mit dem Typ <xref:System.Object>, das für jedes Element in der Auflistung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="84d2d-119">The <xref:System.Activities.ActivityAction> of type <xref:System.Object>, which is executed for each element in the collection.</span></span> <span data-ttu-id="84d2d-120">Jedes einzelne Element wird durch die `Argument`-Eigenschaft in den Text übergeben.</span><span class="sxs-lookup"><span data-stu-id="84d2d-120">Each individual element is passed into the Body through its `Argument` property.</span></span>  
  
 <span data-ttu-id="84d2d-121">Werte (optional)</span><span class="sxs-lookup"><span data-stu-id="84d2d-121">Values (optional)</span></span>  
 <span data-ttu-id="84d2d-122">Die Auflistung von Elementen, die durchlaufen werden.</span><span class="sxs-lookup"><span data-stu-id="84d2d-122">The collection of elements that are iterated over.</span></span> <span data-ttu-id="84d2d-123">Die Sicherstellung, dass alle Elemente der Auflistung kompatible Typen aufweisen, erfolgt zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="84d2d-123">Ensuring that all elements of the collection are of compatible types is done at run-time.</span></span>  
  
## <a name="example-of-using-foreach"></a><span data-ttu-id="84d2d-124">Beispiel der Verwendung von ForEach</span><span class="sxs-lookup"><span data-stu-id="84d2d-124">Example of Using ForEach</span></span>  
 <span data-ttu-id="84d2d-125">Im folgenden Code wird veranschaulicht, wie die ForEach-Aktivität in einer Anwendung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="84d2d-125">The following code demonstrates how to use the ForEach activity in an application.</span></span>  
  
```csharp  
string[] names = { "bill", "steve", "ray" };  
  
DelegateInArgument<object> iterationVariable = new DelegateInArgument<object>() { Name = "iterationVariable" };  
  
Activity sampleUsage =  
    new ForEach  
    {  
       Values = new InArgument<IEnumerable>(c=> names),  
       Body = new ActivityAction<object>   
       {                          
           Argument = iterationVariable,  
           Handler = new WriteLine  
           {  
               Text = new InArgument<string>(env => string.Format("Hello {0}",                                                               iterationVariable.Get(env)))  
           }  
       }  
   };  
```  
  
|<span data-ttu-id="84d2d-126">Bedingung</span><span class="sxs-lookup"><span data-stu-id="84d2d-126">Condition</span></span>|<span data-ttu-id="84d2d-127">Meldung</span><span class="sxs-lookup"><span data-stu-id="84d2d-127">Message</span></span>|<span data-ttu-id="84d2d-128">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="84d2d-128">Severity</span></span>|<span data-ttu-id="84d2d-129">Ausnahmetyp</span><span class="sxs-lookup"><span data-stu-id="84d2d-129">Exception Type</span></span>|  
|---------------|-------------|--------------|--------------------|  
|<span data-ttu-id="84d2d-130">Werte sind `null`</span><span class="sxs-lookup"><span data-stu-id="84d2d-130">Values is `null`</span></span>|<span data-ttu-id="84d2d-131">Für das erforderliche Aktivitätsargument "Values1" wurde kein Wert angegeben.</span><span class="sxs-lookup"><span data-stu-id="84d2d-131">Value for a required activity argument 'Values' was not supplied.</span></span>|<span data-ttu-id="84d2d-132">Fehler</span><span class="sxs-lookup"><span data-stu-id="84d2d-132">Error</span></span>|<xref:System.InvalidOperationException>|  
  
## <a name="foreach-designer"></a><span data-ttu-id="84d2d-133">ForEach-Designer</span><span class="sxs-lookup"><span data-stu-id="84d2d-133">ForEach Designer</span></span>  
 <span data-ttu-id="84d2d-134">Der Aktivitätsdesigner für das Beispiel ist dem Designer im Aussehen ähnlich, der für die integrierte <xref:System.Activities.Statements.ForEach%601>-Aktivität dient.</span><span class="sxs-lookup"><span data-stu-id="84d2d-134">The activity designer for the sample is similar in appearance to the designer provided for the built-in <xref:System.Activities.Statements.ForEach%601> activity.</span></span> <span data-ttu-id="84d2d-135">Der Designer wird in der Toolbox in der Kategorie **Beispiele**, **nicht generische Aktivitäten** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="84d2d-135">The designer appears in the toolbox in the **Samples**, **Non-Generic Activities** category.</span></span> <span data-ttu-id="84d2d-136">Der Designer wird in der Toolbox **ForEachWithBodyFactory** genannt, da die-Aktivität ein <xref:System.Activities.Presentation.IActivityTemplateFactory> in der Toolbox verfügbar macht, das die Aktivität mit einem ordnungsgemäß konfigurierten <xref:System.Activities.ActivityAction>erstellt.</span><span class="sxs-lookup"><span data-stu-id="84d2d-136">The designer is named **ForEachWithBodyFactory** in the toolbox, because the activity exposes an <xref:System.Activities.Presentation.IActivityTemplateFactory> in the toolbox, which creates the activity with a properly configured <xref:System.Activities.ActivityAction>.</span></span>  
  
```csharp  
public sealed class ForEachWithBodyFactory : IActivityTemplateFactory  
{  
    public Activity Create(DependencyObject target)  
    {  
        return new Microsoft.Samples.Activities.Statements.ForEach()  
        {  
            Body = new ActivityAction<object>()  
            {  
                Argument = new DelegateInArgument<object>()  
                {  
                    Name = "item"  
                }  
            }  
        };  
    }  
}  
```  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="84d2d-137">So führen Sie dieses Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="84d2d-137">To run this sample</span></span>  
  
1. <span data-ttu-id="84d2d-138">Legen Sie das Projekt Ihrer Wahl als Startprojekt der Projektmappe fest:</span><span class="sxs-lookup"><span data-stu-id="84d2d-138">Set the project of your choice as the start-up project of the solution:</span></span>  
  
    1. <span data-ttu-id="84d2d-139">**Codetestclient** zeigt, wie die-Aktivität mithilfe von Code verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="84d2d-139">**CodeTestClient** shows how to use the activity using code.</span></span>  
  
    2. <span data-ttu-id="84d2d-140">**Designertestclient** zeigt, wie die-Aktivität innerhalb des Designers verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="84d2d-140">**DesignerTestClient** shows how to use the activity within the designer.</span></span>  
  
2. <span data-ttu-id="84d2d-141">Erstellen Sie das Projekt, und führen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="84d2d-141">Build and run the project.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="84d2d-142">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="84d2d-142">The samples may already be installed on your machine.</span></span> <span data-ttu-id="84d2d-143">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="84d2d-143">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="84d2d-144">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="84d2d-144">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="84d2d-145">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="84d2d-145">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\NonGenericForEach`
