---
title: Nicht generisches ForEach-Element
ms.date: 03/30/2017
ms.assetid: 576cd07a-d58d-4536-b514-77bad60bff38
ms.openlocfilehash: 0274cd5b87e6039ff40afa3108986ffd113fc4fb
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47089620"
---
# <a name="non-generic-foreach"></a><span data-ttu-id="1ea6e-102">Nicht generisches ForEach-Element</span><span class="sxs-lookup"><span data-stu-id="1ea6e-102">Non-Generic ForEach</span></span>
<span data-ttu-id="1ea6e-103">Zur Toolbox von [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] gehört ein Satz von Ablaufsteuerungsaktivitäten, einschließlich <xref:System.Activities.Statements.ForEach%601>, die das Durchlaufen von <xref:System.Collections.Generic.IEnumerable%601>-Auflistungen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="1ea6e-103">[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] ships in its toolbox a set of Control Flow activities, including <xref:System.Activities.Statements.ForEach%601>, which allows iterating through <xref:System.Collections.Generic.IEnumerable%601> collections.</span></span>  
  
 <span data-ttu-id="1ea6e-104">Für <xref:System.Activities.Statements.ForEach%601> muss die <xref:System.Activities.Statements.ForEach%601.Values%2A>-Eigenschaft den Typ <xref:System.Collections.Generic.IEnumerable%601> aufweisen.</span><span class="sxs-lookup"><span data-stu-id="1ea6e-104"><xref:System.Activities.Statements.ForEach%601> requires its <xref:System.Activities.Statements.ForEach%601.Values%2A> property to be of type <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="1ea6e-105">Dies schließt Benutzer davon aus, Datenstrukturen zu durchlaufen, die die <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle implementieren (z. B. <xref:System.Collections.ArrayList>).</span><span class="sxs-lookup"><span data-stu-id="1ea6e-105">This precludes users from iterating over data structures that implement <xref:System.Collections.Generic.IEnumerable%601> interface (for example, <xref:System.Collections.ArrayList>).</span></span> <span data-ttu-id="1ea6e-106">Die nicht generische Version von <xref:System.Activities.Statements.ForEach%601> bewältigt diese Anforderung zulasten einer größeren Laufzeitkomplexität zum Sicherstellen der Kompatibilität der Typen der Werte in der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="1ea6e-106">The non-generic version of <xref:System.Activities.Statements.ForEach%601> overcomes this requirement, at the expense of more run-time complexity for ensuring the compatibility of the types of the values in the collection.</span></span>  
  
 <span data-ttu-id="1ea6e-107">In diesem Beispiel wird gezeigt, wie eine nicht generische <xref:System.Activities.Statements.ForEach%601>-Aktivität und der Designer implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="1ea6e-107">This sample shows how to implement a non-generic <xref:System.Activities.Statements.ForEach%601> activity and its designer.</span></span> <span data-ttu-id="1ea6e-108">Diese Aktivität kann zum Durchlaufen von <xref:System.Collections.ArrayList> verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1ea6e-108">This activity can be used to iterate through <xref:System.Collections.ArrayList>.</span></span>  
  
