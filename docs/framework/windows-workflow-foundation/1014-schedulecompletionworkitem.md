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
ms.openlocfilehash: 3d483a681cae6328dd6111b320a12b5a064d3ff5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="1014---schedulecompletionworkitem"></a><span data-ttu-id="48587-102">1014 - ScheduleCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="48587-102">1014 - ScheduleCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="48587-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="48587-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="48587-104">ID</span><span class="sxs-lookup"><span data-stu-id="48587-104">ID</span></span>|<span data-ttu-id="48587-105">1014</span><span class="sxs-lookup"><span data-stu-id="48587-105">1014</span></span>|  
|<span data-ttu-id="48587-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="48587-106">Keywords</span></span>|<span data-ttu-id="48587-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="48587-107">WFRuntime</span></span>|  
|<span data-ttu-id="48587-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="48587-108">Level</span></span>|<span data-ttu-id="48587-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="48587-109">Verbose</span></span>|  
|<span data-ttu-id="48587-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="48587-110">Channel</span></span>|<span data-ttu-id="48587-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="48587-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="48587-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="48587-112">Description</span></span>  
 <span data-ttu-id="48587-113">Gibt an, dass ein CompletionWorkItem geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="48587-113">Indicates a CompletionWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="48587-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="48587-114">Message</span></span>  
 <span data-ttu-id="48587-115">Wurde eine CompletionWorkItem geplant für die übergeordnete Aktivität '%1', DisplayName: '%2', InstanceId: "%3".</span><span class="sxs-lookup"><span data-stu-id="48587-115">A CompletionWorkItem has been scheduled for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="48587-116">Abgeschlossene Aktivität '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="48587-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="48587-117">Details</span><span class="sxs-lookup"><span data-stu-id="48587-117">Details</span></span>  
  
|<span data-ttu-id="48587-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="48587-118">Data Item Name</span></span>|<span data-ttu-id="48587-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="48587-119">Data Item Type</span></span>|<span data-ttu-id="48587-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="48587-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="48587-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="48587-121">ParentActivity</span></span>|<span data-ttu-id="48587-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="48587-122">xs:string</span></span>|<span data-ttu-id="48587-123">Der Typname der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="48587-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="48587-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="48587-124">ParentDisplayName</span></span>|<span data-ttu-id="48587-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="48587-125">xs:string</span></span>|<span data-ttu-id="48587-126">Der Anzeigename der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="48587-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="48587-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="48587-127">ParentInstanceId</span></span>|<span data-ttu-id="48587-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="48587-128">xs:string</span></span>|<span data-ttu-id="48587-129">Die Instanz-ID der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="48587-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="48587-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="48587-130">CompletedActivity</span></span>|<span data-ttu-id="48587-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="48587-131">xs:string</span></span>|<span data-ttu-id="48587-132">Der Typname der abgeschlossenen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="48587-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="48587-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="48587-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="48587-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="48587-134">xs:string</span></span>|<span data-ttu-id="48587-135">Der Anzeigename der abgeschlossenen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="48587-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="48587-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="48587-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="48587-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="48587-137">xs:string</span></span>|<span data-ttu-id="48587-138">Die Instanz-ID der abgeschlossenen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="48587-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="48587-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="48587-139">AppDomain</span></span>|<span data-ttu-id="48587-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="48587-140">xs:string</span></span>|<span data-ttu-id="48587-141">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="48587-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
