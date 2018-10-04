---
title: Anpassen des Workflowentwurfsvorgangs
ms.date: 03/30/2017
helpviewer_keywords:
- extending [WF], Workflow Designer
ms.assetid: 98135077-0f5d-4d16-9337-01094e843537
ms.openlocfilehash: ed4ccb45e4470eb03cec856e865d4b50220816e3
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48777538"
---
# <a name="customizing-the-workflow-design-experience"></a><span data-ttu-id="338be-102">Anpassen des Workflowentwurfsvorgangs</span><span class="sxs-lookup"><span data-stu-id="338be-102">Customizing the Workflow Design Experience</span></span>

<span data-ttu-id="338be-103">Die Szenarien zum Entwerfen von benutzerdefinierten Aktivitäten und zum erneuten Hosten von [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] wurden in [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] deutlich vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="338be-103">The scenarios for designing custom activities and for rehosting the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] have been greatly simplified in [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)].</span></span> <span data-ttu-id="338be-104">Die Entwicklung und Bereitstellung sind jetzt einfacher sowie flexibler.</span><span class="sxs-lookup"><span data-stu-id="338be-104">Development and deployment are now both easier and more flexible.</span></span> <span data-ttu-id="338be-105">Die wichtigste Änderung ist, dass das neue Aktivitätsdesigner-Programmiermodell von Windows Presentation Foundation (WPF) erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="338be-105">The key infrastructural change is that the new activity designer programming model is built upon Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="338be-106">Dies ermöglicht Ihnen, Aktivitätsdesigner deklarativ zu definieren und den [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] in anderen Anwendungen vergleichsweise einfach erneut zu hosten.</span><span class="sxs-lookup"><span data-stu-id="338be-106">This gives you the ability to define activity designers declaratively and to rehost the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] in other applications with comparative easy.</span></span> <span data-ttu-id="338be-107">Beim erneuten Hosten kann ein benutzerdefinierter Ausdrucks-Editor entwickelt werden, um IntelliSense oder eine vereinfachte Ausdrucksdomäne zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="338be-107">When rehosting, a custom expression editor can be developed to support IntelliSense or a simplified expression domain.</span></span> <span data-ttu-id="338be-108">Die Integration mit Windows Communication Foundation (WCF) ist mit der Verwendung von Workflowdiensten nahtloser geworden.</span><span class="sxs-lookup"><span data-stu-id="338be-108">The integration with Windows Communication Foundation (WCF) has become more seamless with use of workflow services.</span></span> <span data-ttu-id="338be-109">Benutzerdefinierte Aktivitätsdesigner und die Modellelementstruktur können verwendet werden, um die Entwurfszeiterfahrung in neu gehosteten Workflowdesignern zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="338be-109">Custom activity designers and the Model Item Tree can be used to enhance design time experiences in rehosted workflow designers.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="338be-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="338be-110">In This Section</span></span>

 [<span data-ttu-id="338be-111">Verwenden benutzerdefinierter Aktivitätsdesigner und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="338be-111">Using Custom Activity Designers and Templates</span></span>](../../../docs/framework/windows-workflow-foundation/using-custom-activity-designers-and-templates.md)

 <span data-ttu-id="338be-112">Beschreibt die Erstellung eines neuen benutzerdefinierten Aktivitätsdesigners und von Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="338be-112">Describes how to create new custom activity designers and templates.</span></span>

 [<span data-ttu-id="338be-113">Erneutes Hosten des Workflow-Designers</span><span class="sxs-lookup"><span data-stu-id="338be-113">Rehosting the Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)

 <span data-ttu-id="338be-114">Beschreibt das erneute hosten die [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] außerhalb von Visual Studio und wie Validierungsfehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="338be-114">Describes how to re-host the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] outside of Visual Studio and how to display validation errors.</span></span>

 [<span data-ttu-id="338be-115">Verwenden eines benutzerdefinierten Ausdrucks-Editors</span><span class="sxs-lookup"><span data-stu-id="338be-115">Using a Custom Expression Editor</span></span>](../../../docs/framework/windows-workflow-foundation/using-a-custom-expression-editor.md)

 <span data-ttu-id="338be-116">Beschreibt, wie einen benutzerdefinierter Ausdrucks-Editor für die Verwendung von workflowdesignern, die außerhalb von Visual Studio 2010 zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="338be-116">Describes how to implement a custom expression editor to use with workflow designers rehosted outside of Visual Studio 2010.</span></span>

## <a name="reference"></a><span data-ttu-id="338be-117">Referenz</span><span class="sxs-lookup"><span data-stu-id="338be-117">Reference</span></span>

<xref:System.Activities.Presentation.ActivityDesigner>

## <a name="see-also"></a><span data-ttu-id="338be-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="338be-118">See Also</span></span>

- [<span data-ttu-id="338be-119">Erweitern der Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="338be-119">Extending Windows Workflow Foundation</span></span>](../../../docs/framework/windows-workflow-foundation/extend.md)
- [<span data-ttu-id="338be-120">Designer</span><span class="sxs-lookup"><span data-stu-id="338be-120">Designer</span></span>](../../../docs/framework/windows-workflow-foundation/samples/designer.md)
- [<span data-ttu-id="338be-121">Benutzerdefinierte Aktivitätsdesigner</span><span class="sxs-lookup"><span data-stu-id="338be-121">Custom Activity Designers</span></span>](../../../docs/framework/windows-workflow-foundation/samples/custom-activity-designers.md)
- [<span data-ttu-id="338be-122">Erneutes Hosten von Designern</span><span class="sxs-lookup"><span data-stu-id="338be-122">Designer ReHosting</span></span>](../../../docs/framework/windows-workflow-foundation/samples/designer-rehosting.md)