## <a name="foreach-activity"></a><span data-ttu-id="1ea6e-109">ForEach-Aktivität</span><span class="sxs-lookup"><span data-stu-id="1ea6e-109">ForEach Activity</span></span>  
 <span data-ttu-id="1ea6e-110">Die C#/VB-Anweisung `foreach` zählt die Elemente einer Auflistung auf und führt eine eingebettete Anweisung für jedes Element der Auflistung aus.</span><span class="sxs-lookup"><span data-stu-id="1ea6e-110">The C#/VB `foreach` statement enumerates the elements of a collection, executing an embedded statement for each element of the collection.</span></span> <span data-ttu-id="1ea6e-111">Die entsprechenden [!INCLUDE[wf1](../../../../includes/wf1-md.md)]-Aktivitäten für `foreach` sind <xref:System.Activities.Statements.ForEach%601> und <xref:System.Activities.Statements.ParallelForEach%601>.</span><span class="sxs-lookup"><span data-stu-id="1ea6e-111">The [!INCLUDE[wf1](../../../../includes/wf1-md.md)] equivalent activities of `foreach` are <xref:System.Activities.Statements.ForEach%601> and <xref:System.Activities.Statements.ParallelForEach%601>.</span></span> <span data-ttu-id="1ea6e-112">Die <xref:System.Activities.Statements.ForEach%601>-Aktivität enthält eine Liste von Werten und einen Text.</span><span class="sxs-lookup"><span data-stu-id="1ea6e-112">The <xref:System.Activities.Statements.ForEach%601> activity contains a list of values and a body.</span></span> <span data-ttu-id="1ea6e-113">Zur Laufzeit wird die Liste durchlaufen, und der Text wird für jeden Wert in der Liste ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1ea6e-113">At runtime, the list is iterated and the body is executed for each value in the list.</span></span>  
  
 <span data-ttu-id="1ea6e-114">In den meisten Fällen sollte die generische Version der Aktivität die bevorzugte Lösung sein, da die meisten Szenarien, in denen sie verwendet wird, damit abgedeckt werden und sie zur Kompilierzeit eine Typüberprüfung bietet.</span><span class="sxs-lookup"><span data-stu-id="1ea6e-114">For most cases, the generic version of the activity should be the preferred solution, because it covers most of the scenarios in which it would be used, and provides type checking at compile time.</span></span> <span data-ttu-id="1ea6e-115">Die nicht generische Version kann zum Durchlaufen von Typen, die die nicht generische <xref:System.Collections.IEnumerable>-Schnittstelle implementieren, verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1ea6e-115">The non-generic version can be used for iterating through types that implement the non-generic <xref:System.Collections.IEnumerable> interface.</span></span>  
  
## <a name="class-definition"></a><span data-ttu-id="1ea6e-116">Klassendefinition</span><span class="sxs-lookup"><span data-stu-id="1ea6e-116">Class Definition</span></span>  
 <span data-ttu-id="1ea6e-117">Im folgenden Codebeispiel wird die Definition einer nicht generischen `ForEach`-Aktivität veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="1ea6e-117">The following code example shows the definition of a non-generic `ForEach` activity.</span></span>  
  
```  
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
  
 <span data-ttu-id="1ea6e-118">Text (optional)</span><span class="sxs-lookup"><span data-stu-id="1ea6e-118">Body (optional)</span></span>  
 <span data-ttu-id="1ea6e-119">Das <xref:System.Activities.ActivityAction>-Element mit dem Typ <xref:System.Object>, das für jedes Element in der Auflistung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1ea6e-119">The <xref:System.Activities.ActivityAction> of type <xref:System.Object>, which is executed for each element in the collection.</span></span> <span data-ttu-id="1ea6e-120">Jedes einzelne Element wird durch die `Argument`-Eigenschaft in den Text übergeben.</span><span class="sxs-lookup"><span data-stu-id="1ea6e-120">Each individual element is passed into the Body through its `Argument` property.</span></span>  
  
 <span data-ttu-id="1ea6e-121">Werte (optional)</span><span class="sxs-lookup"><span data-stu-id="1ea6e-121">Values (optional)</span></span>  
 <span data-ttu-id="1ea6e-122">Die Auflistung von Elementen, die durchlaufen werden.</span><span class="sxs-lookup"><span data-stu-id="1ea6e-122">The collection of elements that are iterated over.</span></span> <span data-ttu-id="1ea6e-123">Die Sicherstellung, dass alle Elemente der Auflistung kompatible Typen aufweisen, erfolgt zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="1ea6e-123">Ensuring that all elements of the collection are of compatible types is done at run-time.</span></span>  
  
## <a name="example-of-using-foreach"></a><span data-ttu-id="1ea6e-124">Beispiel der Verwendung von ForEach</span><span class="sxs-lookup"><span data-stu-id="1ea6e-124">Example of Using ForEach</span></span>  
 <span data-ttu-id="1ea6e-125">Im folgenden Code wird veranschaulicht, wie die ForEach-Aktivität in einer Anwendung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1ea6e-125">The following code demonstrates how to use the ForEach activity in an application.</span></span>  
  
```  
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
  
