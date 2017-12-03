---
title: Veraltete Typen in Windows Workflow Foundation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4aebe928-a964-4c1c-abf7-0dbbd3604b13
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 422e95a105978749cc56dfe6601fb4518cc11509
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="deprecated-types-in-windows-workflow-foundation"></a><span data-ttu-id="faec7-102">Veraltete Typen in Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="faec7-102">Deprecated types in Windows Workflow Foundation</span></span>
<span data-ttu-id="faec7-103">In .NET 4 hat das Workflowteam ein neues Workflowmodul im <xref:System.Activities>-Namespace eingeführt.</span><span class="sxs-lookup"><span data-stu-id="faec7-103">In .NET 4 the Workflow Team released an all new Workflow engine in the <xref:System.Activities> namespace.</span></span> <span data-ttu-id="faec7-104">Mit der Version von .NET 4.5 Beta werden wir die meisten Typen in den "WF3" markieren <xref:System.Workflow.Activities>, <xref:System.Workflow.ComponentModel>, und <xref:System.Workflow.Runtime> Namespaces als veraltet gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="faec7-104">With the release of .NET 4.5 Beta we are marking most of the types in the "WF 3" <xref:System.Workflow.Activities>, <xref:System.Workflow.ComponentModel>, and  <xref:System.Workflow.Runtime> namespaces as obsolete.</span></span>  
  
## <a name="obsolete-namespaces-and-tools"></a><span data-ttu-id="faec7-105">Veraltete Namespaces und Tools</span><span class="sxs-lookup"><span data-stu-id="faec7-105">Obsolete namespaces and tools</span></span>  
 <span data-ttu-id="faec7-106">Die folgenden Assemblys enthalten mindestens einen öffentlichen Typ, der veraltet sein wird:</span><span class="sxs-lookup"><span data-stu-id="faec7-106">The following assemblies have one or more public types that will be deprecated:</span></span>  
  
-   <span data-ttu-id="faec7-107">System.Workflow.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="faec7-107">System.Workflow.Activities.dll</span></span>  
  
-   <span data-ttu-id="faec7-108">System.Workflow.ComponentModel.dll</span><span class="sxs-lookup"><span data-stu-id="faec7-108">System.Workflow.ComponentModel.dll</span></span>  
  
-   <span data-ttu-id="faec7-109">System.Workflow.Runtime.dll</span><span class="sxs-lookup"><span data-stu-id="faec7-109">System.Workflow.Runtime.dll</span></span>  
  
-   <span data-ttu-id="faec7-110">System.WorkflowServices.dll</span><span class="sxs-lookup"><span data-stu-id="faec7-110">System.WorkflowServices.dll</span></span>  
  
-   <span data-ttu-id="faec7-111">Microsoft.Workflow.DebugController.dll</span><span class="sxs-lookup"><span data-stu-id="faec7-111">Microsoft.Workflow.DebugController.dll</span></span>  
  
-   <span data-ttu-id="faec7-112">Microsoft.Workflow.Compiler.exe</span><span class="sxs-lookup"><span data-stu-id="faec7-112">Microsoft.Workflow.Compiler.exe</span></span>  
  
-   <span data-ttu-id="faec7-113">Wfc.exe</span><span class="sxs-lookup"><span data-stu-id="faec7-113">Wfc.exe</span></span>  
  
 <span data-ttu-id="faec7-114">Daher werden bei Kunden, die veraltete WF3-APIs verwenden, Erstellungswarnungen mit einer Meldung angezeigt, die der folgenden ähnelt:</span><span class="sxs-lookup"><span data-stu-id="faec7-114">As a result, customers who are using the deprecated WF 3 APIs will encounter build warnings with a message similar to the following:</span></span>  
  
 <span data-ttu-id="faec7-115">**Warnung: BC40000 "X" ist veraltet: wf3-Typen sind veraltet. Verwenden Sie stattdessen wf4.**</span><span class="sxs-lookup"><span data-stu-id="faec7-115">**Warning BC40000: X is obsolete: WF 3 types are deprecated. Please use WF 4 instead.**</span></span> <span data-ttu-id="faec7-116">In einem zukünftigen Release werden die Typen aus .NET Framework entfernt, doch der genaue Zeitpunkt hierfür steht noch nicht fest (nicht in 4.5).</span><span class="sxs-lookup"><span data-stu-id="faec7-116">We will remove the types from the .NET Framework in a future release, but we have not yet determined that timeframe (not in 4.5).</span></span> <span data-ttu-id="faec7-117">Dieser Schritt ermöglicht es uns, unseren Kunden unsere Pläne mitzuteilen und ihnen ausreichend Zeit zu geben, zum neuen WF4-Modell zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="faec7-117">This current step allows us to communicate our direction to our customers and allow them plenty of time to move to the new WF4 model.</span></span> <span data-ttu-id="faec7-118">Wir werden natürlich weiterhin für die WF 3 unter Unterstützung der [Microsoft Support Lifecycle-Richtlinie](http://aka.ms/MicrosoftSupportLifecycle).</span><span class="sxs-lookup"><span data-stu-id="faec7-118">We will, of course, continue to support these WF 3 types under the [Microsoft Support Lifecycle Policy](http://aka.ms/MicrosoftSupportLifecycle).</span></span> <span data-ttu-id="faec7-119">Vorhandene WF3-Anwendungen können ohne Probleme unter .NET 4.5 ausgeführt werden. [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] unterstützt neue und vorhandene WF3-basierte Lösungen.</span><span class="sxs-lookup"><span data-stu-id="faec7-119">Existing WF3 applications will run without issue on .NET 4.5, and [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] will support new and existing WF3-based solutions.</span></span>  
  
 <span data-ttu-id="faec7-120">Regelbezogene Typen im <xref:System.Workflow.Activities.Rules>-Namespace, für die es in WF 4.5 keinen Ersatz gibt, wurden nicht als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="faec7-120">Rules related types in the <xref:System.Workflow.Activities.Rules> namespace, which do not have a replacement in WF 4.5, have not been deprecated.</span></span>  
  
 <span data-ttu-id="faec7-121">Kunden, die ihre Anwendungen zu wf4 migrieren möchten, findet in der Hilfe der [Workflow 4 Migrationsanleitung](migration-guidance.md).</span><span class="sxs-lookup"><span data-stu-id="faec7-121">Customers who want to migrate their applications to WF 4 will find help in the [Workflow 4 Migration Guidance](migration-guidance.md).</span></span>
