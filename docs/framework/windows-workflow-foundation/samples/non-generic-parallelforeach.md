---
title: ParallelForEach (nicht generisch)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: de17e7a2-257b-48b3-91a1-860e2e9bf6e6
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2c8c02c920eda881f4a08925e3bff0567244e5c5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="non-generic-parallelforeach"></a><span data-ttu-id="fe525-102">ParallelForEach (nicht generisch)</span><span class="sxs-lookup"><span data-stu-id="fe525-102">Non-Generic ParallelForEach</span></span>
[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]<span data-ttu-id="fe525-103">geliefert wird in der Toolbox einen Satz von ablaufsteuerungsaktivitäten, einschließlich <xref:System.Activities.Statements.ParallelForEach%601>, womit durchlaufen <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` Sammlungen.</span><span class="sxs-lookup"><span data-stu-id="fe525-103"> ships in its toolbox a set of Control Flow activities, including <xref:System.Activities.Statements.ParallelForEach%601>, which allows iterating through <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` collections.</span></span>  
  
 <span data-ttu-id="fe525-104"><xref:System.Activities.Statements.ParallelForEach%601>erfordert die <xref:System.Activities.Statements.ParallelForEach%601.Values%2A> Eigenschaft vom Typ <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable`.</span><span class="sxs-lookup"><span data-stu-id="fe525-104"><xref:System.Activities.Statements.ParallelForEach%601> requires its <xref:System.Activities.Statements.ParallelForEach%601.Values%2A> property to be of type <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable`.</span></span> <span data-ttu-id="fe525-105">Dies schließt Benutzer davon, von Datenstrukturen, die implementieren durchlaufen <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` Schnittstelle (z. B. <xref:System.Collections.ArrayList>).</span><span class="sxs-lookup"><span data-stu-id="fe525-105">This precludes users from iterating over data structures that implement <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` interface (for example, <xref:System.Collections.ArrayList>).</span></span> <span data-ttu-id="fe525-106">Die nicht generische Version von <xref:System.Activities.Statements.ParallelForEach%601> bewältigt diese Anforderung zulasten einer größeren Laufzeitkomplexität zum Sicherstellen der Kompatibilität der Typen der Werte in der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="fe525-106">The non-generic version of <xref:System.Activities.Statements.ParallelForEach%601> overcomes this requirement, at the expense of more run-time complexity for ensuring the compatibility of the types of the values in the collection.</span></span>  
  
 <span data-ttu-id="fe525-107">In diesem Beispiel wird gezeigt, wie eine nicht generische <xref:System.Activities.Statements.ParallelForEach%601>-Aktivität und der Designer implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="fe525-107">This sample shows how to implement a non-generic <xref:System.Activities.Statements.ParallelForEach%601> activity and its designer.</span></span> <span data-ttu-id="fe525-108">Diese Aktivität kann zum Durchlaufen von <xref:System.Collections.ArrayList> verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fe525-108">This activity can be used to iterate through <xref:System.Collections.ArrayList>.</span></span>  
  
