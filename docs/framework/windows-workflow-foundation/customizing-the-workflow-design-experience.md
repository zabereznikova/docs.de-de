---
title: Anpassen des Workflowentwurfsvorgangs
ms.date: 03/30/2017
helpviewer_keywords:
- extending [WF], Workflow Designer
ms.assetid: 98135077-0f5d-4d16-9337-01094e843537
ms.openlocfilehash: 41be55391ae9481f6c2e4feb76443f7fb676b69d
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141922"
---
# <a name="customizing-the-workflow-design-experience"></a><span data-ttu-id="e37a5-102">Anpassen des Workflowentwurfsvorgangs</span><span class="sxs-lookup"><span data-stu-id="e37a5-102">Customizing the Workflow Design Experience</span></span>

<span data-ttu-id="e37a5-103">Die Szenarien zum Entwerfen von benutzerdefinierten Aktivitäten und zum erneuten Hosting der [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] wurden in .NET Framework 4 erheblich vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="e37a5-103">The scenarios for designing custom activities and for rehosting the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] have been greatly simplified in .NET Framework 4.</span></span> <span data-ttu-id="e37a5-104">Die Entwicklung und Bereitstellung sind jetzt einfacher sowie flexibler.</span><span class="sxs-lookup"><span data-stu-id="e37a5-104">Development and deployment are now both easier and more flexible.</span></span> <span data-ttu-id="e37a5-105">Die wesentliche Infrastrukturänderung besteht darin, dass das neue Programmiermodell des Aktivitäts Designers auf Windows Presentation Foundation (WPF) aufbaut.</span><span class="sxs-lookup"><span data-stu-id="e37a5-105">The key infrastructural change is that the new activity designer programming model is built upon Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="e37a5-106">Dies ermöglicht Ihnen, Aktivitätsdesigner deklarativ zu definieren und den [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] in anderen Anwendungen vergleichsweise einfach erneut zu hosten.</span><span class="sxs-lookup"><span data-stu-id="e37a5-106">This gives you the ability to define activity designers declaratively and to rehost the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] in other applications with comparative easy.</span></span> <span data-ttu-id="e37a5-107">Beim erneuten Hosten kann ein benutzerdefinierter Ausdrucks-Editor entwickelt werden, um IntelliSense oder eine vereinfachte Ausdrucksdomäne zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e37a5-107">When rehosting, a custom expression editor can be developed to support IntelliSense or a simplified expression domain.</span></span> <span data-ttu-id="e37a5-108">Die Integration mit Windows Communication Foundation (WCF) wurde mit der Verwendung von Workflow Diensten nahtlos.</span><span class="sxs-lookup"><span data-stu-id="e37a5-108">The integration with Windows Communication Foundation (WCF) has become more seamless with use of workflow services.</span></span> <span data-ttu-id="e37a5-109">Benutzerdefinierte Aktivitätsdesigner und die Modellelementstruktur können verwendet werden, um die Entwurfszeiterfahrung in neu gehosteten Workflowdesignern zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="e37a5-109">Custom activity designers and the Model Item Tree can be used to enhance design time experiences in rehosted workflow designers.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="e37a5-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e37a5-110">In This Section</span></span>

 [<span data-ttu-id="e37a5-111">Verwenden benutzerdefinierter Aktivitätsdesigner und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="e37a5-111">Using Custom Activity Designers and Templates</span></span>](using-custom-activity-designers-and-templates.md)

 <span data-ttu-id="e37a5-112">Beschreibt die Erstellung eines neuen benutzerdefinierten Aktivitätsdesigners und von Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="e37a5-112">Describes how to create new custom activity designers and templates.</span></span>

 [<span data-ttu-id="e37a5-113">Erneutes Hosten des Workflow-Designers</span><span class="sxs-lookup"><span data-stu-id="e37a5-113">Rehosting the Workflow Designer</span></span>](rehosting-the-workflow-designer.md)

 <span data-ttu-id="e37a5-114">Hier wird beschrieben, wie Sie die [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] außerhalb von Visual Studio neu hosten und Validierungs Fehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="e37a5-114">Describes how to re-host the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] outside of Visual Studio and how to display validation errors.</span></span>

 [<span data-ttu-id="e37a5-115">Verwenden eines benutzerdefinierten Ausdrucks-Editors</span><span class="sxs-lookup"><span data-stu-id="e37a5-115">Using a Custom Expression Editor</span></span>](using-a-custom-expression-editor.md)

 <span data-ttu-id="e37a5-116">Beschreibt, wie ein benutzerdefinierter Ausdrucks-Editor für die Verwendung mit Workflow-Designern implementiert wird, die außerhalb von Visual Studio 2010 neu gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="e37a5-116">Describes how to implement a custom expression editor to use with workflow designers rehosted outside of Visual Studio 2010.</span></span>

## <a name="reference"></a><span data-ttu-id="e37a5-117">Referenz</span><span class="sxs-lookup"><span data-stu-id="e37a5-117">Reference</span></span>

<xref:System.Activities.Presentation.ActivityDesigner>

## <a name="see-also"></a><span data-ttu-id="e37a5-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e37a5-118">See also</span></span>

- [<span data-ttu-id="e37a5-119">Erweitern der Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="e37a5-119">Extending Windows Workflow Foundation</span></span>](extend.md)
- [<span data-ttu-id="e37a5-120">Designer</span><span class="sxs-lookup"><span data-stu-id="e37a5-120">Designer</span></span>](./samples/designer.md)
- [<span data-ttu-id="e37a5-121">Benutzerdefinierte Aktivitätsdesigner</span><span class="sxs-lookup"><span data-stu-id="e37a5-121">Custom Activity Designers</span></span>](./samples/custom-activity-designers.md)
- [<span data-ttu-id="e37a5-122">Erneutes Hosten von Designern</span><span class="sxs-lookup"><span data-stu-id="e37a5-122">Designer ReHosting</span></span>](./samples/designer-rehosting.md)
