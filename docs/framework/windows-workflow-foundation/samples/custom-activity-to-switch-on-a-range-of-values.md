---
title: Benutzerdefinierte Aktivität zum Aktivieren eines Wertebereichs
ms.date: 03/30/2017
ms.assetid: 441e0a17-421f-430c-ba97-59e4cc6c88e3
ms.openlocfilehash: cfaf4318b1557a9fc217de8254e164243ea54569
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43563399"
---
# <a name="custom-activity-to-switch-on-a-range-of-values"></a><span data-ttu-id="9691b-102">Benutzerdefinierte Aktivität zum Aktivieren eines Wertebereichs</span><span class="sxs-lookup"><span data-stu-id="9691b-102">Custom Activity to Switch on a Range of Values</span></span>
<span data-ttu-id="9691b-103">Anhand dieses Beispiels wird veranschaulicht, wie eine benutzerdefinierte Aktivität, die die Verwendung eines <xref:System.Activities.Statements.Switch%601>-Elements erweitert, erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="9691b-103">This sample demonstrates how to create a custom activity that extends the use of a <xref:System.Activities.Statements.Switch%601>.</span></span> <span data-ttu-id="9691b-104">Eine herkömmliche <xref:System.Activities.Statements.Switch%601>-Anweisung ermöglicht den auf einem einzelnen Wert basierenden Wechsel.</span><span class="sxs-lookup"><span data-stu-id="9691b-104">A conventional <xref:System.Activities.Statements.Switch%601> statement allows switching based upon a single value.</span></span> <span data-ttu-id="9691b-105">In einigen Szenarios muss eine Aktivität jedoch basierend auf einem Wertebereich einen Wechsel ausführen.</span><span class="sxs-lookup"><span data-stu-id="9691b-105">But, there are business scenarios where an activity must switch based upon a range of values.</span></span> <span data-ttu-id="9691b-106">Beispiel: Eine Aktivität führt eine Aktion aus, wenn der Wert zwischen 1 und 5 liegt, eine andere Aktion, wenn der Wert zwischen 6 und 10 liegt, und eine Standardaktion für alle anderen Werte.</span><span class="sxs-lookup"><span data-stu-id="9691b-106">For example, an activity might execute one action when the value being switched upon is between 1 and 5, another action when the value is between 6 and 10, and a default action for all other values.</span></span> <span data-ttu-id="9691b-107">Diese benutzerdefinierte Aktivität ermöglicht genau dieses Szenario.</span><span class="sxs-lookup"><span data-stu-id="9691b-107">This custom activity enables exactly that scenario.</span></span>  
  
## <a name="the-switchrange-activity"></a><span data-ttu-id="9691b-108">Die SwitchRange-Aktivität</span><span class="sxs-lookup"><span data-stu-id="9691b-108">The SwitchRange Activity</span></span>  
 <span data-ttu-id="9691b-109">Die `SwitchRange`-Aktivität plant eine untergeordnete Aktivität, wenn der Ergebniswert des Ausdrucks innerhalb des Bereichs von einem der `Cases` liegt.</span><span class="sxs-lookup"><span data-stu-id="9691b-109">The `SwitchRange` activity schedules a child activity when the result value of its expression is included within the range of one of its `Cases`.</span></span>  
  
 <span data-ttu-id="9691b-110">Das folgende Codebeispiel ist eine benutzerdefinierte Aktivität, die auf Basis eines Wertebereichs einen Wechsel ausführt.</span><span class="sxs-lookup"><span data-stu-id="9691b-110">The following code example is a custom activity that switches based upon a range of values.</span></span>  
  
```csharp  
public sealed class SwitchRange<T> : NativeActivity where T : IComparable  
{  
   [RequiredArgument]  
   [DefaultValue(null)]  
   public InArgument<T> Expression { get; set; }  
  
   public IList<CaseRange<T>> Cases  
  
   [DefaultValue(null)]  
   public Activity Default { get; set; }}  
}  
```  
  
