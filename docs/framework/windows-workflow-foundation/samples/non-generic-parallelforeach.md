---
title: Nicht generisches ParallelForEach
ms.date: 03/30/2017
ms.assetid: de17e7a2-257b-48b3-91a1-860e2e9bf6e6
ms.openlocfilehash: ea7f57b8812dca3dfcb4908730dd788182d50c5c
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347616"
---
# <a name="non-generic-parallelforeach"></a><span data-ttu-id="701a5-102">Nicht generisches ParallelForEach</span><span class="sxs-lookup"><span data-stu-id="701a5-102">Non-generic ParallelForEach</span></span>

<span data-ttu-id="701a5-103">Zur Toolbox von [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] gehört ein Satz von Ablaufsteuerungsaktivitäten, einschließlich <xref:System.Activities.Statements.ParallelForEach%601>, die das Durchlaufen von <xref:System.Collections.Generic.IEnumerable%601>-Auflistungen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="701a5-103">[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] ships in its toolbox a set of Control Flow activities, including <xref:System.Activities.Statements.ParallelForEach%601>, which allows iterating through <xref:System.Collections.Generic.IEnumerable%601> collections.</span></span>

<span data-ttu-id="701a5-104"><xref:System.Activities.Statements.ParallelForEach%601> erfordert, dass die <xref:System.Activities.Statements.ParallelForEach%601.Values%2A>-Eigenschaft vom Typ <xref:System.Collections.Generic.IEnumerable%601>ist.</span><span class="sxs-lookup"><span data-stu-id="701a5-104"><xref:System.Activities.Statements.ParallelForEach%601> requires its <xref:System.Activities.Statements.ParallelForEach%601.Values%2A> property to be of type  <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="701a5-105">Dies schließt Benutzer davon aus, Datenstrukturen zu durchlaufen, die die <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle implementieren (z. B. <xref:System.Collections.ArrayList>).</span><span class="sxs-lookup"><span data-stu-id="701a5-105">This precludes users from iterating over data structures that implement <xref:System.Collections.Generic.IEnumerable%601> interface (for example, <xref:System.Collections.ArrayList>).</span></span> <span data-ttu-id="701a5-106">Die nicht generische Version von <xref:System.Activities.Statements.ParallelForEach%601> bewältigt diese Anforderung zulasten einer größeren Laufzeitkomplexität zum Sicherstellen der Kompatibilität der Typen der Werte in der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="701a5-106">The non-generic version of <xref:System.Activities.Statements.ParallelForEach%601> overcomes this requirement, at the expense of more run-time complexity for ensuring the compatibility of the types of the values in the collection.</span></span>

<span data-ttu-id="701a5-107">In diesem Beispiel wird gezeigt, wie eine nicht generische <xref:System.Activities.Statements.ParallelForEach%601>-Aktivität und der Designer implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="701a5-107">This sample shows how to implement a non-generic <xref:System.Activities.Statements.ParallelForEach%601> activity and its designer.</span></span> <span data-ttu-id="701a5-108">Diese Aktivität kann zum Durchlaufen von <xref:System.Collections.ArrayList> verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="701a5-108">This activity can be used to iterate through <xref:System.Collections.ArrayList>.</span></span>

## <a name="parallelforeach-activity"></a><span data-ttu-id="701a5-109">ParallelForEach-Aktivität</span><span class="sxs-lookup"><span data-stu-id="701a5-109">ParallelForEach activity</span></span>

<span data-ttu-id="701a5-110">Die C#/Visual Basic `foreach`-Anweisung zählt die Elemente einer Auflistung auf und führt eine eingebettete Anweisung für jedes Element der Auflistung aus.</span><span class="sxs-lookup"><span data-stu-id="701a5-110">The C#/Visual Basic `foreach` statement enumerates the elements of a collection, executing an embedded statement for each element of the collection.</span></span> <span data-ttu-id="701a5-111">Die entsprechenden [!INCLUDE[wf1](../../../../includes/wf1-md.md)]-Aktivitäten sind <xref:System.Activities.Statements.ForEach%601> und <xref:System.Activities.Statements.ParallelForEach%601>.</span><span class="sxs-lookup"><span data-stu-id="701a5-111">The [!INCLUDE[wf1](../../../../includes/wf1-md.md)] equivalent activities are <xref:System.Activities.Statements.ForEach%601> and <xref:System.Activities.Statements.ParallelForEach%601>.</span></span> <span data-ttu-id="701a5-112">Die <xref:System.Activities.Statements.ForEach%601>-Aktivität enthält eine Liste von Werten und einen Text.</span><span class="sxs-lookup"><span data-stu-id="701a5-112">The <xref:System.Activities.Statements.ForEach%601> activity contains a list of values and a body.</span></span> <span data-ttu-id="701a5-113">Zur Laufzeit wird die Liste durchlaufen, und der Text wird für jeden Wert in der Liste ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="701a5-113">At runtime, the list is iterated and the body is executed for each value in the list.</span></span>

