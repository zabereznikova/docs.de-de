---
title: 1002 - WorkflowApplicationTerminated
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4e8b111f-79dc-4898-bb4a-e9b36f69420f
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e3f025be90a997839eec2edfea12a099b4c58f0b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="1002---workflowapplicationterminated"></a><span data-ttu-id="8eb98-102">1002 - WorkflowApplicationTerminated</span><span class="sxs-lookup"><span data-stu-id="8eb98-102">1002 - WorkflowApplicationTerminated</span></span>
## <a name="properties"></a><span data-ttu-id="8eb98-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8eb98-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8eb98-104">ID</span><span class="sxs-lookup"><span data-stu-id="8eb98-104">ID</span></span>|<span data-ttu-id="8eb98-105">1002</span><span class="sxs-lookup"><span data-stu-id="8eb98-105">1002</span></span>|  
|<span data-ttu-id="8eb98-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="8eb98-106">Keywords</span></span>|<span data-ttu-id="8eb98-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="8eb98-107">WFRuntime</span></span>|  
|<span data-ttu-id="8eb98-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="8eb98-108">Level</span></span>|<span data-ttu-id="8eb98-109">Information</span><span class="sxs-lookup"><span data-stu-id="8eb98-109">Information</span></span>|  
|<span data-ttu-id="8eb98-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="8eb98-110">Channel</span></span>|<span data-ttu-id="8eb98-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="8eb98-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8eb98-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8eb98-112">Description</span></span>  
 <span data-ttu-id="8eb98-113">Gibt an, dass eine Workflowanwendung im Faulted-Zustand einer Ausnahme beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="8eb98-113">Indicates a workflow application has terminated in the Faulted state with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8eb98-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="8eb98-114">Message</span></span>  
 <span data-ttu-id="8eb98-115">WorkflowApplication-ID: '%1' wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="8eb98-115">WorkflowApplication Id: '%1' was terminated.</span></span> <span data-ttu-id="8eb98-116">Sie wurde im Faulted-Status mit einer Ausnahme abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="8eb98-116">It has completed in the Faulted state with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8eb98-117">Details</span><span class="sxs-lookup"><span data-stu-id="8eb98-117">Details</span></span>  
  
|<span data-ttu-id="8eb98-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="8eb98-118">Data Item Name</span></span>|<span data-ttu-id="8eb98-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="8eb98-119">Data Item Type</span></span>|<span data-ttu-id="8eb98-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8eb98-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8eb98-121">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="8eb98-121">WorkflowApplicationId</span></span>|`xs:string`|<span data-ttu-id="8eb98-122">Die Workflowanwendungs-ID</span><span class="sxs-lookup"><span data-stu-id="8eb98-122">The workflow application id</span></span>|  
|<span data-ttu-id="8eb98-123">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="8eb98-123">Exception</span></span>|`xs:string`|<span data-ttu-id="8eb98-124">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="8eb98-124">The exception details for the exception</span></span>|  
|<span data-ttu-id="8eb98-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8eb98-125">AppDomain</span></span>|`xs:string`|<span data-ttu-id="8eb98-126">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="8eb98-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
