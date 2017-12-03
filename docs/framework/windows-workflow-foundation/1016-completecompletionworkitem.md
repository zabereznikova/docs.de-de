---
title: 1016 - CompleteCompletionWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 246929fb-6f14-440a-814b-cd8349350644
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b01706f6e84987ea20f52c131139e243e8184c51
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="1016---completecompletionworkitem"></a><span data-ttu-id="91ccb-102">1016 - CompleteCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="91ccb-102">1016 - CompleteCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="91ccb-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="91ccb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="91ccb-104">ID</span><span class="sxs-lookup"><span data-stu-id="91ccb-104">ID</span></span>|<span data-ttu-id="91ccb-105">1016</span><span class="sxs-lookup"><span data-stu-id="91ccb-105">1016</span></span>|  
|<span data-ttu-id="91ccb-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="91ccb-106">Keywords</span></span>|<span data-ttu-id="91ccb-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="91ccb-107">WFRuntime</span></span>|  
|<span data-ttu-id="91ccb-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="91ccb-108">Level</span></span>|<span data-ttu-id="91ccb-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="91ccb-109">Verbose</span></span>|  
|<span data-ttu-id="91ccb-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="91ccb-110">Channel</span></span>|<span data-ttu-id="91ccb-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="91ccb-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="91ccb-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="91ccb-112">Description</span></span>  
 <span data-ttu-id="91ccb-113">Gibt an, dass ein CompletionWorkItem abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="91ccb-113">Indicates a CompletionWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="91ccb-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="91ccb-114">Message</span></span>  
 <span data-ttu-id="91ccb-115">Für die übergeordnete Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde eine CompletionWorkItem abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="91ccb-115">A CompletionWorkItem has completed for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="91ccb-116">Abgeschlossene Aktivität '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="91ccb-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="91ccb-117">Details</span><span class="sxs-lookup"><span data-stu-id="91ccb-117">Details</span></span>  
  
|<span data-ttu-id="91ccb-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="91ccb-118">Data Item Name</span></span>|<span data-ttu-id="91ccb-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="91ccb-119">Data Item Type</span></span>|<span data-ttu-id="91ccb-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="91ccb-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="91ccb-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="91ccb-121">ParentActivity</span></span>|<span data-ttu-id="91ccb-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="91ccb-122">xs:string</span></span>|<span data-ttu-id="91ccb-123">Der Typname der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="91ccb-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="91ccb-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="91ccb-124">ParentDisplayName</span></span>|<span data-ttu-id="91ccb-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="91ccb-125">xs:string</span></span>|<span data-ttu-id="91ccb-126">Der Anzeigename der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="91ccb-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="91ccb-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="91ccb-127">ParentInstanceId</span></span>|<span data-ttu-id="91ccb-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="91ccb-128">xs:string</span></span>|<span data-ttu-id="91ccb-129">Die Instanz-ID der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="91ccb-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="91ccb-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="91ccb-130">CompletedActivity</span></span>|<span data-ttu-id="91ccb-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="91ccb-131">xs:string</span></span>|<span data-ttu-id="91ccb-132">Der Typname der abgeschlossenen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="91ccb-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="91ccb-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="91ccb-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="91ccb-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="91ccb-134">xs:string</span></span>|<span data-ttu-id="91ccb-135">Der Anzeigename der abgeschlossenen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="91ccb-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="91ccb-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="91ccb-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="91ccb-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="91ccb-137">xs:string</span></span>|<span data-ttu-id="91ccb-138">Die Instanz-ID der abgeschlossenen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="91ccb-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="91ccb-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="91ccb-139">AppDomain</span></span>|<span data-ttu-id="91ccb-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="91ccb-140">xs:string</span></span>|<span data-ttu-id="91ccb-141">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="91ccb-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
