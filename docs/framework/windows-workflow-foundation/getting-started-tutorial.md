---
title: Erste Schritte-Tutorial2
ms.date: 03/30/2017
helpviewer_keywords:
- WF [WF], getting started
- Windows Workflow Foundation [WF], getting started
ms.assetid: c2d3585f-6b1a-4d4f-9865-bd7cd31c5d42
ms.openlocfilehash: 33d89b92dc17bc26391047b78c619aac01ea21da
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57724699"
---
# <a name="getting-started-tutorial"></a><span data-ttu-id="cbe0e-102">Lernprogramm 'Erste Schritte'</span><span class="sxs-lookup"><span data-stu-id="cbe0e-102">Getting Started Tutorial</span></span>
<span data-ttu-id="cbe0e-103">Dieser Abschnitt enthält eine Reihe von exemplarischen Vorgehensweisen, in denen die Programmierung von Windows Workflow Foundation (WF)-Anwendungen vorgestellt.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-103">This section contains a set of walkthrough topics that introduce you to programming Windows Workflow Foundation (WF) applications.</span></span> <span data-ttu-id="cbe0e-104">Indem Sie die Vorgehensweisen in diesen Themen befolgen, erstellen Sie eine Anwendung, die ein Spiel darstellt, bei dem es darum geht, eine Zahl zu schätzen.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-104">By following the procedures in these topics, you will build an application that is a number guessing game.</span></span> <span data-ttu-id="cbe0e-105">Das erste Thema im Lernprogramm führt Sie durch die Schritte des Erstellens der benutzerdefinierten Aktivitäten, die für den Workflow erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-105">The first topic in the tutorial leads you through the steps to create the custom activities required for the workflow.</span></span> <span data-ttu-id="cbe0e-106">Im zweiten Thema werden diese Aktivitäten mit integrierten Workflowaktivitäten zu einem Flussdiagrammworkflow zusammengefügt.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-106">In the second topic, these activities are assembled along with built-in workflow activities into a flowchart workflow.</span></span> <span data-ttu-id="cbe0e-107">Im dritten Thema wird die Hostanwendung für die Ausführung des Workflows konfiguriert, und im abschließenden Thema wird die Persistenz eingeführt.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-107">In the third topic, the host application is configured to run the workflow, and in the final topic persistence is introduced.</span></span> <span data-ttu-id="cbe0e-108">Jeder Schritt in diesem Prozess ist von den vorherigen Schritten abhängig, es wird daher empfohlen, diese nacheinander abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-108">Each step in this process depends on the previous steps, so we recommend that you complete them in order.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cbe0e-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="cbe0e-109">In This Section</span></span>  
 [<span data-ttu-id="cbe0e-110">Vorgehensweise: Erstellen einer Aktivität</span><span class="sxs-lookup"><span data-stu-id="cbe0e-110">How to: Create an Activity</span></span>](how-to-create-an-activity.md)  
 <span data-ttu-id="cbe0e-111">Beschreibt, wie Sie eine benutzerdefinierte Aktivität erstellen, die von <xref:System.Activities.NativeActivity%601> abgeleitet ist, und wie Sie diese Aktivität mit einer integrierten Aktivität zu einer zusammengesetzten Aktivität vereinen, indem Sie den Aktivitäts-Designer verwenden.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-111">Describes how to create a custom activity that derives from <xref:System.Activities.NativeActivity%601>, and how to compose this activity along with a built-in activity into a composite activity using the activity designer.</span></span>  
  
 [<span data-ttu-id="cbe0e-112">Vorgehensweise: Erstellen eines Workflows</span><span class="sxs-lookup"><span data-stu-id="cbe0e-112">How to: Create a Workflow</span></span>](how-to-create-a-workflow.md)  
 <span data-ttu-id="cbe0e-113">Beschreibt, wie Flussdiagramm-, sequenzielle und Zustandsautomatworkflows mithilfe von integrierten Aktivitäten und den benutzerdefinierten Aktivitäten aus dem vorherigen Lernprogramm erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-113">Describes how to create flowchart, sequential, and state machine workflows by using built-in activities and the custom activities from the preceding tutorial.</span></span>  
  
 [<span data-ttu-id="cbe0e-114">Vorgehensweise: Ausführen eines Workflows</span><span class="sxs-lookup"><span data-stu-id="cbe0e-114">How to: Run a Workflow</span></span>](how-to-run-a-workflow.md)  
 <span data-ttu-id="cbe0e-115">Beschreibt, wie Sie einen Workflow aus einer Hostumgebung aufrufen, Daten an einen bzw. aus einem Workflow übergeben und Lesezeichen wiederaufnehmen.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-115">Describes how to invoke a workflow from a host environment, pass data into and out of a workflow, and how to resume bookmarks.</span></span>  
  
 [<span data-ttu-id="cbe0e-116">Vorgehensweise: Erstellen und Ausführen einer langen Workflow ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="cbe0e-116">How to: Create and Run a Long Running Workflow</span></span>](how-to-create-and-run-a-long-running-workflow.md)  
 <span data-ttu-id="cbe0e-117">Beschreibt, wie Sie einer Workflowanwendung Persistenz hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-117">Describes how to add persistence to a workflow application.</span></span>  
  
 [<span data-ttu-id="cbe0e-118">Vorgehensweise: Erstellen eines benutzerdefinierten Überwachungsteilnehmer</span><span class="sxs-lookup"><span data-stu-id="cbe0e-118">How to: Create a Custom Tracking Participant</span></span>](how-to-create-a-custom-tracking-participant.md)  
 <span data-ttu-id="cbe0e-119">Beschreibt, wie Sie einen benutzerdefinierten Überwachungsteilnehmer und ein Nachverfolgungsprofil erstellen.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-119">Describes how to create a custom tracking participant and tracking profile.</span></span>  
  
 [<span data-ttu-id="cbe0e-120">Vorgehensweise: Hosten Sie mehrerer Workflowversionen zu einem Workflow Seite-an-Seite</span><span class="sxs-lookup"><span data-stu-id="cbe0e-120">How to: Host Multiple Versions of a Workflow Side-by-Side</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md)  
 <span data-ttu-id="cbe0e-121">Beschreibt, wie `WorkflowIdentity` zum parallelen Hosten mehrerer Workflowversionen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-121">Describes how to use `WorkflowIdentity` to host multiple versions of a workflow side-by-side.</span></span>  
  
 [<span data-ttu-id="cbe0e-122">Vorgehensweise: Aktualisieren der Definition einer ausgeführten Workflowinstanz</span><span class="sxs-lookup"><span data-stu-id="cbe0e-122">How to: Update the Definition of a Running Workflow Instance</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md)  
 <span data-ttu-id="cbe0e-123">Beschreibt, wie Sie dynamische Updates zum Ändern ausgeführter Workflowinstanzen verwenden.</span><span class="sxs-lookup"><span data-stu-id="cbe0e-123">Describes how to use dynamic update to modify running workflow instances.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbe0e-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cbe0e-124">See also</span></span>
- [<span data-ttu-id="cbe0e-125">Windows Workflow Foundation-Programmierung</span><span class="sxs-lookup"><span data-stu-id="cbe0e-125">Windows Workflow Foundation Programming</span></span>](programming.md)
