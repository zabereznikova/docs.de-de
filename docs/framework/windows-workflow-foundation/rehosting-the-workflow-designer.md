---
title: Erneutes Hosten des Workflow-Designers
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bec1fc28-f902-4edb-86c5-436cec802c2b
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e5ca7eec49dec0e9b8896b31147a3cd40ffeef5d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="rehosting-the-workflow-designer"></a><span data-ttu-id="fec92-102">Erneutes Hosten des Workflow-Designers</span><span class="sxs-lookup"><span data-stu-id="fec92-102">Rehosting the Workflow Designer</span></span>
<span data-ttu-id="fec92-103">Der [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] kann in anderen Umgebungen als [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] neu gehostet werden, um Workflows zu erstellen, zu ändern oder zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="fec92-103">The [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] can be rehosted in environments outside of [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] for the purposes of creating, modifying, and monitoring workflows.</span></span>  
  
 <span data-ttu-id="fec92-104">Der <xref:System.Activities.Presentation.WorkflowDesigner>-Typ ist ein Wrapper für den Zeichnungsbereich, das Eigenschaftenraster und andere Elemente. Er stellt ein grundlegendes Programmiermodell bereit, mit dem fast alle Szenarien für das erneute Hosten von Designern ermöglicht werden.</span><span class="sxs-lookup"><span data-stu-id="fec92-104">The <xref:System.Activities.Presentation.WorkflowDesigner> type is a wrapper of the canvas, property grid, and other elements, and exposes a basic programming model to handle the majority of designer rehosting scenarios.</span></span> <span data-ttu-id="fec92-105">Das Hosten des <xref:System.Activities.Presentation.WorkflowDesigner> in einer [!INCLUDE[avalon1](../../../includes/avalon1-md.md)]-Anwendung ist ein häufig verwendetes Szenario für erneutes Hosten für [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fec92-105">Hosting the <xref:System.Activities.Presentation.WorkflowDesigner> inside a [!INCLUDE[avalon1](../../../includes/avalon1-md.md)] application is a common rehosting scenario for [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fec92-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="fec92-106">In This Section</span></span>  
 [<span data-ttu-id="fec92-107">Aufgabe 1: Erstellen einer neuen Windows Presentation Foundation-Anwendung</span><span class="sxs-lookup"><span data-stu-id="fec92-107">Task 1: Create a New Windows Presentation Foundation Application</span></span>](../../../docs/framework/windows-workflow-foundation/task-1-create-a-new-wpf-app.md)  
  
 [<span data-ttu-id="fec92-108">Aufgabe 2: Hosten des Workflow-Designers</span><span class="sxs-lookup"><span data-stu-id="fec92-108">Task 2: Host the Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md)  
  
 [<span data-ttu-id="fec92-109">Aufgabe 3: Erstellen der Toolbox- und PropertyGrid-Bereiche</span><span class="sxs-lookup"><span data-stu-id="fec92-109">Task 3: Create the Toolbox and PropertyGrid Panes</span></span>](../../../docs/framework/windows-workflow-foundation/task-3-create-the-toolbox-and-propertygrid-panes.md)  
  
 [<span data-ttu-id="fec92-110">Unterstützung für neue Workflow Foundation 4.5-Funktionen im neu gehosteten Workflow-Designer</span><span class="sxs-lookup"><span data-stu-id="fec92-110">Support for New Workflow Foundation 4.5 Features in the Rehosted Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/wf-features-in-the-rehosted-workflow-designer.md)  
  
## <a name="see-also"></a><span data-ttu-id="fec92-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fec92-111">See Also</span></span>  
 [<span data-ttu-id="fec92-112">Anpassen des Workflowentwurfsvorgangs</span><span class="sxs-lookup"><span data-stu-id="fec92-112">Customizing the Workflow Design Experience</span></span>](../../../docs/framework/windows-workflow-foundation/customizing-the-workflow-design-experience.md)
