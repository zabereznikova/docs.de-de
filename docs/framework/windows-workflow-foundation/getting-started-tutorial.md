---
title: Getting Started Tutorial2
description: Dieser Artikel beginnt mit einer Reihe von Tutorials, in denen die Programmierung von Windows Workflow Foundation-Anwendungen vorgestellt wird.
ms.date: 03/30/2017
helpviewer_keywords:
- WF [WF], getting started
- Windows Workflow Foundation [WF], getting started
ms.assetid: c2d3585f-6b1a-4d4f-9865-bd7cd31c5d42
ms.openlocfilehash: 148ba77231067bf5f8ff1d8b444b83d951ce8761
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419849"
---
# <a name="getting-started-tutorial"></a><span data-ttu-id="a6a91-103">Lernprogramm 'Erste Schritte'</span><span class="sxs-lookup"><span data-stu-id="a6a91-103">Getting Started Tutorial</span></span>
<span data-ttu-id="a6a91-104">Dieser Abschnitt enthält eine Reihe von Themen mit exemplarischen Vorgehensweisen, in denen Sie die Programmierung von Windows Workflow Foundation-Anwendungen (WF) vorstellen.</span><span class="sxs-lookup"><span data-stu-id="a6a91-104">This section contains a set of walkthrough topics that introduce you to programming Windows Workflow Foundation (WF) applications.</span></span> <span data-ttu-id="a6a91-105">Indem Sie die Vorgehensweisen in diesen Themen befolgen, erstellen Sie eine Anwendung, die ein Spiel darstellt, bei dem es darum geht, eine Zahl zu schätzen.</span><span class="sxs-lookup"><span data-stu-id="a6a91-105">By following the procedures in these topics, you will build an application that is a number guessing game.</span></span> <span data-ttu-id="a6a91-106">Das erste Thema im Lernprogramm führt Sie durch die Schritte des Erstellens der benutzerdefinierten Aktivitäten, die für den Workflow erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="a6a91-106">The first topic in the tutorial leads you through the steps to create the custom activities required for the workflow.</span></span> <span data-ttu-id="a6a91-107">Im zweiten Thema werden diese Aktivitäten mit integrierten Workflowaktivitäten zu einem Flussdiagrammworkflow zusammengefügt.</span><span class="sxs-lookup"><span data-stu-id="a6a91-107">In the second topic, these activities are assembled along with built-in workflow activities into a flowchart workflow.</span></span> <span data-ttu-id="a6a91-108">Im dritten Thema wird die Hostanwendung für die Ausführung des Workflows konfiguriert, und im abschließenden Thema wird die Persistenz eingeführt.</span><span class="sxs-lookup"><span data-stu-id="a6a91-108">In the third topic, the host application is configured to run the workflow, and in the final topic persistence is introduced.</span></span> <span data-ttu-id="a6a91-109">Jeder Schritt in diesem Prozess ist von den vorherigen Schritten abhängig, es wird daher empfohlen, diese nacheinander abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="a6a91-109">Each step in this process depends on the previous steps, so we recommend that you complete them in order.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a6a91-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a6a91-110">In This Section</span></span>  
 [<span data-ttu-id="a6a91-111">Vorgehensweise: Erstellen einer Aktivität</span><span class="sxs-lookup"><span data-stu-id="a6a91-111">How to: Create an Activity</span></span>](how-to-create-an-activity.md)  
 <span data-ttu-id="a6a91-112">Beschreibt, wie Sie eine benutzerdefinierte Aktivität erstellen, die von <xref:System.Activities.NativeActivity%601> abgeleitet ist, und wie Sie diese Aktivität mit einer integrierten Aktivität zu einer zusammengesetzten Aktivität vereinen, indem Sie den Aktivitäts-Designer verwenden.</span><span class="sxs-lookup"><span data-stu-id="a6a91-112">Describes how to create a custom activity that derives from <xref:System.Activities.NativeActivity%601>, and how to compose this activity along with a built-in activity into a composite activity using the activity designer.</span></span>  
  
 [<span data-ttu-id="a6a91-113">Vorgehensweise: Erstellen eines Workflows</span><span class="sxs-lookup"><span data-stu-id="a6a91-113">How to: Create a Workflow</span></span>](how-to-create-a-workflow.md)  
 <span data-ttu-id="a6a91-114">Beschreibt, wie Flussdiagramm-, sequenzielle und Zustandsautomatworkflows mithilfe von integrierten Aktivitäten und den benutzerdefinierten Aktivitäten aus dem vorherigen Lernprogramm erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="a6a91-114">Describes how to create flowchart, sequential, and state machine workflows by using built-in activities and the custom activities from the preceding tutorial.</span></span>  
  
 [<span data-ttu-id="a6a91-115">Vorgehensweise: Ausführen eines Workflows</span><span class="sxs-lookup"><span data-stu-id="a6a91-115">How to: Run a Workflow</span></span>](how-to-run-a-workflow.md)  
 <span data-ttu-id="a6a91-116">Beschreibt, wie Sie einen Workflow aus einer Hostumgebung aufrufen, Daten an einen bzw. aus einem Workflow übergeben und Lesezeichen wiederaufnehmen.</span><span class="sxs-lookup"><span data-stu-id="a6a91-116">Describes how to invoke a workflow from a host environment, pass data into and out of a workflow, and how to resume bookmarks.</span></span>  
  
 [<span data-ttu-id="a6a91-117">Vorgehensweise: Erstellen und Ausführen eines Workflows mit langer Laufzeit</span><span class="sxs-lookup"><span data-stu-id="a6a91-117">How to: Create and Run a Long Running Workflow</span></span>](how-to-create-and-run-a-long-running-workflow.md)  
 <span data-ttu-id="a6a91-118">Beschreibt, wie Sie einer Workflowanwendung Persistenz hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a6a91-118">Describes how to add persistence to a workflow application.</span></span>  
  
 [<span data-ttu-id="a6a91-119">Vorgehensweise: Erstellen einer benutzerdefinierten Nachverfolgungskomponente</span><span class="sxs-lookup"><span data-stu-id="a6a91-119">How to: Create a Custom Tracking Participant</span></span>](how-to-create-a-custom-tracking-participant.md)  
 <span data-ttu-id="a6a91-120">Beschreibt, wie Sie einen benutzerdefinierten Überwachungsteilnehmer und ein Nachverfolgungsprofil erstellen.</span><span class="sxs-lookup"><span data-stu-id="a6a91-120">Describes how to create a custom tracking participant and tracking profile.</span></span>  
  
 [<span data-ttu-id="a6a91-121">Vorgehensweise: Paralleles Hosten mehrerer Workflowversionen</span><span class="sxs-lookup"><span data-stu-id="a6a91-121">How to: Host Multiple Versions of a Workflow Side-by-Side</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md)  
 <span data-ttu-id="a6a91-122">Beschreibt, wie `WorkflowIdentity` zum parallelen Hosten mehrerer Workflowversionen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a6a91-122">Describes how to use `WorkflowIdentity` to host multiple versions of a workflow side-by-side.</span></span>  
  
 [<span data-ttu-id="a6a91-123">Vorgehensweise: Aktualisieren der Definition einer ausgeführten Workflowinstanz</span><span class="sxs-lookup"><span data-stu-id="a6a91-123">How to: Update the Definition of a Running Workflow Instance</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md)  
 <span data-ttu-id="a6a91-124">Beschreibt, wie Sie dynamische Updates zum Ändern ausgeführter Workflowinstanzen verwenden.</span><span class="sxs-lookup"><span data-stu-id="a6a91-124">Describes how to use dynamic update to modify running workflow instances.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6a91-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a6a91-125">See also</span></span>

- [<span data-ttu-id="a6a91-126">Windows Workflow Foundation-Programmierung</span><span class="sxs-lookup"><span data-stu-id="a6a91-126">Windows Workflow Foundation Programming</span></span>](programming.md)
