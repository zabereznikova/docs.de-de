---
title: Verwenden der Pick-Aktivität
ms.date: 03/30/2017
ms.assetid: b89be812-a247-4025-b0e3-ffb20db027a6
ms.openlocfilehash: 7ca4527cc1d5bc90ed1ec4df3eef6cf2d8b93b4e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142614"
---
# <a name="using-the-pick-activity"></a><span data-ttu-id="d1e85-102">Verwenden der Pick-Aktivität</span><span class="sxs-lookup"><span data-stu-id="d1e85-102">Using the Pick Activity</span></span>
<span data-ttu-id="d1e85-103">In diesem Beispiel wird veranschaulicht, wie die <xref:System.Activities.Statements.Pick>-Aktivität verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d1e85-103">This sample demonstrates how to use the <xref:System.Activities.Statements.Pick> activity.</span></span>

 <span data-ttu-id="d1e85-104">Die <xref:System.Activities.Statements.Pick>-Aktivität stellt eine ereignisbasierte Modellierung bereit.</span><span class="sxs-lookup"><span data-stu-id="d1e85-104">The <xref:System.Activities.Statements.Pick> activity provides event-based control modeling.</span></span> <span data-ttu-id="d1e85-105">Sie weist ein ähnliches Verhalten wie die `switch`-Anweisung in C# auf, die nur eine der Verzweigungen in der `switch`-Anweisung ausführt.</span><span class="sxs-lookup"><span data-stu-id="d1e85-105">It behaves similar to the C# `switch` statement, which executes only one of the branches in the `switch` statement.</span></span> <span data-ttu-id="d1e85-106">Im Gegensatz zur `switch`-Anweisung, in dem ein Branch basierend auf einem Wert ausgeführt wird, führt die <xref:System.Activities.Statements.Pick>-Aktivität einen Branch basierend darauf aus, wie eine Aktivität abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="d1e85-106">Unlike the `switch` statement in which a branch is executed based upon on a value, the <xref:System.Activities.Statements.Pick> activity executes a branch based upon how an activity completes.</span></span>

 <span data-ttu-id="d1e85-107">In diesem Beispiel wird ein Benutzer aufgefordert, seinen Namen in der Konsole innerhalb eines bestimmten Zeitraums einzugeben.</span><span class="sxs-lookup"><span data-stu-id="d1e85-107">This sample prompts a user to type in their name on the console within a given time period.</span></span> <span data-ttu-id="d1e85-108">Die <xref:System.Activities.Statements.Pick>-Aktivität im Beispiel verfügt über zwei Branches, die basierend darauf ausgeführt werden, ob der Benutzer seinen Namen innerhalb von 5 Sekunden eingibt oder nicht.</span><span class="sxs-lookup"><span data-stu-id="d1e85-108">The <xref:System.Activities.Statements.Pick> activity in the sample has two branches that are executed based upon whether the user types in their name within 5 seconds or not.</span></span> <span data-ttu-id="d1e85-109">Wenn der Benutzer seinen Namen innerhalb von 5 Sekunden eingibt, wird die erste Verzweigung ausgeführt, die eine benutzerdefinierte `ReadLine`-Aktivität enthält; andernfalls wird die andere Verzweigung ausgeführt, die eine <xref:System.Activities.Statements.Delay>-Aktivität enthält.</span><span class="sxs-lookup"><span data-stu-id="d1e85-109">If the user types in their name within 5 seconds, the first branch is executed, which contains a custom `ReadLine` activity; otherwise the other branch is executed, which contains a <xref:System.Activities.Statements.Delay> activity.</span></span> <span data-ttu-id="d1e85-110">Sobald der Name eines Benutzers in der Konsole eingegeben wird, wird der Name des Benutzers in der Konsole gedruckt.</span><span class="sxs-lookup"><span data-stu-id="d1e85-110">Once a user’s name is typed in on the console, the user’s name is printed on the console.</span></span> <span data-ttu-id="d1e85-111">Wenn eine Eingabe nicht innerhalb von 5 Sekunden erfolgt, tritt ein Timeout für den Vorgang auf.</span><span class="sxs-lookup"><span data-stu-id="d1e85-111">If an input is not entered within 5 seconds, the operation is timed out.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="d1e85-112">Zeigt</span><span class="sxs-lookup"><span data-stu-id="d1e85-112">Demonstrates</span></span>
 <span data-ttu-id="d1e85-113"><xref:System.Activities.Statements.Pick>-Aktivität</span><span class="sxs-lookup"><span data-stu-id="d1e85-113"><xref:System.Activities.Statements.Pick> activity.</span></span>

