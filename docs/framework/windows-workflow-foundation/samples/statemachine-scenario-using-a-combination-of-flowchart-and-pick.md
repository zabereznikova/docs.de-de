---
title: StateMachine-Szenario mit einer Kombination aus FlowChart und Pick
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 88d81395-f7a3-41d8-8439-20a425c538a6
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 46aa2f9a4ed152bfc861bb02ed2d8c6429694764
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="statemachine-scenario-using-a-combination-of-flowchart-and-pick"></a><span data-ttu-id="35659-102">StateMachine-Szenario mit einer Kombination aus FlowChart und Pick</span><span class="sxs-lookup"><span data-stu-id="35659-102">StateMachine Scenario Using a Combination of FlowChart and Pick</span></span>
<span data-ttu-id="35659-103">Dieses Beispiel veranschaulicht, wie ein einfaches Szenario mit einer Stoppuhr mithilfe einer Kombination der <xref:System.Activities.Statements.Flowchart>-Aktivität und der <xref:System.Activities.Statements.Pick>-Aktivität implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="35659-103">This sample demonstrates how to implement a simple stopwatch scenario using a combination of the <xref:System.Activities.Statements.Flowchart> and <xref:System.Activities.Statements.Pick> activities.</span></span> <span data-ttu-id="35659-104">Stoppuhrereignisse werden mithilfe von Empfangs- und Sendeaktivitäten innerhalb der Pick-Aktivität überwacht.</span><span class="sxs-lookup"><span data-stu-id="35659-104">It uses Receive and Send within the Pick activity to listen for stopwatch events.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="35659-105">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="35659-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="35659-106">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="35659-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="35659-107">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie (Downloadseite) auf, und laden Sie alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Beispiele und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]-Beispiele herunter.</span><span class="sxs-lookup"><span data-stu-id="35659-107">If this directory does not exist, go to (download page) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="35659-108">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="35659-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\StateMachineWithPick`  
  
## <a name="sample-details"></a><span data-ttu-id="35659-109">Beispieldetails</span><span class="sxs-lookup"><span data-stu-id="35659-109">Sample Details</span></span>  
 <span data-ttu-id="35659-110">In der folgenden Tabelle sind die Projekte in diesem Beispiel aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="35659-110">The following table lists the projects in this sample.</span></span>  
  
|<span data-ttu-id="35659-111">Projektname</span><span class="sxs-lookup"><span data-stu-id="35659-111">Project Name</span></span>|<span data-ttu-id="35659-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="35659-112">Description</span></span>|  
|-|-|  
|<span data-ttu-id="35659-113">StopWatchService</span><span class="sxs-lookup"><span data-stu-id="35659-113">StopWatchService</span></span>|<span data-ttu-id="35659-114">Dieses Projekt enthält die Implementierung eines Zustandsautomaten für das Stoppuhrbeispiel, in dem eine Kombination der <xref:System.Activities.Statements.Flowchart>-Aktivität und der <xref:System.Activities.Statements.Pick>-Aktivität verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="35659-114">This project contains the implementation of a state machine for the stopwatch sample using a combination of the <xref:System.Activities.Statements.Flowchart> and <xref:System.Activities.Statements.Pick> activities.</span></span><br /><br /> <span data-ttu-id="35659-115">Die <xref:System.Activities.Statements.Pick>-Aktivität verfügt über 3 <xref:System.Activities.Statements.PickBranch>-Anweisungen innerhalb der <xref:System.Activities.Statements.Pick.Branches%2A>-Eigenschaft, die die Ereignisse `GetStart`, `GetStop` und `GetOff` überwacht.</span><span class="sxs-lookup"><span data-stu-id="35659-115">The <xref:System.Activities.Statements.Pick> activity has 3 <xref:System.Activities.Statements.PickBranch> statements within the <xref:System.Activities.Statements.Pick.Branches%2A> property that listen for `GetStart`, `GetStop` and `GetOff` events.</span></span> <span data-ttu-id="35659-116">Auf Grundlage des eingehenden Ereignisses werden die Trigger für eine der Verzweigungen aktiviert, und die entsprechende <xref:System.Activities.Statements.PickBranch.Action%2A> wird ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="35659-116">Based on the incoming event, the triggers for one of the branches activate and the corresponding <xref:System.Activities.Statements.PickBranch.Action%2A> is triggered.</span></span> <span data-ttu-id="35659-117">In der <xref:System.Activities.Statements.PickBranch.Action%2A>-Eigenschaft gibt es eine <xref:System.Activities.Statements.Switch%601>-Anweisung, die auswertet, ob der Übergang ein rechtmäßiger Übergang ist. Ist dies der Fall, wird die `currentState`-Eigenschaft auf den Übergangszustand aktualisiert und an den Client gesendet.</span><span class="sxs-lookup"><span data-stu-id="35659-117">In the <xref:System.Activities.Statements.PickBranch.Action%2A> property, there is a <xref:System.Activities.Statements.Switch%601> statement that evaluates whether the transition is a legitimate transition and if it is, the `currentState` property is updated to the transitioning state and sent to the client.</span></span><br /><br /> <span data-ttu-id="35659-118">Die <xref:System.Activities.Statements.FlowDecision>-Aktivität am Ende von <xref:System.Activities.Statements.Flowchart> wertet die `currentState`-Eigenschaft aus, um zu bestimmen, ob der Zustand ein Endstatus ist.</span><span class="sxs-lookup"><span data-stu-id="35659-118">The <xref:System.Activities.Statements.FlowDecision> activity at the end of the <xref:System.Activities.Statements.Flowchart> evaluates the `currentState` property to determine whether the state is terminal.</span></span> <span data-ttu-id="35659-119">Ist dies der Fall, endet der Workflow. Andernfalls springt die Steuerung zurück zum Start der <xref:System.Activities.Statements.Pick>-Aktivität, wo der Workflow auf weitere Stoppuhrereignisse wartet.</span><span class="sxs-lookup"><span data-stu-id="35659-119">If it is, the workflow ends; otherwise control loops back to the start of the <xref:System.Activities.Statements.Pick> activity where the workflow waits for more stopwatch events.</span></span>|  
|<span data-ttu-id="35659-120">StopWatchClient</span><span class="sxs-lookup"><span data-stu-id="35659-120">StopWatchClient</span></span>|<span data-ttu-id="35659-121">Dies ist eine einfache sequenzielle Workflowkonsolenanwendung, die verschiedene Stoppuhrereignisse mit einfachen Kombinationen der Send- und Receive-Aktivitäten sendet.</span><span class="sxs-lookup"><span data-stu-id="35659-121">This is a simple sequential workflow console application that sends various stopwatch events with simple Send or Receive activity combinations.</span></span>|  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="35659-122">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="35659-122">To use this sample</span></span>  
  