<span data-ttu-id="701a5-114"><xref:System.Activities.Statements.ParallelForEach%601> weist eine <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> auf, damit die <xref:System.Activities.Statements.ParallelForEach%601>-Aktivität vorzeitig abgeschlossen werden kann, wenn die Auswertung der <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A>`true` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="701a5-114"><xref:System.Activities.Statements.ParallelForEach%601> has a <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A>, so that the <xref:System.Activities.Statements.ParallelForEach%601> activity could complete early if the evaluation of the <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> returns `true`.</span></span> <span data-ttu-id="701a5-115">Die <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> wird nach dem Abschluss jeder Iteration ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="701a5-115">The <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> is evaluated after each iteration is completed.</span></span>

<span data-ttu-id="701a5-116">In den meisten Fällen sollte die generische Version der Aktivität die bevorzugte Lösung sein, da die meisten Szenarien, in denen sie verwendet wird, damit abgedeckt werden und sie zur Kompilierzeit eine Typüberprüfung bietet.</span><span class="sxs-lookup"><span data-stu-id="701a5-116">For most cases, the generic version of the activity should be the preferred solution, because it covers most of the scenarios in which it is used and provides type checking at compile time.</span></span> <span data-ttu-id="701a5-117">Die nicht generische Version kann zum Durchlaufen von Typen, die die nicht generische <xref:System.Collections.IEnumerable>-Schnittstelle implementieren, verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="701a5-117">The non-generic version can be used for iterating through types that implement the non-generic <xref:System.Collections.IEnumerable> interface.</span></span>

## <a name="class-definition"></a><span data-ttu-id="701a5-118">Klassendefinition</span><span class="sxs-lookup"><span data-stu-id="701a5-118">Class definition</span></span>

<span data-ttu-id="701a5-119">Im folgenden Codebeispiel wird die Definition einer nicht generischen `ParallelForEach`-Aktivität veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="701a5-119">The following code example shows the definition of a non-generic `ParallelForEach` activity is.</span></span>

```csharp
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

<span data-ttu-id="701a5-120">Body (optional) </span><span class="sxs-lookup"><span data-stu-id="701a5-120">Body (optional)</span></span>\
<span data-ttu-id="701a5-121">Das <xref:System.Activities.ActivityAction>-Element mit dem Typ <xref:System.Object>, das für jedes Element in der Auflistung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="701a5-121">The <xref:System.Activities.ActivityAction> of type <xref:System.Object>, which is executed for each element in the collection.</span></span> <span data-ttu-id="701a5-122">Jedes einzelne Element wird durch die Argument-Eigenschaft in den Text übergeben.</span><span class="sxs-lookup"><span data-stu-id="701a5-122">Each individual element is passed into the Body through its Argument property.</span></span>

<span data-ttu-id="701a5-123">Werte (optional) </span><span class="sxs-lookup"><span data-stu-id="701a5-123">Values (optional)</span></span>\
<span data-ttu-id="701a5-124">Die Auflistung von Elementen, die durchlaufen werden.</span><span class="sxs-lookup"><span data-stu-id="701a5-124">The collection of elements that are iterated over.</span></span> <span data-ttu-id="701a5-125">Die Sicherstellung, dass alle Elemente der Auflistung kompatible Typen aufweisen, erfolgt zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="701a5-125">Ensuring that all elements of the collection are of compatible types is done at run-time.</span></span>

<span data-ttu-id="701a5-126">CompletionCondition (optional) </span><span class="sxs-lookup"><span data-stu-id="701a5-126">CompletionCondition (optional)</span></span>\
<span data-ttu-id="701a5-127">Die <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A>-Eigenschaft wird ausgewertet, nachdem eine Iteration abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="701a5-127">The <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> property is evaluated after any iteration completes.</span></span> <span data-ttu-id="701a5-128">Ergibt die Auswertung `true`, werden die geplanten ausstehenden Iterationen abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="701a5-128">If it evaluates to `true`, then the scheduled pending iterations are canceled.</span></span> <span data-ttu-id="701a5-129">Wenn diese Eigenschaft nicht festgelegt ist, werden alle Aktivitäten in der Branchauflistung bis zur Beendigung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="701a5-129">If this property is not set, all activities in the Branches collection execute until completion.</span></span>

## <a name="example-of-using-parallelforeach"></a><span data-ttu-id="701a5-130">Beispiel für die Verwendung von ParallelForEach</span><span class="sxs-lookup"><span data-stu-id="701a5-130">Example of using ParallelForEach</span></span>

<span data-ttu-id="701a5-131">Im folgenden Code wird veranschaulicht, wie die ParallelForEach-Aktivität in einer Anwendung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="701a5-131">The following code demonstrates how to use the ParallelForEach activity in an application.</span></span>

```csharp
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

