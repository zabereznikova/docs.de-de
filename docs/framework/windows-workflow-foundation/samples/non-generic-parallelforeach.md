---
title: ParallelForEach (nicht generisch)
ms.date: 03/30/2017
ms.assetid: de17e7a2-257b-48b3-91a1-860e2e9bf6e6
ms.openlocfilehash: 70d5de587dda3cb61205a8d77f2173df9b93498b
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44210584"
---
# <a name="non-generic-parallelforeach"></a><span data-ttu-id="34d9d-102">ParallelForEach (nicht generisch)</span><span class="sxs-lookup"><span data-stu-id="34d9d-102">Non-Generic ParallelForEach</span></span>
[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]<span data-ttu-id="34d9d-103"> ausgeliefert wird in der Toolbox einen Satz von ablaufsteuerungsaktivitäten, einschließlich <xref:System.Activities.Statements.ParallelForEach%601>, wodurch durchlaufen <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` Sammlungen.</span><span class="sxs-lookup"><span data-stu-id="34d9d-103"> ships in its toolbox a set of Control Flow activities, including <xref:System.Activities.Statements.ParallelForEach%601>, which allows iterating through <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` collections.</span></span>  
  
 <span data-ttu-id="34d9d-104"><xref:System.Activities.Statements.ParallelForEach%601> erfordert die <xref:System.Activities.Statements.ParallelForEach%601.Values%2A> Eigenschaft vom Typ <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable`.</span><span class="sxs-lookup"><span data-stu-id="34d9d-104"><xref:System.Activities.Statements.ParallelForEach%601> requires its <xref:System.Activities.Statements.ParallelForEach%601.Values%2A> property to be of type <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable`.</span></span> <span data-ttu-id="34d9d-105">Dies verhindert, dass Benutzer durchlaufen-Datenstrukturen, die implementieren <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` Schnittstelle (z. B. <xref:System.Collections.ArrayList>).</span><span class="sxs-lookup"><span data-stu-id="34d9d-105">This precludes users from iterating over data structures that implement <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` interface (for example, <xref:System.Collections.ArrayList>).</span></span> <span data-ttu-id="34d9d-106">Die nicht generische Version von <xref:System.Activities.Statements.ParallelForEach%601> bewältigt diese Anforderung zulasten einer größeren Laufzeitkomplexität zum Sicherstellen der Kompatibilität der Typen der Werte in der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="34d9d-106">The non-generic version of <xref:System.Activities.Statements.ParallelForEach%601> overcomes this requirement, at the expense of more run-time complexity for ensuring the compatibility of the types of the values in the collection.</span></span>  
  
 <span data-ttu-id="34d9d-107">In diesem Beispiel wird gezeigt, wie eine nicht generische <xref:System.Activities.Statements.ParallelForEach%601>-Aktivität und der Designer implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="34d9d-107">This sample shows how to implement a non-generic <xref:System.Activities.Statements.ParallelForEach%601> activity and its designer.</span></span> <span data-ttu-id="34d9d-108">Diese Aktivität kann zum Durchlaufen von <xref:System.Collections.ArrayList> verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="34d9d-108">This activity can be used to iterate through <xref:System.Collections.ArrayList>.</span></span>  
  
