---
title: Erneutes Hosten des Workflow-Designers
description: Der Windows-Workflow-Designer kann in Umgebungen außerhalb von Visual Studio erneut gehostet werden, um Workflows zu erstellen, zu ändern und zu überwachen.
ms.date: 03/30/2017
ms.assetid: bec1fc28-f902-4edb-86c5-436cec802c2b
ms.openlocfilehash: 8c3a67d0beecdfcf4f99580bb6ec25fea6473718
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96245899"
---
# <a name="rehosting-the-workflow-designer"></a><span data-ttu-id="b9352-103">Erneutes Hosten des Workflow-Designers</span><span class="sxs-lookup"><span data-stu-id="b9352-103">Rehosting the Workflow Designer</span></span>

<span data-ttu-id="b9352-104">Der Windows-Workflow-Designer kann in Umgebungen außerhalb von Visual Studio 2012 erneut gehostet werden, um Workflows zu erstellen, zu ändern und zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="b9352-104">The Windows Workflow Designer can be rehosted in environments outside of Visual Studio 2012 for the purposes of creating, modifying, and monitoring workflows.</span></span>

 <span data-ttu-id="b9352-105">Der <xref:System.Activities.Presentation.WorkflowDesigner>-Typ ist ein Wrapper für den Zeichnungsbereich, das Eigenschaftenraster und andere Elemente. Er stellt ein grundlegendes Programmiermodell bereit, mit dem fast alle Szenarien für das erneute Hosten von Designern ermöglicht werden.</span><span class="sxs-lookup"><span data-stu-id="b9352-105">The <xref:System.Activities.Presentation.WorkflowDesigner> type is a wrapper of the canvas, property grid, and other elements, and exposes a basic programming model to handle the majority of designer rehosting scenarios.</span></span> <span data-ttu-id="b9352-106">Das Hosting <xref:System.Activities.Presentation.WorkflowDesigner> von innerhalb einer Windows Presentation Foundation-Anwendung (WPF) ist ein gängiges Szenario für die neuhosting von Workflow-Designer.</span><span class="sxs-lookup"><span data-stu-id="b9352-106">Hosting the <xref:System.Activities.Presentation.WorkflowDesigner> inside a Windows Presentation Foundation (WPF) application is a common rehosting scenario for Workflow Designer.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="b9352-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b9352-107">In This Section</span></span>

 [<span data-ttu-id="b9352-108">Aufgabe 1: Erstellen einer neuen Windows Presentation Foundation-Anwendung</span><span class="sxs-lookup"><span data-stu-id="b9352-108">Task 1: Create a New Windows Presentation Foundation Application</span></span>](task-1-create-a-new-wpf-app.md)

 [<span data-ttu-id="b9352-109">Aufgabe 2: Hosten des Workflow-Designers</span><span class="sxs-lookup"><span data-stu-id="b9352-109">Task 2: Host the Workflow Designer</span></span>](task-2-host-the-workflow-designer.md)

 [<span data-ttu-id="b9352-110">Aufgabe 3: Erstellen der Toolbox- und PropertyGrid-Bereiche</span><span class="sxs-lookup"><span data-stu-id="b9352-110">Task 3: Create the Toolbox and PropertyGrid Panes</span></span>](task-3-create-the-toolbox-and-propertygrid-panes.md)

 [<span data-ttu-id="b9352-111">Unterstützung für neue Workflow Foundation 4.5-Funktionen im neu gehosteten Workflow-Designer</span><span class="sxs-lookup"><span data-stu-id="b9352-111">Support for New Workflow Foundation 4.5 Features in the Rehosted Workflow Designer</span></span>](wf-features-in-the-rehosted-workflow-designer.md)

## <a name="see-also"></a><span data-ttu-id="b9352-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b9352-112">See also</span></span>

- [<span data-ttu-id="b9352-113">Anpassen des Workflowentwurfsvorgangs</span><span class="sxs-lookup"><span data-stu-id="b9352-113">Customizing the Workflow Design Experience</span></span>](customizing-the-workflow-design-experience.md)
