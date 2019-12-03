---
title: Anpassen des Workflowentwurfsvorgangs
ms.date: 03/30/2017
helpviewer_keywords:
- extending [WF], Workflow Designer
ms.assetid: 98135077-0f5d-4d16-9337-01094e843537
ms.openlocfilehash: 27be398d874747b65ae051224070d3f40f1fbbb0
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715139"
---
# <a name="customizing-the-workflow-design-experience"></a><span data-ttu-id="c3532-102">Anpassen des Workflowentwurfsvorgangs</span><span class="sxs-lookup"><span data-stu-id="c3532-102">Customizing the Workflow Design Experience</span></span>

<span data-ttu-id="c3532-103">Die Szenarien zum Entwerfen von benutzerdefinierten Aktivitäten und zum erneuten Hosting der Windows-Workflow-Designer wurden in .NET Framework 4 erheblich vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="c3532-103">The scenarios for designing custom activities and for rehosting the Windows Workflow Designer have been greatly simplified in .NET Framework 4.</span></span> <span data-ttu-id="c3532-104">Die Entwicklung und Bereitstellung sind jetzt einfacher sowie flexibler.</span><span class="sxs-lookup"><span data-stu-id="c3532-104">Development and deployment are now both easier and more flexible.</span></span> <span data-ttu-id="c3532-105">Die wesentliche Infrastrukturänderung besteht darin, dass das neue Programmiermodell des Aktivitäts Designers auf Windows Presentation Foundation (WPF) aufbaut.</span><span class="sxs-lookup"><span data-stu-id="c3532-105">The key infrastructural change is that the new activity designer programming model is built upon Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="c3532-106">Dadurch haben Sie die Möglichkeit, Aktivitäts Designer deklarativ zu definieren und die Workflow-Designer in anderen Anwendungen mit Vergleichs einfachem Host zu hosten.</span><span class="sxs-lookup"><span data-stu-id="c3532-106">This gives you the ability to define activity designers declaratively and to rehost the Workflow Designer in other applications with comparative easy.</span></span> <span data-ttu-id="c3532-107">Beim erneuten Hosten kann ein benutzerdefinierter Ausdrucks-Editor entwickelt werden, um IntelliSense oder eine vereinfachte Ausdrucksdomäne zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="c3532-107">When rehosting, a custom expression editor can be developed to support IntelliSense or a simplified expression domain.</span></span> <span data-ttu-id="c3532-108">Die Integration mit Windows Communication Foundation (WCF) wurde mit der Verwendung von Workflow Diensten nahtlos.</span><span class="sxs-lookup"><span data-stu-id="c3532-108">The integration with Windows Communication Foundation (WCF) has become more seamless with use of workflow services.</span></span> <span data-ttu-id="c3532-109">Benutzerdefinierte Aktivitätsdesigner und die Modellelementstruktur können verwendet werden, um die Entwurfszeiterfahrung in neu gehosteten Workflowdesignern zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="c3532-109">Custom activity designers and the Model Item Tree can be used to enhance design time experiences in rehosted workflow designers.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="c3532-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c3532-110">In This Section</span></span>

 [<span data-ttu-id="c3532-111">Verwenden benutzerdefinierter Aktivitätsdesigner und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="c3532-111">Using Custom Activity Designers and Templates</span></span>](using-custom-activity-designers-and-templates.md)

 <span data-ttu-id="c3532-112">Beschreibt die Erstellung eines neuen benutzerdefinierten Aktivitätsdesigners und von Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="c3532-112">Describes how to create new custom activity designers and templates.</span></span>

 [<span data-ttu-id="c3532-113">Erneutes Hosten des Workflow-Designers</span><span class="sxs-lookup"><span data-stu-id="c3532-113">Rehosting the Workflow Designer</span></span>](rehosting-the-workflow-designer.md)

 <span data-ttu-id="c3532-114">Hier wird beschrieben, wie Sie die Windows Workflow-Designer außerhalb von Visual Studio neu hosten und Validierungs Fehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="c3532-114">Describes how to re-host the Windows Workflow Designer outside of Visual Studio and how to display validation errors.</span></span>

 [<span data-ttu-id="c3532-115">Verwenden eines benutzerdefinierten Ausdrucks-Editors</span><span class="sxs-lookup"><span data-stu-id="c3532-115">Using a Custom Expression Editor</span></span>](using-a-custom-expression-editor.md)

 <span data-ttu-id="c3532-116">Beschreibt, wie ein benutzerdefinierter Ausdrucks-Editor für die Verwendung mit Workflow-Designern implementiert wird, die außerhalb von Visual Studio 2010 neu gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="c3532-116">Describes how to implement a custom expression editor to use with workflow designers rehosted outside of Visual Studio 2010.</span></span>

## <a name="reference"></a><span data-ttu-id="c3532-117">Referenz</span><span class="sxs-lookup"><span data-stu-id="c3532-117">Reference</span></span>

<xref:System.Activities.Presentation.ActivityDesigner>

## <a name="see-also"></a><span data-ttu-id="c3532-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c3532-118">See also</span></span>

- [<span data-ttu-id="c3532-119">Erweitern der Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="c3532-119">Extending Windows Workflow Foundation</span></span>](extend.md)
- [<span data-ttu-id="c3532-120">Designer</span><span class="sxs-lookup"><span data-stu-id="c3532-120">Designer</span></span>](./samples/designer.md)
- [<span data-ttu-id="c3532-121">Benutzerdefinierte Aktivitätsdesigner</span><span class="sxs-lookup"><span data-stu-id="c3532-121">Custom Activity Designers</span></span>](./samples/custom-activity-designers.md)
- [<span data-ttu-id="c3532-122">Erneutes Hosten von Designern</span><span class="sxs-lookup"><span data-stu-id="c3532-122">Designer ReHosting</span></span>](./samples/designer-rehosting.md)
