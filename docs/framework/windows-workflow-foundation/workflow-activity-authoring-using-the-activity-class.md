---
title: "Erstellen von Workflowaktivitäten mit der Aktivitätsklasse"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7b7b1c66-f093-43c3-b4d1-7173b46516da
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f4fc6d0807c07952e9b3abe2861ef04bc225142f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="workflow-activity-authoring-using-the-activity-class"></a><span data-ttu-id="17502-102">Erstellen von Workflowaktivitäten mit der Aktivitätsklasse</span><span class="sxs-lookup"><span data-stu-id="17502-102">Workflow Activity Authoring Using the Activity Class</span></span>
<span data-ttu-id="17502-103">Die einfachste Möglichkeit zum Erstellen eine Aktivität mit [!INCLUDE[wf](../../../includes/wf-md.md)] in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] besteht darin, eine Klasse erstellen, die von erben <xref:System.Activities.Activity> erstellt Funktionalität durch das Zusammenfügen von benutzerdefinierten Aktivitäten oder Aktivitäten aus der [integrierte Aktivitätsbibliothek ](../../../docs/framework/windows-workflow-foundation/net-framework-4-5-built-in-activity-library.md).</span><span class="sxs-lookup"><span data-stu-id="17502-103">The most basic way to create an activity using [!INCLUDE[wf](../../../includes/wf-md.md)] in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] is to create a class that inherits from <xref:System.Activities.Activity> that creates functionality by assembling custom activities or activities from the [Built-In Activity Library](../../../docs/framework/windows-workflow-foundation/net-framework-4-5-built-in-activity-library.md).</span></span> <span data-ttu-id="17502-104">In diesem Thema wird veranschaulicht, wie eine Aktivität erstellt wird, die zwei Meldungen in die Konsole schreibt.</span><span class="sxs-lookup"><span data-stu-id="17502-104">This topic demonstrates how to create an activity that writes two messages to the console.</span></span>  
  
### <a name="to-create-a-custom-activity-using-the-activity-designer"></a><span data-ttu-id="17502-105">So erstellen Sie eine benutzerdefinierte Aktivität mit dem Aktivitätsdesigner</span><span class="sxs-lookup"><span data-stu-id="17502-105">To create a custom Activity using the activity designer</span></span>  
  
1.  <span data-ttu-id="17502-106">Öffnen Sie [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="17502-106">Open [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="17502-107">Wählen Sie "Datei", "Neu" und "Projekt" aus.</span><span class="sxs-lookup"><span data-stu-id="17502-107">Select File, New, Project.</span></span> <span data-ttu-id="17502-108">Wählen Sie **Workflow 4.0** unter **Visual C#-** in der **Projekttypen** , und wählen Sie die **v2010** Knoten.</span><span class="sxs-lookup"><span data-stu-id="17502-108">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="17502-109">Wählen Sie **Aktivitätsbibliothek** in der **Vorlagen** Fenster.</span><span class="sxs-lookup"><span data-stu-id="17502-109">Select **Activity Library** in the **Templates** window.</span></span> <span data-ttu-id="17502-110">Geben Sie dem neuen Projekt den Namen "HelloActivity".</span><span class="sxs-lookup"><span data-stu-id="17502-110">Name the new project HelloActivity.</span></span>  
  
3.  <span data-ttu-id="17502-111">Öffnen Sie die neue Aktivität.</span><span class="sxs-lookup"><span data-stu-id="17502-111">Open the new activity.</span></span>  <span data-ttu-id="17502-112">Ziehen Sie eine <xref:System.Activities.Statements.Sequence>-Aktivität von der Toolbox auf die Designeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="17502-112">Drag a <xref:System.Activities.Statements.Sequence> activity from the toolbox onto the designer surface.</span></span>  
  
4.  <span data-ttu-id="17502-113">Ziehen Sie eine <xref:System.Activities.Statements.WriteLine>-Aktivität in die <xref:System.Activities.Statements.Sequence>-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="17502-113">Drag a <xref:System.Activities.Statements.WriteLine> activity into the <xref:System.Activities.Statements.Sequence> activity.</span></span> <span data-ttu-id="17502-114">Geben Sie `"Hello World"` (mit Anführungszeichen) in der **Text** Feld.</span><span class="sxs-lookup"><span data-stu-id="17502-114">Enter `"Hello World"` (with quotes) into the **Text** field.</span></span>  
  
5.  <span data-ttu-id="17502-115">Ziehen Sie eine zweite <xref:System.Activities.Statements.WriteLine>-Aktivität in die <xref:System.Activities.Statements.Sequence>-Aktivität (unter die erste).</span><span class="sxs-lookup"><span data-stu-id="17502-115">Drag a second <xref:System.Activities.Statements.WriteLine> activity into the <xref:System.Activities.Statements.Sequence> activity, below the first one.</span></span> <span data-ttu-id="17502-116">Geben Sie `"Goodbye"` (mit Anführungszeichen) in der **Text** Feld.</span><span class="sxs-lookup"><span data-stu-id="17502-116">Enter `"Goodbye"` (with quotes) into the **Text** field.</span></span>