## <a name="parallelforeach-activity"></a><span data-ttu-id="34d9d-109">Die ParallelForEachT-Aktivität</span><span class="sxs-lookup"><span data-stu-id="34d9d-109">ParallelForEach Activity</span></span>  
 <span data-ttu-id="34d9d-110">Die C#/VB-Anweisung `foreach` zählt die Elemente einer Auflistung auf und führt eine eingebettete Anweisung für jedes Element der Auflistung aus.</span><span class="sxs-lookup"><span data-stu-id="34d9d-110">The C#/VB `foreach` statement enumerates the elements of a collection, executing an embedded statement for each element of the collection.</span></span> <span data-ttu-id="34d9d-111">Die entsprechenden [!INCLUDE[wf1](../../../../includes/wf1-md.md)]-Aktivitäten sind <xref:System.Activities.Statements.ForEach%601> und <xref:System.Activities.Statements.ParallelForEach%601>.</span><span class="sxs-lookup"><span data-stu-id="34d9d-111">The [!INCLUDE[wf1](../../../../includes/wf1-md.md)] equivalent activities are <xref:System.Activities.Statements.ForEach%601> and <xref:System.Activities.Statements.ParallelForEach%601>.</span></span> <span data-ttu-id="34d9d-112">Die <xref:System.Activities.Statements.ForEach%601>-Aktivität enthält eine Liste von Werten und einen Text.</span><span class="sxs-lookup"><span data-stu-id="34d9d-112">The <xref:System.Activities.Statements.ForEach%601> activity contains a list of values and a body.</span></span> <span data-ttu-id="34d9d-113">Zur Laufzeit wird die Liste durchlaufen, und der Text wird für jeden Wert in der Liste ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="34d9d-113">At runtime, the list is iterated and the body is executed for each value in the list.</span></span>  
  
 <span data-ttu-id="34d9d-114"><xref:System.Activities.Statements.ParallelForEach%601> weist eine <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> auf, damit die <xref:System.Activities.Statements.ParallelForEach%601>-Aktivität vorzeitig abgeschlossen werden kann, wenn die Auswertung der <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> `true` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="34d9d-114"><xref:System.Activities.Statements.ParallelForEach%601> has a <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A>, so that the <xref:System.Activities.Statements.ParallelForEach%601> activity could complete early if the evaluation of the <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> returns `true`.</span></span> <span data-ttu-id="34d9d-115">Die <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> wird nach dem Abschluss jeder Iteration ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="34d9d-115">The <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> is evaluated after each iteration is completed.</span></span>  
  
 <span data-ttu-id="34d9d-116">In den meisten Fällen sollte die generische Version der Aktivität die bevorzugte Lösung sein, da die meisten Szenarien, in denen sie verwendet wird, damit abgedeckt werden und sie zur Kompilierzeit eine Typüberprüfung bietet.</span><span class="sxs-lookup"><span data-stu-id="34d9d-116">For most cases, the generic version of the activity should be the preferred solution, because it covers most of the scenarios in which it is used and provides type checking at compile time.</span></span> <span data-ttu-id="34d9d-117">Die nicht generische Version kann zum Durchlaufen von Typen, die die nicht generische <xref:System.Collections.IEnumerable>-Schnittstelle implementieren, verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="34d9d-117">The non-generic version can be used for iterating through types that implement the non-generic <xref:System.Collections.IEnumerable> interface.</span></span>  
  
## <a name="class-definition"></a><span data-ttu-id="34d9d-118">Klassendefinition</span><span class="sxs-lookup"><span data-stu-id="34d9d-118">Class Definition</span></span>  
 <span data-ttu-id="34d9d-119">Im folgenden Codebeispiel wird die Definition einer nicht generischen `ParallelForEach`-Aktivität veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="34d9d-119">The following code example shows the definition of a non-generic `ParallelForEach` activity is.</span></span>  
  
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
  
 <span data-ttu-id="34d9d-120">Text (optional)</span><span class="sxs-lookup"><span data-stu-id="34d9d-120">Body (optional)</span></span>  
 <span data-ttu-id="34d9d-121">Das <xref:System.Activities.ActivityAction>-Element mit dem Typ <xref:System.Object>, das für jedes Element in der Auflistung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="34d9d-121">The <xref:System.Activities.ActivityAction> of type <xref:System.Object>, which is executed for each element in the collection.</span></span> <span data-ttu-id="34d9d-122">Jedes einzelne Element wird durch die Argument-Eigenschaft in den Text übergeben.</span><span class="sxs-lookup"><span data-stu-id="34d9d-122">Each individual element is passed into the Body through its Argument property.</span></span>  
  
 <span data-ttu-id="34d9d-123">Werte (optional)</span><span class="sxs-lookup"><span data-stu-id="34d9d-123">Values (optional)</span></span>  
 <span data-ttu-id="34d9d-124">Die Auflistung von Elementen, die durchlaufen werden.</span><span class="sxs-lookup"><span data-stu-id="34d9d-124">The collection of elements that are iterated over.</span></span> <span data-ttu-id="34d9d-125">Die Sicherstellung, dass alle Elemente der Auflistung kompatible Typen aufweisen, erfolgt zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="34d9d-125">Ensuring that all elements of the collection are of compatible types is done at run-time.</span></span>  
  
 <span data-ttu-id="34d9d-126">CompletionCondition (optional)</span><span class="sxs-lookup"><span data-stu-id="34d9d-126">CompletionCondition (optional)</span></span>  
 <span data-ttu-id="34d9d-127">Die <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A>-Eigenschaft wird ausgewertet, nachdem eine Iteration abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="34d9d-127">The <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> property is evaluated after any iteration completes.</span></span> <span data-ttu-id="34d9d-128">Ergibt die Auswertung `true`, werden die geplanten ausstehenden Iterationen abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="34d9d-128">If it evaluates to `true`, then the scheduled pending iterations are canceled.</span></span> <span data-ttu-id="34d9d-129">Wenn diese Eigenschaft nicht festgelegt ist, werden alle Aktivitäten in der Verzweigungsauflistung bis zur Beendigung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="34d9d-129">If this property is not set, all activities in the Branches collection execute until completion.</span></span>  
  