|<span data-ttu-id="9691b-111">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="9691b-111">Property</span></span>|<span data-ttu-id="9691b-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9691b-112">Description</span></span>|  
|-|-|  
|<span data-ttu-id="9691b-113">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="9691b-113">Expression</span></span>|<span data-ttu-id="9691b-114">Der Ausdruck, der ausgewertet und mit den Wertebereichen in der Cases-Liste verglichen wird.</span><span class="sxs-lookup"><span data-stu-id="9691b-114">This is the expression to be evaluated and compared against the ranges in the Cases list.</span></span> <span data-ttu-id="9691b-115">Das Ergebnis dieses Ausdrucks ist vom Typ "T".</span><span class="sxs-lookup"><span data-stu-id="9691b-115">The result of the expression is of type T.</span></span>|  
|<span data-ttu-id="9691b-116">Cases</span><span class="sxs-lookup"><span data-stu-id="9691b-116">Cases</span></span>|<span data-ttu-id="9691b-117">Jeder "Fall" besteht aus einem Bereich (Von-Bis) und einer Aktivität (Text).</span><span class="sxs-lookup"><span data-stu-id="9691b-117">Each case consists of a range (From and To) and an activity (Body).</span></span> <span data-ttu-id="9691b-118">Der Ausdruck wird ausgewertet und mit den Wertebereichen verglichen.</span><span class="sxs-lookup"><span data-stu-id="9691b-118">The expression is evaluated and compared against the ranges.</span></span> <span data-ttu-id="9691b-119">Wenn das Ergebnis des Ausdrucks innerhalb des Wertebereichs von einem der Fälle liegt, wird die entsprechende Aktivität ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9691b-119">If the result of the expression is within the range of one of the cases, the corresponding activity is executed.</span></span>|  
|<span data-ttu-id="9691b-120">Standard</span><span class="sxs-lookup"><span data-stu-id="9691b-120">Default</span></span>|<span data-ttu-id="9691b-121">Die Aktivität, die ausgeführt wird, wenn das Ergebnis mit keinem Fall in der Cases-Liste übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="9691b-121">The activity that is executed when no case is matched.</span></span> <span data-ttu-id="9691b-122">Wenn Sie diese Eigenschaft auf `null` festlegen, wird keine Aktion ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9691b-122">When set to `null`, no action is taken.</span></span>|  
  
## <a name="caserange-class"></a><span data-ttu-id="9691b-123">CaseRange-Klasse</span><span class="sxs-lookup"><span data-stu-id="9691b-123">CaseRange Class</span></span>  
 <span data-ttu-id="9691b-124">Die `CaseRange`-Klasse stellt einen Bereich innerhalb einer `SwitchRange`-Aktivität dar.</span><span class="sxs-lookup"><span data-stu-id="9691b-124">The `CaseRange` class represents a range within a `SwitchRange` activity.</span></span> <span data-ttu-id="9691b-125">Jede `CaseRange`-Instanz enthält einen Wertebereich (zwischen `From` und `To`) und eine Aktivität (`Body`), die ausgeführt wird, wenn das Ergebnis des Ausdrucks der `SwitchRange`-Aktivität innerhalb des Wertebereichs liegt.</span><span class="sxs-lookup"><span data-stu-id="9691b-125">Every instance of `CaseRange` contains a range (composed of a `From` and a `To`) and a `Body` activity that is scheduled if the expression in the `SwitchRange` is evaluated within the range.</span></span>  
  
 <span data-ttu-id="9691b-126">Das folgende Codebeispiel stellt die Definition der `CaseRange`-Klasse dar.</span><span class="sxs-lookup"><span data-stu-id="9691b-126">The following code example is the definition for the `CaseRange` class.</span></span>  
  
```  
public class CaseRange<T> where T : IComparable  
{  
    public T From { get; set; }  
  
    public T To { get; set; }  
  
    public Activity Action { get; set; }  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="9691b-127">Sowohl die `SwitchRange`-Klasse als auch die `CaseRange`-Klasse, die im Beispiel definiert werden, sind generische Klassen, die jeden Typ unterstützen, der `IComparable` implementiert, wie die <xref:System.Activities.Statements.Switch%601>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="9691b-127">Both the `SwitchRange` and `CaseRange` classes, which are defined in the sample are generic classes that can work with any type that implements `IComparable`, like the <xref:System.Activities.Statements.Switch%601> class.</span></span>  
  
## <a name="sample-usage"></a><span data-ttu-id="9691b-128">Verwendung des Beispiels</span><span class="sxs-lookup"><span data-stu-id="9691b-128">Sample Usage</span></span>  
 <span data-ttu-id="9691b-129">Das folgende Codebeispiel zeigt, wie Sie die `SwitchRange`-Aktivität verwenden.</span><span class="sxs-lookup"><span data-stu-id="9691b-129">The following code example demonstrates how to use the `SwitchRange` activity.</span></span>  
  
```csharp  
Activity SwitchRange = new SwitchRange<int>  
{  
    Expression = new InArgument<int>(value),  
    Cases =   
    {  
        new CaseRange<int>                      
        {  
            From = 1,  
            To = 5,  
            Action = new WriteLine  
            {  
                Text = "Case 1-5 selected",  
            }  
        },  
        new CaseRange<int>  
        {  
            From = 6,  
            To = 10,  
            Action = new WriteLine  
            {  
                Text = "Case 6-10 selected",  
            }  
        }  
    },  
    Default = new WriteLine { Text = "Default Case selected" }  
};  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="9691b-130">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="9691b-130">To use this sample</span></span>  
  
1.  <span data-ttu-id="9691b-131">Öffnen Sie in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "SwitchRange.sln".</span><span class="sxs-lookup"><span data-stu-id="9691b-131">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the SwitchRange.sln solution file.</span></span>  
  
2.  <span data-ttu-id="9691b-132">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9691b-132">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="9691b-133">Drücken Sie STRG+F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="9691b-133">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9691b-134">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="9691b-134">The samples may already be installed on your machine.</span></span> <span data-ttu-id="9691b-135">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="9691b-135">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="9691b-136">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="9691b-136">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9691b-137">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="9691b-137">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\SwitchRange`