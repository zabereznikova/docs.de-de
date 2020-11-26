---
title: Auswahlaktivität
description: In Workflow Foundation vereinfacht die Pick-Aktivität die Modellierung eines Satzes von Ereignis Triggern, gefolgt von den entsprechenden Handlern.
ms.date: 03/30/2017
ms.assetid: b3e49b7f-0285-4720-8c09-11ae18f0d53e
ms.openlocfilehash: 6fc31679c20e24115e790bb50b0b5fa8dd62c705
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96246133"
---
# <a name="pick-activity"></a><span data-ttu-id="bb190-103">Auswahlaktivität</span><span class="sxs-lookup"><span data-stu-id="bb190-103">Pick Activity</span></span>

<span data-ttu-id="bb190-104">Die <xref:System.Activities.Statements.Pick>-Aktivität vereinfacht die Modellierung einer Gruppe von Ereignistriggern gefolgt von den entsprechenden Handlern.</span><span class="sxs-lookup"><span data-stu-id="bb190-104">The <xref:System.Activities.Statements.Pick> activity simplifies the modeling of a set of event triggers followed by their corresponding handlers.</span></span>  <span data-ttu-id="bb190-105">Eine <xref:System.Activities.Statements.Pick>-Aktivität enthält eine Auflistung von <xref:System.Activities.Statements.PickBranch>-Aktivitäten, wobei jedes <xref:System.Activities.Statements.PickBranch>-Objekt eine Paarung einer <xref:System.Activities.Statements.PickBranch.Trigger%2A>-Aktivität und einer <xref:System.Activities.Statements.PickBranch.Action%2A>-Aktivität darstellt.</span><span class="sxs-lookup"><span data-stu-id="bb190-105">A <xref:System.Activities.Statements.Pick> activity contains a collection of <xref:System.Activities.Statements.PickBranch> activities, where each <xref:System.Activities.Statements.PickBranch> is a pairing between a <xref:System.Activities.Statements.PickBranch.Trigger%2A> activity and an <xref:System.Activities.Statements.PickBranch.Action%2A> activity.</span></span>  <span data-ttu-id="bb190-106">Bei der Ausführung werden die Trigger für alle Branches parallel ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="bb190-106">At execution time, the triggers for all branches are executed in parallel.</span></span>  <span data-ttu-id="bb190-107">Nach Abschluss eines Triggers wird die zugeordnete Aktion ausgeführt, und alle anderen Trigger werden abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="bb190-107">When one trigger completes, then its corresponding action is executed, and all other triggers are canceled.</span></span>  <span data-ttu-id="bb190-108">Das Verhalten der- [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] <xref:System.Activities.Statements.Pick> Aktivität ähnelt der .NET Framework 3,5- <xref:System.Workflow.Activities.ListenActivity> Aktivität.</span><span class="sxs-lookup"><span data-stu-id="bb190-108">The behavior of the [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]<xref:System.Activities.Statements.Pick> activity is similar to the .NET Framework 3.5 <xref:System.Workflow.Activities.ListenActivity> activity.</span></span>  
  
 <span data-ttu-id="bb190-109">Der folgende Screenshot aus dem SDK-Beispiel [Verwenden der Pick-Aktivität](./samples/using-the-pick-activity.md) zeigt eine Pick-Aktivität mit zwei Branches.</span><span class="sxs-lookup"><span data-stu-id="bb190-109">The following screenshot from the [Using the Pick Activity](./samples/using-the-pick-activity.md) SDK sample shows a Pick activity with two branches.</span></span>  <span data-ttu-id="bb190-110">Ein Branch verfügt über einen Trigger mit dem Namen **Read input**, eine benutzerdefinierte Aktivität, die Eingaben aus der Befehlszeile liest.</span><span class="sxs-lookup"><span data-stu-id="bb190-110">One branch has a trigger called **Read input**, a custom activity that reads input from the command line.</span></span> <span data-ttu-id="bb190-111">Der zweite Branch verfügt über einen <xref:System.Activities.Statements.Delay>-Aktivitätstrigger.</span><span class="sxs-lookup"><span data-stu-id="bb190-111">The second branch has a <xref:System.Activities.Statements.Delay> activity trigger.</span></span> <span data-ttu-id="bb190-112">Wenn die **Read Input** -Aktivität Daten empfängt, bevor die <xref:System.Activities.Statements.Delay> Aktivität abgeschlossen ist, wird die <xref:System.Activities.Statements.Delay> Verzögerung abgebrochen, und es wird eine Begrüßung in die Konsole geschrieben.</span><span class="sxs-lookup"><span data-stu-id="bb190-112">If the **Read input** activity receives data before the <xref:System.Activities.Statements.Delay> activity finishes, <xref:System.Activities.Statements.Delay> Delay will be canceled and a greeting will be written to the console.</span></span>  <span data-ttu-id="bb190-113">Die Aktivität **Read input** wird jedoch abgebrochen und eine Timeoutmeldung in die Konsole geschrieben, wenn die Aktivität in der zugewiesenen Zeit keine Daten empfängt.</span><span class="sxs-lookup"><span data-stu-id="bb190-113">Otherwise, if the **Read input** activity does not receive data in the allotted time, then it will be canceled and a timeout message will be written to the console.</span></span>  <span data-ttu-id="bb190-114">Dies ist ein allgemeines Muster, mit dem einer beliebigen Aktion ein Timeoutverhalten hinzugefügt werden kann.</span><span class="sxs-lookup"><span data-stu-id="bb190-114">This is a common pattern used to add a timeout to any action.</span></span>  
  
 ![Auswahlaktivität](./media/pick-activity/pick-activity-two-branches.jpg)  
  
