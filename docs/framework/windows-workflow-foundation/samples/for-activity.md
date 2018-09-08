---
title: For-Aktivität
ms.date: 03/30/2017
ms.assetid: 2ea751b4-36f0-48aa-a115-70a2ab89f6d8
ms.openlocfilehash: 7a7023abb9057ab4b25552fbf9a81cd2ae2b4e88
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44206262"
---
# <a name="for-activity"></a><span data-ttu-id="d20d3-102">For-Aktivität</span><span class="sxs-lookup"><span data-stu-id="d20d3-102">For Activity</span></span>
<span data-ttu-id="d20d3-103">Im For-Beispiel wird veranschaulicht, wie eine benutzerdefinierte Aktivität erstellt wird, die von <xref:System.Activities.NativeActivity> erbt, und wie diese in einem Workflow verwendet wird, um ein Beispiel mit realen Bedingungen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d20d3-103">The For sample demonstrates how to build a custom activity that inherits from <xref:System.Activities.NativeActivity>, and use it in a workflow to execute a real world example.</span></span> <span data-ttu-id="d20d3-104">Die benutzerdefinierte Aktivität in diesem Beispiel funktioniert wie die `for`-Anweisung in C#.</span><span class="sxs-lookup"><span data-stu-id="d20d3-104">The custom activity included in this sample functions like the C# `for` statement.</span></span> <span data-ttu-id="d20d3-105">T</span><span class="sxs-lookup"><span data-stu-id="d20d3-105">T</span></span>  
  
 <span data-ttu-id="d20d3-106">Die benutzerdefinierte `For`-Aktivität weist die Eigenschaften `InitAction`, `IterationAction`, `Condition` und `Body` auf, die jeweils der Initialisierungsanweisung, der iterativen Anweisung, der Fortsetzungsbedingung und der Textanweisung in der standardmäßigen `For`-Anweisung in C# entsprechen.</span><span class="sxs-lookup"><span data-stu-id="d20d3-106">The `For` custom activity has properties named `InitAction`, `IterationAction`, `Condition`, and `Body` that correspond to the initialization statement, iterative statement, continuation condition, and body statement respectively found in the standard C# `For` statement.</span></span>  
  
 <span data-ttu-id="d20d3-107">In der folgenden Tabelle sind die im Beispiel verwendeten Schlüsseldateien beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d20d3-107">The following table describes the key files in the sample.</span></span>  
  
|<span data-ttu-id="d20d3-108">Datei</span><span class="sxs-lookup"><span data-stu-id="d20d3-108">File</span></span>|<span data-ttu-id="d20d3-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d20d3-109">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="d20d3-110">For.cs</span><span class="sxs-lookup"><span data-stu-id="d20d3-110">For.cs</span></span>|<span data-ttu-id="d20d3-111">Klassendefinition für die benutzerdefinierte `For`-Aktivität, die durch Erweiterung der <xref:System.Activities.NativeActivity>-Klasse die Funktionalität der `For`-Anweisung in C# bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="d20d3-111">Class definition for the `For` custom activity, which extends the <xref:System.Activities.NativeActivity> class to provide the functionality of the C# `For` statement.</span></span>|  
|<span data-ttu-id="d20d3-112">Program.cs</span><span class="sxs-lookup"><span data-stu-id="d20d3-112">Program.cs</span></span>|<span data-ttu-id="d20d3-113">Eine Clientanwendung, die unter Verwendung der benutzerdefinierten `For`-Aktivität grundlegende iterative Verarbeitungsschritte für eine Auflistung ausführt.</span><span class="sxs-lookup"><span data-stu-id="d20d3-113">A client application that performs basic iterative work on a collection using the custom `For` activity.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="d20d3-114">Stellen Sie bei Verwendung der benutzerdefinierten `For`-Aktivität sicher, dass die `Condition`-Eigenschaft festgelegt ist. Andernfalls kann eine Endlosschleife auftreten.</span><span class="sxs-lookup"><span data-stu-id="d20d3-114">When using the `For` custom activity, ensure that the `Condition` property is set; otherwise an infinite loop could occur.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="d20d3-115">Veranschaulicht</span><span class="sxs-lookup"><span data-stu-id="d20d3-115">Demonstrates</span></span>  
 <span data-ttu-id="d20d3-116">Erstellen einer benutzerdefinierten Aktivität, die von <xref:System.Activities.NativeActivity> erbt.</span><span class="sxs-lookup"><span data-stu-id="d20d3-116">Create a custom activity that inherits from <xref:System.Activities.NativeActivity>.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="d20d3-117">Diskussion</span><span class="sxs-lookup"><span data-stu-id="d20d3-117">Discussion</span></span>  
 <span data-ttu-id="d20d3-118">In der folgenden Tabelle werden die Eigenschaften der Aktivität in diesem Beispiel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d20d3-118">The following table describes the properties of the activity included in this sample.</span></span>  
  
 <span data-ttu-id="d20d3-119">InitAction</span><span class="sxs-lookup"><span data-stu-id="d20d3-119">InitAction</span></span>  
 <span data-ttu-id="d20d3-120">Initialisierungsanweisung</span><span class="sxs-lookup"><span data-stu-id="d20d3-120">Initialization statement</span></span>  
  
 <span data-ttu-id="d20d3-121">IterationAction</span><span class="sxs-lookup"><span data-stu-id="d20d3-121">IterationAction</span></span>  
 <span data-ttu-id="d20d3-122">Iterative Anweisung</span><span class="sxs-lookup"><span data-stu-id="d20d3-122">Iterative statement</span></span>  
  
 <span data-ttu-id="d20d3-123">Bedingung</span><span class="sxs-lookup"><span data-stu-id="d20d3-123">Condition</span></span>  
 <span data-ttu-id="d20d3-124">Fortsetzungsanweisung</span><span class="sxs-lookup"><span data-stu-id="d20d3-124">Continuation statement</span></span>  
  
 <span data-ttu-id="d20d3-125">Body</span><span class="sxs-lookup"><span data-stu-id="d20d3-125">Body</span></span>  
 <span data-ttu-id="d20d3-126">Textanweisung</span><span class="sxs-lookup"><span data-stu-id="d20d3-126">Body statement</span></span>  
  
 <span data-ttu-id="d20d3-127">Die Aktivität erbt von <xref:System.Activities.NativeActivity>, um mittels einer der `ScheduleActivity`-Methoden von <xref:System.Activities.NativeActivityContext> Zugriff auf Laufzeitfunktionen zu erhalten, z. B. zur Planung zusätzlicher auszuführender Aktivitäten.</span><span class="sxs-lookup"><span data-stu-id="d20d3-127">The activity inherits from <xref:System.Activities.NativeActivity> to gain access to runtime features such as scheduling additional activities to run, using one of the `ScheduleActivity` methods of <xref:System.Activities.NativeActivityContext>.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="d20d3-128">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="d20d3-128">To use this sample</span></span>  
  
1.  <span data-ttu-id="d20d3-129">Öffnen Sie in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "For.sln".</span><span class="sxs-lookup"><span data-stu-id="d20d3-129">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the For.sln solution file.</span></span>  
  
2.  <span data-ttu-id="d20d3-130">Erstellen Sie die Projektmappe, indem Sie STRG+UMSCHALT+B drücken.</span><span class="sxs-lookup"><span data-stu-id="d20d3-130">Build the solution, by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="d20d3-131">Drücken Sie F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d20d3-131">Run the solution, by pressing F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d20d3-132">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="d20d3-132">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d20d3-133">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="d20d3-133">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d20d3-134">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="d20d3-134">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d20d3-135">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="d20d3-135">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\For`