## <a name="example-of-using-parallelforeach"></a><span data-ttu-id="34d9d-130">Beispiel für die Verwendung von ParallelForEach</span><span class="sxs-lookup"><span data-stu-id="34d9d-130">Example of Using ParallelForEach</span></span>  
 <span data-ttu-id="34d9d-131">Im folgenden Code wird veranschaulicht, wie die ParallelForEach-Aktivität in einer Anwendung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="34d9d-131">The following code demonstrates how to use the ParallelForEach activity in an application.</span></span>  
  
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
  
## <a name="parallelforeach-designer"></a><span data-ttu-id="34d9d-132">ParallelForEach-Designer</span><span class="sxs-lookup"><span data-stu-id="34d9d-132">ParallelForEach Designer</span></span>  
 <span data-ttu-id="34d9d-133">Der Aktivitätsdesigner für das Beispiel ist dem Designer im Aussehen ähnlich, der für die integrierte <xref:System.Activities.Statements.ParallelForEach%601>-Aktivität dient.</span><span class="sxs-lookup"><span data-stu-id="34d9d-133">The activity designer for the sample is similar in appearance to the designer provided for the built-in <xref:System.Activities.Statements.ParallelForEach%601> activity.</span></span> <span data-ttu-id="34d9d-134">Der Designer wird angezeigt, in der Toolbox in die **Beispiele**, **nicht generische Aktivitäten** Kategorie.</span><span class="sxs-lookup"><span data-stu-id="34d9d-134">The designer appears in the toolbox in the **Samples**, **Non-Generic Activities** category.</span></span> <span data-ttu-id="34d9d-135">Der Designer ist mit dem Namen **ParallelForEachWithBodyFactory** in der Toolbox, da die Aktivität stellt eine <xref:System.Activities.Presentation.IActivityTemplateFactory> in der Toolbox, die die Aktivität mit einem ordnungsgemäß konfigurierten erstellt <xref:System.Activities.ActivityAction>.</span><span class="sxs-lookup"><span data-stu-id="34d9d-135">The designer is named **ParallelForEachWithBodyFactory** in the toolbox, because the activity exposes an <xref:System.Activities.Presentation.IActivityTemplateFactory> in the toolbox that creates the activity with a properly configured <xref:System.Activities.ActivityAction>.</span></span>  
  
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
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="34d9d-136">So führen Sie das Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="34d9d-136">To run the sample</span></span>  
  
1.  <span data-ttu-id="34d9d-137">Legen Sie das Projekt Ihrer Wahl als Startprojekt der Projektmappe fest:</span><span class="sxs-lookup"><span data-stu-id="34d9d-137">Set the project of your choice as the startup project of the solution.</span></span>  
  
    1.  <span data-ttu-id="34d9d-138">**CodeTestClient** zeigt, wie die Aktivität mit Code.</span><span class="sxs-lookup"><span data-stu-id="34d9d-138">**CodeTestClient** shows how to use the activity using code.</span></span>  
  
    2.  <span data-ttu-id="34d9d-139">**DesignerTestClient** wird gezeigt, wie die Aktivität im Designer verwendet.</span><span class="sxs-lookup"><span data-stu-id="34d9d-139">**DesignerTestClient** shows how to use the activity within the designer.</span></span>  
  
2.  <span data-ttu-id="34d9d-140">Erstellen Sie das Projekt, und führen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="34d9d-140">Build and run the project.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="34d9d-141">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="34d9d-141">The samples may already be installed on your machine.</span></span> <span data-ttu-id="34d9d-142">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="34d9d-142">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="34d9d-143">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="34d9d-143">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="34d9d-144">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="34d9d-144">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\NonGenericParallelForEach`
