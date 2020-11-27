---
title: Erstellen von Workflowaktivitäten mit der Aktivitätsklasse
ms.date: 03/30/2017
ms.assetid: 7b7b1c66-f093-43c3-b4d1-7173b46516da
ms.openlocfilehash: 21f1c8b1249d41029fa7a19360e96ad866c823a7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293844"
---
# <a name="workflow-activity-authoring-using-the-activity-class"></a><span data-ttu-id="cb8c9-102">Erstellen von Workflowaktivitäten mit der Aktivitätsklasse</span><span class="sxs-lookup"><span data-stu-id="cb8c9-102">Workflow Activity Authoring Using the Activity Class</span></span>

<span data-ttu-id="cb8c9-103">Die einfachste Möglichkeit zum Erstellen einer Aktivität mithilfe von Windows Workflow Foundation (WF) in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] besteht darin, eine Klasse zu erstellen, die von erbt, die durch das Zusammenstellen von <xref:System.Activities.Activity> benutzerdefinierten Aktivitäten oder Aktivitäten aus der [integrierten Aktivitäts Bibliothek](net-framework-4-5-built-in-activity-library.md)eine Funktionalität erstellt.</span><span class="sxs-lookup"><span data-stu-id="cb8c9-103">The most basic way to create an activity using Windows Workflow Foundation (WF) in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] is to create a class that inherits from <xref:System.Activities.Activity> that creates functionality by assembling custom activities or activities from the [Built-In Activity Library](net-framework-4-5-built-in-activity-library.md).</span></span> <span data-ttu-id="cb8c9-104">In diesem Thema wird veranschaulicht, wie eine Aktivität erstellt wird, die zwei Meldungen in die Konsole schreibt.</span><span class="sxs-lookup"><span data-stu-id="cb8c9-104">This topic demonstrates how to create an activity that writes two messages to the console.</span></span>

### <a name="to-create-a-custom-activity-using-the-activity-designer"></a><span data-ttu-id="cb8c9-105">So erstellen Sie eine benutzerdefinierte Aktivität mit dem Aktivitätsdesigner</span><span class="sxs-lookup"><span data-stu-id="cb8c9-105">To create a custom Activity using the activity designer</span></span>

1. <span data-ttu-id="cb8c9-106">Öffnen Sie Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="cb8c9-106">Open Visual Studio 2012.</span></span>

2. <span data-ttu-id="cb8c9-107">Wählen Sie "Datei", "Neu" und "Projekt" aus.</span><span class="sxs-lookup"><span data-stu-id="cb8c9-107">Select File, New, Project.</span></span> <span data-ttu-id="cb8c9-108">Wählen Sie im Fenster **Projekttypen** unter **Visual c#** die Option **Workflow 4,0** aus, und wählen Sie den Knoten **v2010** aus.</span><span class="sxs-lookup"><span data-stu-id="cb8c9-108">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="cb8c9-109">Wählen Sie im Fenster **Vorlagen** die Option **Aktivitäts Bibliothek** aus.</span><span class="sxs-lookup"><span data-stu-id="cb8c9-109">Select **Activity Library** in the **Templates** window.</span></span> <span data-ttu-id="cb8c9-110">Geben Sie dem neuen Projekt den Namen "HelloActivity".</span><span class="sxs-lookup"><span data-stu-id="cb8c9-110">Name the new project HelloActivity.</span></span>

3. <span data-ttu-id="cb8c9-111">Öffnen Sie die neue Aktivität.</span><span class="sxs-lookup"><span data-stu-id="cb8c9-111">Open the new activity.</span></span>  <span data-ttu-id="cb8c9-112">Ziehen Sie eine <xref:System.Activities.Statements.Sequence>-Aktivität von der Toolbox auf die Designeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="cb8c9-112">Drag a <xref:System.Activities.Statements.Sequence> activity from the toolbox onto the designer surface.</span></span>

4. <span data-ttu-id="cb8c9-113">Ziehen Sie eine <xref:System.Activities.Statements.WriteLine>-Aktivität in die <xref:System.Activities.Statements.Sequence>-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="cb8c9-113">Drag a <xref:System.Activities.Statements.WriteLine> activity into the <xref:System.Activities.Statements.Sequence> activity.</span></span> <span data-ttu-id="cb8c9-114">Geben Sie `"Hello World"` (mit Anführungszeichen) in das **Textfeld** ein.</span><span class="sxs-lookup"><span data-stu-id="cb8c9-114">Enter `"Hello World"` (with quotes) into the **Text** field.</span></span>

5. <span data-ttu-id="cb8c9-115">Ziehen Sie eine zweite <xref:System.Activities.Statements.WriteLine>-Aktivität in die <xref:System.Activities.Statements.Sequence>-Aktivität (unter die erste).</span><span class="sxs-lookup"><span data-stu-id="cb8c9-115">Drag a second <xref:System.Activities.Statements.WriteLine> activity into the <xref:System.Activities.Statements.Sequence> activity, below the first one.</span></span> <span data-ttu-id="cb8c9-116">Geben Sie `"Goodbye"` (mit Anführungszeichen) in das **Textfeld** ein.</span><span class="sxs-lookup"><span data-stu-id="cb8c9-116">Enter `"Goodbye"` (with quotes) into the **Text** field.</span></span>
