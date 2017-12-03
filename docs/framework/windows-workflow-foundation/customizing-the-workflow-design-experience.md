---
title: Anpassen des Workflowentwurfsvorgangs
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: extending [WF], Workflow Designer
ms.assetid: 98135077-0f5d-4d16-9337-01094e843537
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 60e8d01ad32e10f06191f7e0b38dcb648780ba29
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="customizing-the-workflow-design-experience"></a><span data-ttu-id="47c76-102">Anpassen des Workflowentwurfsvorgangs</span><span class="sxs-lookup"><span data-stu-id="47c76-102">Customizing the Workflow Design Experience</span></span>
<span data-ttu-id="47c76-103">Die Szenarien zum Entwerfen von benutzerdefinierten Aktivitäten und zum erneuten Hosten von [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] wurden in [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] deutlich vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="47c76-103">The scenarios for designing custom activities and for rehosting the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] have been greatly simplified in [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)].</span></span> <span data-ttu-id="47c76-104">Die Entwicklung und Bereitstellung sind jetzt einfacher sowie flexibler.</span><span class="sxs-lookup"><span data-stu-id="47c76-104">Development and deployment are now both easier and more flexible.</span></span> <span data-ttu-id="47c76-105">Die wichtigste Änderung besteht darin, dass das neue Aktivitätsdesigner-Programmiermodell auf [!INCLUDE[avalon1](../../../includes/avalon1-md.md)] aufbaut.</span><span class="sxs-lookup"><span data-stu-id="47c76-105">The key infrastructural change is that the new activity designer programming model is built upon [!INCLUDE[avalon1](../../../includes/avalon1-md.md)].</span></span> <span data-ttu-id="47c76-106">Dies ermöglicht Ihnen, Aktivitätsdesigner deklarativ zu definieren und den [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] in anderen Anwendungen vergleichsweise einfach erneut zu hosten.</span><span class="sxs-lookup"><span data-stu-id="47c76-106">This gives you the ability to define activity designers declaratively and to rehost the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] in other applications with comparative easy.</span></span> <span data-ttu-id="47c76-107">Beim erneuten Hosten kann ein benutzerdefinierter Ausdrucks-Editor entwickelt werden, um IntelliSense oder eine vereinfachte Ausdrucksdomäne zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="47c76-107">When rehosting, a custom expression editor can be developed to support IntelliSense or a simplified expression domain.</span></span> <span data-ttu-id="47c76-108">Die Integration in [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] ist durch die Verwendung von Workflowdiensten nahtloser geworden.</span><span class="sxs-lookup"><span data-stu-id="47c76-108">The integration with [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] has become more seamless with use of workflow services.</span></span> <span data-ttu-id="47c76-109">Benutzerdefinierte Aktivitätsdesigner und die Modellelementstruktur können verwendet werden, um die Entwurfszeiterfahrung in neu gehosteten Workflowdesignern zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="47c76-109">Custom activity designers and the Model Item Tree can be used to enhance design time experiences in rehosted workflow designers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="47c76-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="47c76-110">In This Section</span></span>  
 [<span data-ttu-id="47c76-111">Verwenden benutzerdefinierter Aktivitätsdesigner und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="47c76-111">Using Custom Activity Designers and Templates</span></span>](../../../docs/framework/windows-workflow-foundation/using-custom-activity-designers-and-templates.md)  
 <span data-ttu-id="47c76-112">Beschreibt die Erstellung eines neuen benutzerdefinierten Aktivitätsdesigners und von Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="47c76-112">Describes how to create new custom activity designers and templates.</span></span>  
  
 [<span data-ttu-id="47c76-113">Erneutes Hosten des Workflow-Designers</span><span class="sxs-lookup"><span data-stu-id="47c76-113">Rehosting the Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)  
 <span data-ttu-id="47c76-114">Beschreibt das erneute Hosten von [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] außerhalb von [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] und wie Validierungsfehler angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="47c76-114">Describes how to re-host the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] outside of [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] and how to display validation errors.</span></span>  
  
 [<span data-ttu-id="47c76-115">Verwenden eines benutzerdefinierten Ausdrucks-Editors</span><span class="sxs-lookup"><span data-stu-id="47c76-115">Using a Custom Expression Editor</span></span>](../../../docs/framework/windows-workflow-foundation/using-a-custom-expression-editor.md)  
 <span data-ttu-id="47c76-116">Beschreibt die Implementierung eines benutzerdefinierten Ausdrucks-Editors zur Verwendung von Workflowdesignern, die außerhalb von [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] erneut gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="47c76-116">Describes how to implement a custom expression editor to use with workflow designers rehosted outside of [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span></span>  
  
## <a name="reference"></a><span data-ttu-id="47c76-117">Verweis</span><span class="sxs-lookup"><span data-stu-id="47c76-117">Reference</span></span>  
 <xref:System.Activities.Presentation.ActivityDesigner>  
  
## <a name="see-also"></a><span data-ttu-id="47c76-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="47c76-118">See Also</span></span>  
 [<span data-ttu-id="47c76-119">Erweitern der Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="47c76-119">Extending Windows Workflow Foundation</span></span>](../../../docs/framework/windows-workflow-foundation/extend.md)  
 [<span data-ttu-id="47c76-120">Designer</span><span class="sxs-lookup"><span data-stu-id="47c76-120">Designer</span></span>](../../../docs/framework/windows-workflow-foundation/samples/designer.md)  
 [<span data-ttu-id="47c76-121">Benutzerdefinierte Aktivitätsdesigner</span><span class="sxs-lookup"><span data-stu-id="47c76-121">Custom Activity Designers</span></span>](../../../docs/framework/windows-workflow-foundation/samples/custom-activity-designers.md)  
 [<span data-ttu-id="47c76-122">Hosten von Designern</span><span class="sxs-lookup"><span data-stu-id="47c76-122">Designer ReHosting</span></span>](../../../docs/framework/windows-workflow-foundation/samples/designer-rehosting.md)