## <a name="parallelforeach-activity"></a><span data-ttu-id="fe525-109">Die ParallelForEachT-Aktivität</span><span class="sxs-lookup"><span data-stu-id="fe525-109">ParallelForEach Activity</span></span>  
 <span data-ttu-id="fe525-110">Die C#/VB-Anweisung `foreach` zählt die Elemente einer Auflistung auf und führt eine eingebettete Anweisung für jedes Element der Auflistung aus.</span><span class="sxs-lookup"><span data-stu-id="fe525-110">The C#/VB `foreach` statement enumerates the elements of a collection, executing an embedded statement for each element of the collection.</span></span> <span data-ttu-id="fe525-111">Die entsprechenden [!INCLUDE[wf1](../../../../includes/wf1-md.md)]-Aktivitäten sind <xref:System.Activities.Statements.ForEach%601> und <xref:System.Activities.Statements.ParallelForEach%601>.</span><span class="sxs-lookup"><span data-stu-id="fe525-111">The [!INCLUDE[wf1](../../../../includes/wf1-md.md)] equivalent activities are <xref:System.Activities.Statements.ForEach%601> and <xref:System.Activities.Statements.ParallelForEach%601>.</span></span> <span data-ttu-id="fe525-112">Die <xref:System.Activities.Statements.ForEach%601>-Aktivität enthält eine Liste von Werten und einen Text.</span><span class="sxs-lookup"><span data-stu-id="fe525-112">The <xref:System.Activities.Statements.ForEach%601> activity contains a list of values and a body.</span></span> <span data-ttu-id="fe525-113">Zur Laufzeit wird die Liste durchlaufen, und der Text wird für jeden Wert in der Liste ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="fe525-113">At runtime, the list is iterated and the body is executed for each value in the list.</span></span>  
  
 <span data-ttu-id="fe525-114"><xref:System.Activities.Statements.ParallelForEach%601> weist eine <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> auf, damit die <xref:System.Activities.Statements.ParallelForEach%601>-Aktivität vorzeitig abgeschlossen werden kann, wenn die Auswertung der <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> `true` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="fe525-114"><xref:System.Activities.Statements.ParallelForEach%601> has a <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A>, so that the <xref:System.Activities.Statements.ParallelForEach%601> activity could complete early if the evaluation of the <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> returns `true`.</span></span> <span data-ttu-id="fe525-115">Die <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> wird nach dem Abschluss jeder Iteration ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="fe525-115">The <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> is evaluated after each iteration is completed.</span></span>  
  
 <span data-ttu-id="fe525-116">In den meisten Fällen sollte die generische Version der Aktivität die bevorzugte Lösung sein, da die meisten Szenarien, in denen sie verwendet wird, damit abgedeckt werden und sie zur Kompilierzeit eine Typüberprüfung bietet.</span><span class="sxs-lookup"><span data-stu-id="fe525-116">For most cases, the generic version of the activity should be the preferred solution, because it covers most of the scenarios in which it is used and provides type checking at compile time.</span></span> <span data-ttu-id="fe525-117">Die nicht generische Version kann zum Durchlaufen von Typen, die die nicht generische <xref:System.Collections.IEnumerable>-Schnittstelle implementieren, verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fe525-117">The non-generic version can be used for iterating through types that implement the non-generic <xref:System.Collections.IEnumerable> interface.</span></span>  
  
## <a name="class-definition"></a><span data-ttu-id="fe525-118">Klassendefinition</span><span class="sxs-lookup"><span data-stu-id="fe525-118">Class Definition</span></span>  
 <span data-ttu-id="fe525-119">Im folgenden Codebeispiel wird die Definition einer nicht generischen `ParallelForEach`-Aktivität veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="fe525-119">The following code example shows the definition of a non-generic `ParallelForEach` activity is.</span></span>  
  
```  
[ContentProperty("Body")]  
public class ParallelForEach : NativeActivity  
{  
    [RequiredArgument]  
    [DefaultValue(null)]  
    InArgument<IEnumerable> Values { get; set; }  
  
    [DefaultValue(null)]  
    [DependsOn("Values")]  
    public Activity<bool> CompletionCondition  
    [DefaultValue(null)]  
    [DependsOn("CompletionCondition")]  
    ActivityAction<object> Body { get; set; }   
}  
```  
  
 <span data-ttu-id="fe525-120">Text (optional)</span><span class="sxs-lookup"><span data-stu-id="fe525-120">Body (optional)</span></span>  
 <span data-ttu-id="fe525-121">Das <xref:System.Activities.ActivityAction>-Element mit dem Typ <xref:System.Object>, das für jedes Element in der Auflistung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fe525-121">The <xref:System.Activities.ActivityAction> of type <xref:System.Object>, which is executed for each element in the collection.</span></span> <span data-ttu-id="fe525-122">Jedes einzelne Element wird durch die Argument-Eigenschaft in den Text übergeben.</span><span class="sxs-lookup"><span data-stu-id="fe525-122">Each individual element is passed into the Body through its Argument property.</span></span>  
  
 <span data-ttu-id="fe525-123">Werte (optional)</span><span class="sxs-lookup"><span data-stu-id="fe525-123">Values (optional)</span></span>  
 <span data-ttu-id="fe525-124">Die Auflistung von Elementen, die durchlaufen werden.</span><span class="sxs-lookup"><span data-stu-id="fe525-124">The collection of elements that are iterated over.</span></span> <span data-ttu-id="fe525-125">Die Sicherstellung, dass alle Elemente der Auflistung kompatible Typen aufweisen, erfolgt zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="fe525-125">Ensuring that all elements of the collection are of compatible types is done at run-time.</span></span>  
  
 <span data-ttu-id="fe525-126">CompletionCondition (optional)</span><span class="sxs-lookup"><span data-stu-id="fe525-126">CompletionCondition (optional)</span></span>  
 <span data-ttu-id="fe525-127">Die <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A>-Eigenschaft wird ausgewertet, nachdem eine Iteration abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="fe525-127">The <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> property is evaluated after any iteration completes.</span></span> <span data-ttu-id="fe525-128">Ergibt die Auswertung `true`, werden die geplanten ausstehenden Iterationen abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="fe525-128">If it evaluates to `true`, then the scheduled pending iterations are canceled.</span></span> <span data-ttu-id="fe525-129">Wenn diese Eigenschaft nicht festgelegt ist, werden alle Aktivitäten in der Verzweigungsauflistung bis zur Beendigung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="fe525-129">If this property is not set, all activities in the Branches collection execute until completion.</span></span>  
  
