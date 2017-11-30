---
title: "For-Aktivität"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2ea751b4-36f0-48aa-a115-70a2ab89f6d8
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e77800b21d671a0de0cab6f442919f50ce5ca51b
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2017
---
# <a name="for-activity"></a><span data-ttu-id="58f78-102">For-Aktivität</span><span class="sxs-lookup"><span data-stu-id="58f78-102">For Activity</span></span>
<span data-ttu-id="58f78-103">Im For-Beispiel wird veranschaulicht, wie eine benutzerdefinierte Aktivität erstellt wird, die von <xref:System.Activities.NativeActivity> erbt, und wie diese in einem Workflow verwendet wird, um ein Beispiel mit realen Bedingungen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="58f78-103">The For sample demonstrates how to build a custom activity that inherits from <xref:System.Activities.NativeActivity>, and use it in a workflow to execute a real world example.</span></span> <span data-ttu-id="58f78-104">Die benutzerdefinierte Aktivität in diesem Beispiel funktioniert wie die `for`-Anweisung in C#.</span><span class="sxs-lookup"><span data-stu-id="58f78-104">The custom activity included in this sample functions like the C# `for` statement.</span></span> <span data-ttu-id="58f78-105">T</span><span class="sxs-lookup"><span data-stu-id="58f78-105">T</span></span>  
  
 <span data-ttu-id="58f78-106">Die benutzerdefinierte `For`-Aktivität weist die Eigenschaften `InitAction`, `IterationAction`, `Condition` und `Body` auf, die jeweils der Initialisierungsanweisung, der iterativen Anweisung, der Fortsetzungsbedingung und der Textanweisung in der standardmäßigen `For`-Anweisung in C# entsprechen.</span><span class="sxs-lookup"><span data-stu-id="58f78-106">The `For` custom activity has properties named `InitAction`, `IterationAction`, `Condition`, and `Body` that correspond to the initialization statement, iterative statement, continuation condition, and body statement respectively found in the standard C# `For` statement.</span></span>  
  
 <span data-ttu-id="58f78-107">In der folgenden Tabelle sind die im Beispiel verwendeten Schlüsseldateien beschrieben.</span><span class="sxs-lookup"><span data-stu-id="58f78-107">The following table describes the key files in the sample.</span></span>  
  
|<span data-ttu-id="58f78-108">Datei</span><span class="sxs-lookup"><span data-stu-id="58f78-108">File</span></span>|<span data-ttu-id="58f78-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58f78-109">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="58f78-110">For.cs</span><span class="sxs-lookup"><span data-stu-id="58f78-110">For.cs</span></span>|<span data-ttu-id="58f78-111">Klassendefinition für die benutzerdefinierte `For`-Aktivität, die durch Erweiterung der <xref:System.Activities.NativeActivity>-Klasse die Funktionalität der `For`-Anweisung in C# bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="58f78-111">Class definition for the `For` custom activity, which extends the <xref:System.Activities.NativeActivity> class to provide the functionality of the C# `For` statement.</span></span>|  
|<span data-ttu-id="58f78-112">Program.cs</span><span class="sxs-lookup"><span data-stu-id="58f78-112">Program.cs</span></span>|<span data-ttu-id="58f78-113">Eine Clientanwendung, die unter Verwendung der benutzerdefinierten `For`-Aktivität grundlegende iterative Verarbeitungsschritte für eine Auflistung ausführt.</span><span class="sxs-lookup"><span data-stu-id="58f78-113">A client application that performs basic iterative work on a collection using the custom `For` activity.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="58f78-114">Stellen Sie bei Verwendung der benutzerdefinierten `For`-Aktivität sicher, dass die `Condition`-Eigenschaft festgelegt ist. Andernfalls kann eine Endlosschleife auftreten.</span><span class="sxs-lookup"><span data-stu-id="58f78-114">When using the `For` custom activity, ensure that the `Condition` property is set; otherwise an infinite loop could occur.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="58f78-115">Veranschaulicht</span><span class="sxs-lookup"><span data-stu-id="58f78-115">Demonstrates</span></span>  
 <span data-ttu-id="58f78-116">Erstellen einer benutzerdefinierten Aktivität, die von <xref:System.Activities.NativeActivity> erbt.</span><span class="sxs-lookup"><span data-stu-id="58f78-116">Create a custom activity that inherits from <xref:System.Activities.NativeActivity>.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="58f78-117">Diskussion</span><span class="sxs-lookup"><span data-stu-id="58f78-117">Discussion</span></span>  
 <span data-ttu-id="58f78-118">In der folgenden Tabelle werden die Eigenschaften der Aktivität in diesem Beispiel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="58f78-118">The following table describes the properties of the activity included in this sample.</span></span>  
  
 <span data-ttu-id="58f78-119">InitAction</span><span class="sxs-lookup"><span data-stu-id="58f78-119">InitAction</span></span>  
 <span data-ttu-id="58f78-120">Initialisierungsanweisung</span><span class="sxs-lookup"><span data-stu-id="58f78-120">Initialization statement</span></span>  
  
 <span data-ttu-id="58f78-121">IterationAction</span><span class="sxs-lookup"><span data-stu-id="58f78-121">IterationAction</span></span>  
 <span data-ttu-id="58f78-122">Iterative Anweisung</span><span class="sxs-lookup"><span data-stu-id="58f78-122">Iterative statement</span></span>  
  
 <span data-ttu-id="58f78-123">Bedingung</span><span class="sxs-lookup"><span data-stu-id="58f78-123">Condition</span></span>  
 <span data-ttu-id="58f78-124">Fortsetzungsanweisung</span><span class="sxs-lookup"><span data-stu-id="58f78-124">Continuation statement</span></span>  
  
 <span data-ttu-id="58f78-125">Body</span><span class="sxs-lookup"><span data-stu-id="58f78-125">Body</span></span>  
 <span data-ttu-id="58f78-126">Textanweisung</span><span class="sxs-lookup"><span data-stu-id="58f78-126">Body statement</span></span>  
  
 <span data-ttu-id="58f78-127">Die Aktivität erbt von <xref:System.Activities.NativeActivity>, um mittels einer der `ScheduleActivity`-Methoden von <xref:System.Activities.NativeActivityContext> Zugriff auf Laufzeitfunktionen zu erhalten, z. B. zur Planung zusätzlicher auszuführender Aktivitäten.</span><span class="sxs-lookup"><span data-stu-id="58f78-127">The activity inherits from <xref:System.Activities.NativeActivity> to gain access to runtime features such as scheduling additional activities to run, using one of the `ScheduleActivity` methods of <xref:System.Activities.NativeActivityContext>.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="58f78-128">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="58f78-128">To use this sample</span></span>  
  
1.  <span data-ttu-id="58f78-129">Öffnen Sie in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "For.sln".</span><span class="sxs-lookup"><span data-stu-id="58f78-129">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the For.sln solution file.</span></span>  
  
2.  <span data-ttu-id="58f78-130">Erstellen Sie die Projektmappe, indem Sie STRG+UMSCHALT+B drücken.</span><span class="sxs-lookup"><span data-stu-id="58f78-130">Build the solution, by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="58f78-131">Drücken Sie F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="58f78-131">Run the solution, by pressing F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="58f78-132">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="58f78-132">The samples may already be installed on your machine.</span></span> <span data-ttu-id="58f78-133">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="58f78-133">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="58f78-134">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="58f78-134">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="58f78-135">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="58f78-135">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\For`