|<span data-ttu-id="1ea6e-126">Bedingung</span><span class="sxs-lookup"><span data-stu-id="1ea6e-126">Condition</span></span>|<span data-ttu-id="1ea6e-127">Meldung</span><span class="sxs-lookup"><span data-stu-id="1ea6e-127">Message</span></span>|<span data-ttu-id="1ea6e-128">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="1ea6e-128">Severity</span></span>|<span data-ttu-id="1ea6e-129">Ausnahmetyp</span><span class="sxs-lookup"><span data-stu-id="1ea6e-129">Exception Type</span></span>|  
|---------------|-------------|--------------|--------------------|  
|<span data-ttu-id="1ea6e-130">Werte sind `null`</span><span class="sxs-lookup"><span data-stu-id="1ea6e-130">Values is `null`</span></span>|<span data-ttu-id="1ea6e-131">Für das erforderliche Aktivitätsargument "Values1" wurde kein Wert angegeben.</span><span class="sxs-lookup"><span data-stu-id="1ea6e-131">Value for a required activity argument 'Values' was not supplied.</span></span>|<span data-ttu-id="1ea6e-132">Fehler</span><span class="sxs-lookup"><span data-stu-id="1ea6e-132">Error</span></span>|<xref:System.InvalidOperationException>|  
  
## <a name="foreach-designer"></a><span data-ttu-id="1ea6e-133">ForEach-Designer</span><span class="sxs-lookup"><span data-stu-id="1ea6e-133">ForEach Designer</span></span>  
 <span data-ttu-id="1ea6e-134">Der Aktivitätsdesigner für das Beispiel ist dem Designer im Aussehen ähnlich, der für die integrierte <xref:System.Activities.Statements.ForEach%601>-Aktivität dient.</span><span class="sxs-lookup"><span data-stu-id="1ea6e-134">The activity designer for the sample is similar in appearance to the designer provided for the built-in <xref:System.Activities.Statements.ForEach%601> activity.</span></span> <span data-ttu-id="1ea6e-135">Der Designer wird angezeigt, in der Toolbox in die **Beispiele**, **nicht generische Aktivitäten** Kategorie.</span><span class="sxs-lookup"><span data-stu-id="1ea6e-135">The designer appears in the toolbox in the **Samples**, **Non-Generic Activities** category.</span></span> <span data-ttu-id="1ea6e-136">Der Designer ist mit dem Namen **ForEachWithBodyFactory** in der Toolbox, da die Aktivität stellt eine <xref:System.Activities.Presentation.IActivityTemplateFactory> in der Toolbox erstellt die die Aktivität mit einem ordnungsgemäß konfigurierten <xref:System.Activities.ActivityAction>.</span><span class="sxs-lookup"><span data-stu-id="1ea6e-136">The designer is named **ForEachWithBodyFactory** in the toolbox, because the activity exposes an <xref:System.Activities.Presentation.IActivityTemplateFactory> in the toolbox, which creates the activity with a properly configured <xref:System.Activities.ActivityAction>.</span></span>  
  
```  
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
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="1ea6e-137">So führen Sie dieses Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="1ea6e-137">To run this sample</span></span>  
  
1.  <span data-ttu-id="1ea6e-138">Legen Sie das Projekt Ihrer Wahl als Startprojekt der Projektmappe fest:</span><span class="sxs-lookup"><span data-stu-id="1ea6e-138">Set the project of your choice as the start-up project of the solution:</span></span>  
  
    1.  <span data-ttu-id="1ea6e-139">**CodeTestClient** zeigt, wie die Aktivität mit Code.</span><span class="sxs-lookup"><span data-stu-id="1ea6e-139">**CodeTestClient** shows how to use the activity using code.</span></span>  
  
    2.  <span data-ttu-id="1ea6e-140">**DesignerTestClient** wird gezeigt, wie die Aktivität im Designer verwendet.</span><span class="sxs-lookup"><span data-stu-id="1ea6e-140">**DesignerTestClient** shows how to use the activity within the designer.</span></span>  
  
2.  <span data-ttu-id="1ea6e-141">Erstellen Sie das Projekt, und führen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="1ea6e-141">Build and run the project.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1ea6e-142">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="1ea6e-142">The samples may already be installed on your machine.</span></span> <span data-ttu-id="1ea6e-143">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="1ea6e-143">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="1ea6e-144">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="1ea6e-144">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1ea6e-145">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="1ea6e-145">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\NonGenericForEach`