1.  <span data-ttu-id="35659-123">Öffnen Sie in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "StateMachineWithPick.sln".</span><span class="sxs-lookup"><span data-stu-id="35659-123">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open StateMachineWithPick.sln solution file.</span></span>  
  
2.  <span data-ttu-id="35659-124">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="35659-124">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="35659-125">Starten Sie den StopWatchService.exe aus [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] als Administrator, indem Sie mit der rechten Maustaste auf die .exe-Datei klicken und auswählen **als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="35659-125">Start the StopWatchService.exe from [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] as an administrator by right clicking the .exe file and selecting **Run as administrator**.</span></span>  
  
    1.  <span data-ttu-id="35659-126">Navigieren Sie zum Ordner "StateMachineWithPick\CS\StopWatchService\bin\Debug".</span><span class="sxs-lookup"><span data-stu-id="35659-126">Navigate to the StateMachineWithPick\CS\StopWatchService\bin\Debug folder.</span></span>  
  
    2.  <span data-ttu-id="35659-127">Mit der rechten Maustaste der StopWatchService.exe-Datei, und wählen Sie **als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="35659-127">Right-click the StopWatchService.exe file and select **Run as administrator**.</span></span>  
  
4.  <span data-ttu-id="35659-128">Starten Sie die StopWatchClient-Clientanwendung über [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35659-128">Start the StopWatchClient client application from within [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
    1.  <span data-ttu-id="35659-129">In **Projektmappen-Explorer**, wählen die **StopWatchClient** Projekt, und mit der rechten Maustaste **als Startprojekt festlegen**.</span><span class="sxs-lookup"><span data-stu-id="35659-129">In **Solution Explorer**, select the **StopWatchClient** project and right-click **Set as StartUp Project**.</span></span>  
  
    2.  <span data-ttu-id="35659-130">Drücken Sie STRG+F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="35659-130">To run the solution, press CTRL+F5.</span></span>  
  
5.  <span data-ttu-id="35659-131">Wechseln Sie zum Konsolenfenster für "StopWatchService.exe" zurück, um die Zustandsübergänge anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="35659-131">Switch back to the console window for the StopWatchService.exe to view the state transitions.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="35659-132">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="35659-132">The samples may already be installed on your machine.</span></span> <span data-ttu-id="35659-133">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="35659-133">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="35659-134">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="35659-134">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="35659-135">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="35659-135">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\StateMachineWithPick`