---
title: Veraltete Typen in Windows Workflow Foundation
ms.date: 03/30/2017
ms.assetid: 4aebe928-a964-4c1c-abf7-0dbbd3604b13
ms.openlocfilehash: 628963650d32237dedbb6ab2a0a2d9a79866af18
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272871"
---
# <a name="deprecated-types-in-windows-workflow-foundation"></a><span data-ttu-id="4c029-102">Veraltete Typen in Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="4c029-102">Deprecated types in Windows Workflow Foundation</span></span>

<span data-ttu-id="4c029-103">In .NET 4 hat das Workflowteam eine neue Workflow-Engine im <xref:System.Activities>-Namespace eingeführt.</span><span class="sxs-lookup"><span data-stu-id="4c029-103">In .NET 4 the Workflow Team released an all new Workflow engine in the <xref:System.Activities> namespace.</span></span> <span data-ttu-id="4c029-104">Mit der Veröffentlichung von .NET Framework 4,5 Beta werden die meisten Typen in den Namespaces "WF 3" <xref:System.Workflow.Activities> , <xref:System.Workflow.ComponentModel> und  <xref:System.Workflow.Runtime> als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="4c029-104">With the release of .NET Framework 4.5 Beta we are marking most of the types in the "WF 3" <xref:System.Workflow.Activities>, <xref:System.Workflow.ComponentModel>, and  <xref:System.Workflow.Runtime> namespaces as obsolete.</span></span>

## <a name="obsolete-namespaces-and-tools"></a><span data-ttu-id="4c029-105">Veraltete Namespaces und Tools</span><span class="sxs-lookup"><span data-stu-id="4c029-105">Obsolete namespaces and tools</span></span>

 <span data-ttu-id="4c029-106">Die folgenden Assemblys enthalten mindestens einen öffentlichen Typ, der veraltet sein wird:</span><span class="sxs-lookup"><span data-stu-id="4c029-106">The following assemblies have one or more public types that will be deprecated:</span></span>

- <span data-ttu-id="4c029-107">System.Workflow.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="4c029-107">System.Workflow.Activities.dll</span></span>

- <span data-ttu-id="4c029-108">System.Workflow.ComponentModel.dll</span><span class="sxs-lookup"><span data-stu-id="4c029-108">System.Workflow.ComponentModel.dll</span></span>

- <span data-ttu-id="4c029-109">System.Workflow.Runtime.dll</span><span class="sxs-lookup"><span data-stu-id="4c029-109">System.Workflow.Runtime.dll</span></span>

- <span data-ttu-id="4c029-110">System.WorkflowServices.dll</span><span class="sxs-lookup"><span data-stu-id="4c029-110">System.WorkflowServices.dll</span></span>

- <span data-ttu-id="4c029-111">Microsoft.Workflow.DebugController.dll</span><span class="sxs-lookup"><span data-stu-id="4c029-111">Microsoft.Workflow.DebugController.dll</span></span>

- <span data-ttu-id="4c029-112">Microsoft.Workflow.Compiler.exe</span><span class="sxs-lookup"><span data-stu-id="4c029-112">Microsoft.Workflow.Compiler.exe</span></span>

- <span data-ttu-id="4c029-113">Wfc.exe</span><span class="sxs-lookup"><span data-stu-id="4c029-113">Wfc.exe</span></span>

 <span data-ttu-id="4c029-114">Daher werden bei Kunden, die veraltete WF3-APIs verwenden, Erstellungswarnungen mit einer Meldung angezeigt, die der folgenden ähnelt:</span><span class="sxs-lookup"><span data-stu-id="4c029-114">As a result, customers who are using the deprecated WF 3 APIs will encounter build warnings with a message similar to the following:</span></span>

 <span data-ttu-id="4c029-115">**Warnung BC40000: X ist veraltet: WF 3-Typen sind veraltet. Verwenden Sie stattdessen WF 4.**</span><span class="sxs-lookup"><span data-stu-id="4c029-115">**Warning BC40000: X is obsolete: WF 3 types are deprecated. Please use WF 4 instead.**</span></span> <span data-ttu-id="4c029-116">In einem zukünftigen Release werden die Typen aus .NET Framework entfernt, doch der genaue Zeitpunkt hierfür steht noch nicht fest (nicht in 4.5).</span><span class="sxs-lookup"><span data-stu-id="4c029-116">We will remove the types from the .NET Framework in a future release, but we have not yet determined that timeframe (not in 4.5).</span></span> <span data-ttu-id="4c029-117">Dieser Schritt ermöglicht es uns, unseren Kunden unsere Pläne mitzuteilen und ihnen ausreichend Zeit zu geben, zum neuen WF4-Modell zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="4c029-117">This current step allows us to communicate our direction to our customers and allow them plenty of time to move to the new WF4 model.</span></span> <span data-ttu-id="4c029-118">Diese WF 3-Typen werden natürlich weiterhin unter der [Microsoft-Support Lifecycle-Richtlinie](/lifecycle/)unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4c029-118">We will, of course, continue to support these WF 3 types under the [Microsoft Support Lifecycle Policy](/lifecycle/).</span></span> <span data-ttu-id="4c029-119">Vorhandene WF3-Anwendungen können ohne Probleme auf .NET Framework 4,5 ausgeführt werden, und Visual Studio 2012 unterstützt neue und vorhandene WF3-basierte Lösungen.</span><span class="sxs-lookup"><span data-stu-id="4c029-119">Existing WF3 applications will run without issue on .NET Framework 4.5, and Visual Studio 2012 will support new and existing WF3-based solutions.</span></span>

 <span data-ttu-id="4c029-120">Regelbezogene Typen im <xref:System.Workflow.Activities.Rules>-Namespace, für die es in WF 4.5 keinen Ersatz gibt, wurden nicht als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="4c029-120">Rules related types in the <xref:System.Workflow.Activities.Rules> namespace, which do not have a replacement in WF 4.5, have not been deprecated.</span></span>

 <span data-ttu-id="4c029-121">Kunden, die Ihre Anwendungen zu WF 4 migrieren möchten, finden Hilfe in der [Migrations Anleitung für Workflow 4](migration-guidance.md).</span><span class="sxs-lookup"><span data-stu-id="4c029-121">Customers who want to migrate their applications to WF 4 will find help in the [Workflow 4 Migration Guidance](migration-guidance.md).</span></span>