## <a name="example-of-using-parallelforeach"></a><span data-ttu-id="fe525-130">Beispiel für die Verwendung von ParallelForEach</span><span class="sxs-lookup"><span data-stu-id="fe525-130">Example of Using ParallelForEach</span></span>  
 <span data-ttu-id="fe525-131">Im folgenden Code wird veranschaulicht, wie die ParallelForEach-Aktivität in einer Anwendung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fe525-131">The following code demonstrates how to use the ParallelForEach activity in an application.</span></span>  
  
```  
string[] names = { "bill", "steve", "ray" };  
  
DelegateInArgument<object> iterationVariable = new DelegateInArgument<object>() { Name = "iterationVariable" };  
  
Activity sampleUsage =  
    new ParallelForEach  
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
  
## <a name="parallelforeach-designer"></a><span data-ttu-id="fe525-132">ParallelForEach-Designer</span><span class="sxs-lookup"><span data-stu-id="fe525-132">ParallelForEach Designer</span></span>  
 <span data-ttu-id="fe525-133">Der Aktivitätsdesigner für das Beispiel ist dem Designer im Aussehen ähnlich, der für die integrierte <xref:System.Activities.Statements.ParallelForEach%601>-Aktivität dient.</span><span class="sxs-lookup"><span data-stu-id="fe525-133">The activity designer for the sample is similar in appearance to the designer provided for the built-in <xref:System.Activities.Statements.ParallelForEach%601> activity.</span></span> <span data-ttu-id="fe525-134">Der Designer wird angezeigt, in der Toolbox unter die **Beispiele**, **nicht generische Aktivitäten** Kategorie.</span><span class="sxs-lookup"><span data-stu-id="fe525-134">The designer appears in the toolbox in the **Samples**, **Non-Generic Activities** category.</span></span> <span data-ttu-id="fe525-135">Der Designer ist mit dem Namen **ParallelForEachWithBodyFactory** in der Toolbox, da die Aktivität macht eine <xref:System.Activities.Presentation.IActivityTemplateFactory> in der Toolbox, die mit einem ordnungsgemäß konfigurierten Aktivität erstellt <xref:System.Activities.ActivityAction>.</span><span class="sxs-lookup"><span data-stu-id="fe525-135">The designer is named **ParallelForEachWithBodyFactory** in the toolbox, because the activity exposes an <xref:System.Activities.Presentation.IActivityTemplateFactory> in the toolbox that creates the activity with a properly configured <xref:System.Activities.ActivityAction>.</span></span>  
  
```  
public sealed class ParallelForEachWithBodyFactory : IActivityTemplateFactory  
{  
    public Activity Create(DependencyObject target)  
    {  
        return new Microsoft.Samples.Activities.Statements.ParallelForEach()  
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
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="fe525-136">So führen Sie das Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="fe525-136">To run the sample</span></span>  
  
1.  <span data-ttu-id="fe525-137">Legen Sie das Projekt Ihrer Wahl als Startprojekt der Projektmappe fest:</span><span class="sxs-lookup"><span data-stu-id="fe525-137">Set the project of your choice as the startup project of the solution.</span></span>  
  
    1.  <span data-ttu-id="fe525-138">**CodeTestClient** wird gezeigt, wie die Aktivität mit Code zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="fe525-138">**CodeTestClient** shows how to use the activity using code.</span></span>  
  
    2.  <span data-ttu-id="fe525-139">**DesignerTestClient** wird gezeigt, wie die Aktivität im Designer verwendet.</span><span class="sxs-lookup"><span data-stu-id="fe525-139">**DesignerTestClient** shows how to use the activity within the designer.</span></span>  
  
2.  <span data-ttu-id="fe525-140">Erstellen Sie das Projekt, und führen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="fe525-140">Build and run the project.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fe525-141">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="fe525-141">The samples may already be installed on your machine.</span></span> <span data-ttu-id="fe525-142">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="fe525-142">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="fe525-143">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="fe525-143">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="fe525-144">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="fe525-144">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\NonGenericParallelForEach`
