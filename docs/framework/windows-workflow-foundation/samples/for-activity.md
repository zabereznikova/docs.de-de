---
title: For-Aktivität
ms.date: 03/30/2017
ms.assetid: 2ea751b4-36f0-48aa-a115-70a2ab89f6d8
ms.openlocfilehash: c79f295e7880f845c606a55f9c56ad65350f9c52
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33515444"
---
# <a name="for-activity"></a><span data-ttu-id="dd959-102">For-Aktivität</span><span class="sxs-lookup"><span data-stu-id="dd959-102">For Activity</span></span>
<span data-ttu-id="dd959-103">Im For-Beispiel wird veranschaulicht, wie eine benutzerdefinierte Aktivität erstellt wird, die von <xref:System.Activities.NativeActivity> erbt, und wie diese in einem Workflow verwendet wird, um ein Beispiel mit realen Bedingungen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="dd959-103">The For sample demonstrates how to build a custom activity that inherits from <xref:System.Activities.NativeActivity>, and use it in a workflow to execute a real world example.</span></span> <span data-ttu-id="dd959-104">Die benutzerdefinierte Aktivität in diesem Beispiel funktioniert wie die `for`-Anweisung in C#.</span><span class="sxs-lookup"><span data-stu-id="dd959-104">The custom activity included in this sample functions like the C# `for` statement.</span></span> <span data-ttu-id="dd959-105">T</span><span class="sxs-lookup"><span data-stu-id="dd959-105">T</span></span>  
  
 <span data-ttu-id="dd959-106">Die benutzerdefinierte `For`-Aktivität weist die Eigenschaften `InitAction`, `IterationAction`, `Condition` und `Body` auf, die jeweils der Initialisierungsanweisung, der iterativen Anweisung, der Fortsetzungsbedingung und der Textanweisung in der standardmäßigen `For`-Anweisung in C# entsprechen.</span><span class="sxs-lookup"><span data-stu-id="dd959-106">The `For` custom activity has properties named `InitAction`, `IterationAction`, `Condition`, and `Body` that correspond to the initialization statement, iterative statement, continuation condition, and body statement respectively found in the standard C# `For` statement.</span></span>  
  
 <span data-ttu-id="dd959-107">In der folgenden Tabelle sind die im Beispiel verwendeten Schlüsseldateien beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dd959-107">The following table describes the key files in the sample.</span></span>  
  
|<span data-ttu-id="dd959-108">Datei</span><span class="sxs-lookup"><span data-stu-id="dd959-108">File</span></span>|<span data-ttu-id="dd959-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dd959-109">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="dd959-110">For.cs</span><span class="sxs-lookup"><span data-stu-id="dd959-110">For.cs</span></span>|<span data-ttu-id="dd959-111">Klassendefinition für die benutzerdefinierte `For`-Aktivität, die durch Erweiterung der <xref:System.Activities.NativeActivity>-Klasse die Funktionalität der `For`-Anweisung in C# bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="dd959-111">Class definition for the `For` custom activity, which extends the <xref:System.Activities.NativeActivity> class to provide the functionality of the C# `For` statement.</span></span>|  
|<span data-ttu-id="dd959-112">Program.cs</span><span class="sxs-lookup"><span data-stu-id="dd959-112">Program.cs</span></span>|<span data-ttu-id="dd959-113">Eine Clientanwendung, die unter Verwendung der benutzerdefinierten `For`-Aktivität grundlegende iterative Verarbeitungsschritte für eine Auflistung ausführt.</span><span class="sxs-lookup"><span data-stu-id="dd959-113">A client application that performs basic iterative work on a collection using the custom `For` activity.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="dd959-114">Stellen Sie bei Verwendung der benutzerdefinierten `For`-Aktivität sicher, dass die `Condition`-Eigenschaft festgelegt ist. Andernfalls kann eine Endlosschleife auftreten.</span><span class="sxs-lookup"><span data-stu-id="dd959-114">When using the `For` custom activity, ensure that the `Condition` property is set; otherwise an infinite loop could occur.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="dd959-115">Veranschaulicht</span><span class="sxs-lookup"><span data-stu-id="dd959-115">Demonstrates</span></span>  
 <span data-ttu-id="dd959-116">Erstellen einer benutzerdefinierten Aktivität, die von <xref:System.Activities.NativeActivity> erbt.</span><span class="sxs-lookup"><span data-stu-id="dd959-116">Create a custom activity that inherits from <xref:System.Activities.NativeActivity>.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="dd959-117">Diskussion</span><span class="sxs-lookup"><span data-stu-id="dd959-117">Discussion</span></span>  
 <span data-ttu-id="dd959-118">In der folgenden Tabelle werden die Eigenschaften der Aktivität in diesem Beispiel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dd959-118">The following table describes the properties of the activity included in this sample.</span></span>  
  
 <span data-ttu-id="dd959-119">InitAction</span><span class="sxs-lookup"><span data-stu-id="dd959-119">InitAction</span></span>  
 <span data-ttu-id="dd959-120">Initialisierungsanweisung</span><span class="sxs-lookup"><span data-stu-id="dd959-120">Initialization statement</span></span>  
  
 <span data-ttu-id="dd959-121">IterationAction</span><span class="sxs-lookup"><span data-stu-id="dd959-121">IterationAction</span></span>  
 <span data-ttu-id="dd959-122">Iterative Anweisung</span><span class="sxs-lookup"><span data-stu-id="dd959-122">Iterative statement</span></span>  
  
 <span data-ttu-id="dd959-123">Bedingung</span><span class="sxs-lookup"><span data-stu-id="dd959-123">Condition</span></span>  
 <span data-ttu-id="dd959-124">Fortsetzungsanweisung</span><span class="sxs-lookup"><span data-stu-id="dd959-124">Continuation statement</span></span>  
  
 <span data-ttu-id="dd959-125">Body</span><span class="sxs-lookup"><span data-stu-id="dd959-125">Body</span></span>  
 <span data-ttu-id="dd959-126">Textanweisung</span><span class="sxs-lookup"><span data-stu-id="dd959-126">Body statement</span></span>  
  
 <span data-ttu-id="dd959-127">Die Aktivität erbt von <xref:System.Activities.NativeActivity>, um mittels einer der `ScheduleActivity`-Methoden von <xref:System.Activities.NativeActivityContext> Zugriff auf Laufzeitfunktionen zu erhalten, z. B. zur Planung zusätzlicher auszuführender Aktivitäten.</span><span class="sxs-lookup"><span data-stu-id="dd959-127">The activity inherits from <xref:System.Activities.NativeActivity> to gain access to runtime features such as scheduling additional activities to run, using one of the `ScheduleActivity` methods of <xref:System.Activities.NativeActivityContext>.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="dd959-128">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="dd959-128">To use this sample</span></span>  
  
1.  <span data-ttu-id="dd959-129">Öffnen Sie in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "For.sln".</span><span class="sxs-lookup"><span data-stu-id="dd959-129">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the For.sln solution file.</span></span>  
  
2.  <span data-ttu-id="dd959-130">Erstellen Sie die Projektmappe, indem Sie STRG+UMSCHALT+B drücken.</span><span class="sxs-lookup"><span data-stu-id="dd959-130">Build the solution, by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="dd959-131">Drücken Sie F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="dd959-131">Run the solution, by pressing F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dd959-132">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="dd959-132">The samples may already be installed on your machine.</span></span> <span data-ttu-id="dd959-133">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="dd959-133">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="dd959-134">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="dd959-134">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="dd959-135">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="dd959-135">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\For`