## <a name="best-practices"></a><span data-ttu-id="bb190-116">Bewährte Methoden</span><span class="sxs-lookup"><span data-stu-id="bb190-116">Best practices</span></span>  

 <span data-ttu-id="bb190-117">Bei Verwendung der Pick-Option ist die ausgeführte Verzweigung diejenige, deren Trigger zuerst abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="bb190-117">When using Pick, the branch that executes is the branch whose trigger completes first.</span></span>  <span data-ttu-id="bb190-118">Vom Konzept her werden alle Trigger parallel ausgeführt. Ein Trigger hat möglicherweise den Großteil seiner Logik ausgeführt, bevor er durch den Abschluss eines anderen Triggers abgebrochen wird.</span><span class="sxs-lookup"><span data-stu-id="bb190-118">Conceptually, all triggers execute in parallel, and one trigger may have executed the majority of its logic before it is canceled by the completion of another trigger.</span></span>  <span data-ttu-id="bb190-119">Unter Beachtung dieser Option gilt als allgemeine Richtlinie für die Verwendung einer Pick-Aktivität, dass der Trigger als Einzelereignis behandelt werden sollte und so wenig Logik wie möglich enthalten sein sollte.</span><span class="sxs-lookup"><span data-stu-id="bb190-119">With this in mind, a general guideline to follow when using the Pick activity is to treat the trigger as representing a single event, and to put as little logic as possible into it.</span></span>  <span data-ttu-id="bb190-120">Im Idealfall enthält der Trigger gerade genügend Logik, um ein Ereignis empfangen zu können. Die gesamte Verarbeitung des Ereignisses sollte in der Aktion der Verzweigung erfolgen.</span><span class="sxs-lookup"><span data-stu-id="bb190-120">Ideally, the trigger should contain just enough logic to receive an event, and all the processing of that event should go into the action of the branch.</span></span>  <span data-ttu-id="bb190-121">Auf diese Weise kann der Grad der Überschneidung bei der Ausführung der Trigger minimiert werden.</span><span class="sxs-lookup"><span data-stu-id="bb190-121">This method minimizes the amount of overlap between the execution of the triggers.</span></span>  <span data-ttu-id="bb190-122">Nehmen Sie z. B. ein <xref:System.Activities.Statements.Pick>-Objekt mit zwei Triggern an, wobei jeder Trigger eine <xref:System.ServiceModel.Activities.Receive>-Aktivität und darauf folgend zusätzliche Logik enthält.</span><span class="sxs-lookup"><span data-stu-id="bb190-122">For example, consider a <xref:System.Activities.Statements.Pick> with two triggers, where each trigger contains a <xref:System.ServiceModel.Activities.Receive> activity followed by additional logic.</span></span>  <span data-ttu-id="bb190-123">Wenn die zusätzliche Logik einen Leerlaufpunkt einführt, können beide <xref:System.ServiceModel.Activities.Receive>-Aktivitäten erfolgreich abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="bb190-123">If the additional logic introduces an idle point, then there is the possibility of both <xref:System.ServiceModel.Activities.Receive> activities completing successfully.</span></span>  <span data-ttu-id="bb190-124">Ein Trigger wird vollständig abgeschlossen, während ein anderer nur teilweise abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="bb190-124">One trigger will fully complete, while another will partially complete.</span></span>  <span data-ttu-id="bb190-125">In einigen Szenarien ist es nicht zulässig, dass eine Meldung angenommen und die Verarbeitung nur teilweise abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="bb190-125">In some scenarios, accepting a message, and then partially completing the processing of it is unacceptable.</span></span>  <span data-ttu-id="bb190-126">Wenn daher die integrierten WF-Messagingaktivitäten wie <xref:System.ServiceModel.Activities.Receive> und <xref:System.ServiceModel.Activities.SendReply> verwendet, während <xref:System.ServiceModel.Activities.Receive> häufig im Trigger verwendet wird, sollten das <xref:System.ServiceModel.Activities.SendReply>-Objekt und andere Logik nach Möglichkeit der Aktion hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="bb190-126">Therefore, when using WF built-in messaging activities such as <xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply>, while <xref:System.ServiceModel.Activities.Receive> is commonly used in the trigger, <xref:System.ServiceModel.Activities.SendReply> and other logic should be put in the action whenever possible.</span></span>  
  
