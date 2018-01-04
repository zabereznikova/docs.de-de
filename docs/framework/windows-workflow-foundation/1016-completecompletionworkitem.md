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
ms.workload: dotnet
ms.openlocfilehash: 3f9b09001212de6d5aa4f5fde577b9eeb9d967ee
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="1016---completecompletionworkitem"></a><span data-ttu-id="d52e7-102">1016 - CompleteCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="d52e7-102">1016 - CompleteCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="d52e7-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d52e7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d52e7-104">ID</span><span class="sxs-lookup"><span data-stu-id="d52e7-104">ID</span></span>|<span data-ttu-id="d52e7-105">1016</span><span class="sxs-lookup"><span data-stu-id="d52e7-105">1016</span></span>|  
|<span data-ttu-id="d52e7-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d52e7-106">Keywords</span></span>|<span data-ttu-id="d52e7-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="d52e7-107">WFRuntime</span></span>|  
|<span data-ttu-id="d52e7-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="d52e7-108">Level</span></span>|<span data-ttu-id="d52e7-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="d52e7-109">Verbose</span></span>|  
|<span data-ttu-id="d52e7-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="d52e7-110">Channel</span></span>|<span data-ttu-id="d52e7-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="d52e7-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d52e7-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d52e7-112">Description</span></span>  
 <span data-ttu-id="d52e7-113">Gibt an, dass ein CompletionWorkItem abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="d52e7-113">Indicates a CompletionWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d52e7-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="d52e7-114">Message</span></span>  
 <span data-ttu-id="d52e7-115">Für die übergeordnete Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde eine CompletionWorkItem abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="d52e7-115">A CompletionWorkItem has completed for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="d52e7-116">Abgeschlossene Aktivität '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="d52e7-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d52e7-117">Details</span><span class="sxs-lookup"><span data-stu-id="d52e7-117">Details</span></span>  
  
|<span data-ttu-id="d52e7-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="d52e7-118">Data Item Name</span></span>|<span data-ttu-id="d52e7-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="d52e7-119">Data Item Type</span></span>|<span data-ttu-id="d52e7-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d52e7-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d52e7-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="d52e7-121">ParentActivity</span></span>|<span data-ttu-id="d52e7-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="d52e7-122">xs:string</span></span>|<span data-ttu-id="d52e7-123">Der Typname der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="d52e7-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="d52e7-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="d52e7-124">ParentDisplayName</span></span>|<span data-ttu-id="d52e7-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="d52e7-125">xs:string</span></span>|<span data-ttu-id="d52e7-126">Der Anzeigename der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="d52e7-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="d52e7-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="d52e7-127">ParentInstanceId</span></span>|<span data-ttu-id="d52e7-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="d52e7-128">xs:string</span></span>|<span data-ttu-id="d52e7-129">Die Instanz-ID der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="d52e7-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="d52e7-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="d52e7-130">CompletedActivity</span></span>|<span data-ttu-id="d52e7-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="d52e7-131">xs:string</span></span>|<span data-ttu-id="d52e7-132">Der Typname der abgeschlossenen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="d52e7-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="d52e7-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="d52e7-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="d52e7-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="d52e7-134">xs:string</span></span>|<span data-ttu-id="d52e7-135">Der Anzeigename der abgeschlossenen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="d52e7-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="d52e7-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="d52e7-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="d52e7-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="d52e7-137">xs:string</span></span>|<span data-ttu-id="d52e7-138">Die Instanz-ID der abgeschlossenen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="d52e7-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="d52e7-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d52e7-139">AppDomain</span></span>|<span data-ttu-id="d52e7-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="d52e7-140">xs:string</span></span>|<span data-ttu-id="d52e7-141">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="d52e7-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