## <a name="discussion"></a><span data-ttu-id="d1e85-114">Diskussion</span><span class="sxs-lookup"><span data-stu-id="d1e85-114">Discussion</span></span>
 <span data-ttu-id="d1e85-115">Das Beispiel umfasst einen Designerworkflow und einen codierten Workflow.</span><span class="sxs-lookup"><span data-stu-id="d1e85-115">The sample includes a Designer workflow and coded workflow.</span></span>

 <span data-ttu-id="d1e85-116">Designer-Workflow Die Designer-Version des Beispiels veranschaulicht, wie ein Workflow im Designer erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="d1e85-116">Designer Workflow The Designer version of the sample demonstrates how to create a workflow in the designer.</span></span> <span data-ttu-id="d1e85-117">Die folgenden Dateien sind enthalten:</span><span class="sxs-lookup"><span data-stu-id="d1e85-117">The following files are included:</span></span>

- <span data-ttu-id="d1e85-118">Program.cs: schließt die `Main`-Funktion ein, die den Beispielworkflow ausführt.</span><span class="sxs-lookup"><span data-stu-id="d1e85-118">Program.cs : Includes the `Main` function that executes the sample workflow.</span></span>

- <span data-ttu-id="d1e85-119">ReadString.cs: eine benutzerdefinierte Aktivität, die Eingaben aus der Konsole liest.</span><span class="sxs-lookup"><span data-stu-id="d1e85-119">ReadString.cs: A custom activity that reads some input from the console.</span></span>

- <span data-ttu-id="d1e85-120">Sequence1.xaml: ein Workflow, der mit dem Designer erstellt wurde, der Pick verwendet.</span><span class="sxs-lookup"><span data-stu-id="d1e85-120">Sequence1.xaml: A workflow created using the designer that uses Pick.</span></span>

 <span data-ttu-id="d1e85-121">Codierter Workflow Die codierte Version des Beispiels veranschaulicht, wie ein Workflow im Designer erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="d1e85-121">Coded Workflow The coded version of the sample demonstrates how to create a workflow in the designer.</span></span> <span data-ttu-id="d1e85-122">Die folgenden Dateien sind enthalten:</span><span class="sxs-lookup"><span data-stu-id="d1e85-122">The following files are included:</span></span>

- <span data-ttu-id="d1e85-123">Program.cs: schließt die `Main`-Funktion ein, die den Beispielworkflow ausführt.</span><span class="sxs-lookup"><span data-stu-id="d1e85-123">Program.cs : Includes the `Main` function that executes the sample workflow.</span></span>

- <span data-ttu-id="d1e85-124">ReadString.cs: eine benutzerdefinierte Aktivität, die Eingaben aus der Konsole liest.</span><span class="sxs-lookup"><span data-stu-id="d1e85-124">ReadString.cs: A custom activity that reads some input from the console.</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="d1e85-125">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="d1e85-125">To use this sample</span></span>

1. <span data-ttu-id="d1e85-126">Öffnen Sie mit Visual Studio 2010 die Lösungsdatei Pick.sln.</span><span class="sxs-lookup"><span data-stu-id="d1e85-126">Using Visual Studio 2010, open the Pick.sln solution file.</span></span>

2. <span data-ttu-id="d1e85-127">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d1e85-127">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="d1e85-128">Drücken Sie F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d1e85-128">To run the solution, press F5.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d1e85-129">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="d1e85-129">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d1e85-130">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="d1e85-130">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="d1e85-131">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="d1e85-131">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d1e85-132">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="d1e85-132">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Pick`