## <a name="using-the-pick-activity-in-the-designer"></a><span data-ttu-id="bb190-127">Verwenden der Pick-Aktivität im Designer</span><span class="sxs-lookup"><span data-stu-id="bb190-127">Using the Pick activity in the designer</span></span>  

 <span data-ttu-id="bb190-128">Um die Pick-Aktivität im Designer verwenden zu können, suchen Sie in der Toolbox nach **Pick** und **PickBranch**.</span><span class="sxs-lookup"><span data-stu-id="bb190-128">To use Pick in the designer, find **Pick** and **PickBranch** in the toolbox.</span></span>  <span data-ttu-id="bb190-129">Ziehen Sie **Pick** per Drag & Drop auf die Canvas.</span><span class="sxs-lookup"><span data-stu-id="bb190-129">Drag and drop **Pick** onto the canvas.</span></span>  <span data-ttu-id="bb190-130">Standardmäßig enthält eine neue **Pick**-Aktivität im Designer zwei Branches.</span><span class="sxs-lookup"><span data-stu-id="bb190-130">By default, a new **Pick** Activity in the designer will contain two branches.</span></span>  <span data-ttu-id="bb190-131">Um zusätzliche Branches hinzuzufügen, ziehen Sie die **PickBranch**-Aktivität per Drag & Drop neben vorhandene Branches.</span><span class="sxs-lookup"><span data-stu-id="bb190-131">To add additional branches, drag the **PickBranch** activity and drop it next to existing branches.</span></span> <span data-ttu-id="bb190-132">Aktivitäten können für die **Pick**-Aktivität entweder im Bereich **Trigger** oder im Bereich **Aktion** einer **PickBranch** abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="bb190-132">Activities can be dropped onto the **Pick** Activity into either the **Trigger** area or the **Action** area of any **PickBranch**.</span></span>  
  
