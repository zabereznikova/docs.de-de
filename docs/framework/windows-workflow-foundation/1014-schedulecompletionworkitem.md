---
title: 1014 - ScheduleCompletionWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 84203735-478d-42d8-a320-c175dbddcb38
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a80406ce56000703555f7834714222e03d2b65f1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="1014---schedulecompletionworkitem"></a><span data-ttu-id="1ccd9-102">1014 - ScheduleCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="1ccd9-102">1014 - ScheduleCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="1ccd9-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1ccd9-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1ccd9-104">ID</span><span class="sxs-lookup"><span data-stu-id="1ccd9-104">ID</span></span>|<span data-ttu-id="1ccd9-105">1014</span><span class="sxs-lookup"><span data-stu-id="1ccd9-105">1014</span></span>|  
|<span data-ttu-id="1ccd9-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="1ccd9-106">Keywords</span></span>|<span data-ttu-id="1ccd9-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="1ccd9-107">WFRuntime</span></span>|  
|<span data-ttu-id="1ccd9-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="1ccd9-108">Level</span></span>|<span data-ttu-id="1ccd9-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="1ccd9-109">Verbose</span></span>|  
|<span data-ttu-id="1ccd9-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="1ccd9-110">Channel</span></span>|<span data-ttu-id="1ccd9-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="1ccd9-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1ccd9-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1ccd9-112">Description</span></span>  
 <span data-ttu-id="1ccd9-113">Gibt an, dass ein CompletionWorkItem geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="1ccd9-113">Indicates a CompletionWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1ccd9-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="1ccd9-114">Message</span></span>  
 <span data-ttu-id="1ccd9-115">Wurde eine CompletionWorkItem geplant für die übergeordnete Aktivität '%1', DisplayName: '%2', InstanceId: "%3".</span><span class="sxs-lookup"><span data-stu-id="1ccd9-115">A CompletionWorkItem has been scheduled for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="1ccd9-116">Abgeschlossene Aktivität '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="1ccd9-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1ccd9-117">Details</span><span class="sxs-lookup"><span data-stu-id="1ccd9-117">Details</span></span>  
  
|<span data-ttu-id="1ccd9-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="1ccd9-118">Data Item Name</span></span>|<span data-ttu-id="1ccd9-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="1ccd9-119">Data Item Type</span></span>|<span data-ttu-id="1ccd9-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1ccd9-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1ccd9-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="1ccd9-121">ParentActivity</span></span>|<span data-ttu-id="1ccd9-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="1ccd9-122">xs:string</span></span>|<span data-ttu-id="1ccd9-123">Der Typname der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="1ccd9-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="1ccd9-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="1ccd9-124">ParentDisplayName</span></span>|<span data-ttu-id="1ccd9-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="1ccd9-125">xs:string</span></span>|<span data-ttu-id="1ccd9-126">Der Anzeigename der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="1ccd9-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="1ccd9-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="1ccd9-127">ParentInstanceId</span></span>|<span data-ttu-id="1ccd9-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="1ccd9-128">xs:string</span></span>|<span data-ttu-id="1ccd9-129">Die Instanz-ID der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="1ccd9-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="1ccd9-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="1ccd9-130">CompletedActivity</span></span>|<span data-ttu-id="1ccd9-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="1ccd9-131">xs:string</span></span>|<span data-ttu-id="1ccd9-132">Der Typname der abgeschlossenen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="1ccd9-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="1ccd9-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="1ccd9-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="1ccd9-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="1ccd9-134">xs:string</span></span>|<span data-ttu-id="1ccd9-135">Der Anzeigename der abgeschlossenen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="1ccd9-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="1ccd9-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="1ccd9-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="1ccd9-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="1ccd9-137">xs:string</span></span>|<span data-ttu-id="1ccd9-138">Die Instanz-ID der abgeschlossenen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="1ccd9-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="1ccd9-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1ccd9-139">AppDomain</span></span>|<span data-ttu-id="1ccd9-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="1ccd9-140">xs:string</span></span>|<span data-ttu-id="1ccd9-141">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="1ccd9-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