## <a name="parallelforeach-designer"></a><span data-ttu-id="701a5-132">ParallelForEach-Designer</span><span class="sxs-lookup"><span data-stu-id="701a5-132">ParallelForEach designer</span></span>

<span data-ttu-id="701a5-133">Der Aktivitätsdesigner für das Beispiel ist dem Designer im Aussehen ähnlich, der für die integrierte <xref:System.Activities.Statements.ParallelForEach%601>-Aktivität dient.</span><span class="sxs-lookup"><span data-stu-id="701a5-133">The activity designer for the sample is similar in appearance to the designer provided for the built-in <xref:System.Activities.Statements.ParallelForEach%601> activity.</span></span> <span data-ttu-id="701a5-134">Der Designer wird in der Toolbox in der Kategorie **Beispiele**, **nicht generische Aktivitäten** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="701a5-134">The designer appears in the toolbox in the **Samples**, **Non-Generic Activities** category.</span></span> <span data-ttu-id="701a5-135">Der Designer hat den Namen **ParallelForEachWithBodyFactory** in der Toolbox, da die-Aktivität eine <xref:System.Activities.Presentation.IActivityTemplateFactory> in der Toolbox verfügbar macht, mit der die-Aktivität mit einem ordnungsgemäß konfigurierten <xref:System.Activities.ActivityAction>erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="701a5-135">The designer is named **ParallelForEachWithBodyFactory** in the toolbox, because the activity exposes an <xref:System.Activities.Presentation.IActivityTemplateFactory> in the toolbox that creates the activity with a properly configured <xref:System.Activities.ActivityAction>.</span></span>

```csharp
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

## <a name="to-run-the-sample"></a><span data-ttu-id="701a5-136">So führen Sie das Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="701a5-136">To run the sample</span></span>

1. <span data-ttu-id="701a5-137">Legen Sie das Projekt Ihrer Wahl als Startprojekt der Projektmappe fest:</span><span class="sxs-lookup"><span data-stu-id="701a5-137">Set the project of your choice as the startup project of the solution.</span></span>

    1. <span data-ttu-id="701a5-138">**Codetestclient** zeigt, wie die-Aktivität mithilfe von Code verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="701a5-138">**CodeTestClient** shows how to use the activity using code.</span></span>

    2. <span data-ttu-id="701a5-139">**Designertestclient** zeigt, wie die-Aktivität innerhalb des Designers verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="701a5-139">**DesignerTestClient** shows how to use the activity within the designer.</span></span>

2. <span data-ttu-id="701a5-140">Erstellen Sie das Projekt, und führen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="701a5-140">Build and run the project.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="701a5-141">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="701a5-141">The samples may already be installed on your machine.</span></span> <span data-ttu-id="701a5-142">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="701a5-142">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="701a5-143">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="701a5-143">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="701a5-144">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="701a5-144">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\NonGenericParallelForEach`