## <a name="using-the-pick-activity-in-code"></a><span data-ttu-id="bb190-133">Verwenden der Pick-Aktivität im Code</span><span class="sxs-lookup"><span data-stu-id="bb190-133">Using the Pick Activity in code</span></span>  

 <span data-ttu-id="bb190-134">Die <xref:System.Activities.Statements.Pick>-Aktivität wird verwendet, indem die zugehörige <xref:System.Activities.Statements.Pick.Branches%2A>-Auflistung mit <xref:System.Activities.Statements.PickBranch>-Aktivitäten aufgefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="bb190-134">The <xref:System.Activities.Statements.Pick> activity is used by populating its <xref:System.Activities.Statements.Pick.Branches%2A> collection with <xref:System.Activities.Statements.PickBranch> activities.</span></span> <span data-ttu-id="bb190-135">Die <xref:System.Activities.Statements.PickBranch>-Aktivitäten verfügen jeweils über eine <xref:System.Activities.Statements.PickBranch.Trigger%2A>-Eigenschaft des Typs <xref:System.Activities.Activity>.</span><span class="sxs-lookup"><span data-stu-id="bb190-135">The <xref:System.Activities.Statements.PickBranch> activities each have a <xref:System.Activities.Statements.PickBranch.Trigger%2A> property of type <xref:System.Activities.Activity>.</span></span> <span data-ttu-id="bb190-136">Wenn die Ausführung der angegebenen Aktivität abgeschlossen wird, wird die <xref:System.Activities.Statements.PickBranch.Action%2A> ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="bb190-136">When the specified activity completes execution, the <xref:System.Activities.Statements.PickBranch.Action%2A> executes.</span></span>  
  
 <span data-ttu-id="bb190-137">Im folgenden Codebeispiel wird demonstriert, wie mit einer <xref:System.Activities.Statements.Pick>-Aktivität ein Timeout für eine Aktivität implementiert wird, die eine Zeile aus der Konsole liest.</span><span class="sxs-lookup"><span data-stu-id="bb190-137">The following code example demonstrates how to use a <xref:System.Activities.Statements.Pick> activity to implement a timeout for an activity that reads a line from the console.</span></span>  
  
```csharp  
Sequence body = new Sequence()  
{  
    Variables = { name },  
    Activities =
   {  
       new System.Activities.Statements.Pick  
        {  
           Branches =
           {  
               new PickBranch  
               {  
                   Trigger = new ReadLine  
                   {  
                      Result = name,  
                      BookmarkName = "name"  
                   },  
                   Action = new WriteLine
                   {
                       Text = ExpressionServices.Convert<string>(ctx => "Hello " +
                           name.Get(ctx))
                   }  
               },  
               new PickBranch  
               {  
                   Trigger = new Delay  
                   {  
                      Duration = new TimeSpan(0, 0, 5)  
                   },  
                   Action = new WriteLine  
                   {  
                      Text = "Time is up."  
                   }  
               }  
           }  
       }  
   }  
};  
```  
  
```xaml  
<Sequence xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <Sequence.Variables>  
    <Variable x:TypeArguments="x:String" Name="username" />  
  </Sequence.Variables>  
  <Pick>  
    <PickBranch>  
      <PickBranch.Trigger>  
        <ReadLine BookmarkName="name" Result="username" />  
      </PickBranch.Trigger>  
      <WriteLine>[String.Concat("Hello ", username)]</WriteLine>  
    </PickBranch>  
    <PickBranch>  
      <PickBranch.Trigger>  
        <Delay>00:00:05</Delay>  
      </PickBranch.Trigger>  
      <WriteLine>Time is up.</WriteLine>  
    </PickBranch>  
  </Pick>  
</Sequence>  
```
