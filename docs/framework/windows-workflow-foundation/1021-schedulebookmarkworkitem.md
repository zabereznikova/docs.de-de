---
title: 1021 - ScheduleBookmarkWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e0da311-b219-4637-9460-90cdafcc4ecd
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 61c67792f807907f58480f3bfa3d192b811766b4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="1021---schedulebookmarkworkitem"></a><span data-ttu-id="87c52-102">1021 - ScheduleBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="87c52-102">1021 - ScheduleBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="87c52-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="87c52-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="87c52-104">ID</span><span class="sxs-lookup"><span data-stu-id="87c52-104">ID</span></span>|<span data-ttu-id="87c52-105">1021</span><span class="sxs-lookup"><span data-stu-id="87c52-105">1021</span></span>|  
|<span data-ttu-id="87c52-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="87c52-106">Keywords</span></span>|<span data-ttu-id="87c52-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="87c52-107">WFRuntime</span></span>|  
|<span data-ttu-id="87c52-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="87c52-108">Level</span></span>|<span data-ttu-id="87c52-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="87c52-109">Verbose</span></span>|  
|<span data-ttu-id="87c52-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="87c52-110">Channel</span></span>|<span data-ttu-id="87c52-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="87c52-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="87c52-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="87c52-112">Description</span></span>  
 <span data-ttu-id="87c52-113">Gibt an, dass ein BookmarkWorkItem geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="87c52-113">Indicates a BookmarkWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="87c52-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="87c52-114">Message</span></span>  
 <span data-ttu-id="87c52-115">Wurde ein BookmarkWorkItem geplant für die Aktivität '%1', DisplayName: '%2', InstanceId: "%3".</span><span class="sxs-lookup"><span data-stu-id="87c52-115">A BookmarkWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="87c52-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="87c52-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="87c52-117">Details</span><span class="sxs-lookup"><span data-stu-id="87c52-117">Details</span></span>  
  
|<span data-ttu-id="87c52-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="87c52-118">Data Item Name</span></span>|<span data-ttu-id="87c52-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="87c52-119">Data Item Type</span></span>|<span data-ttu-id="87c52-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="87c52-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="87c52-121">Aktivität</span><span class="sxs-lookup"><span data-stu-id="87c52-121">Activity</span></span>|<span data-ttu-id="87c52-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="87c52-122">xs:string</span></span>|<span data-ttu-id="87c52-123">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="87c52-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="87c52-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="87c52-124">DisplayName</span></span>|<span data-ttu-id="87c52-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="87c52-125">xs:string</span></span>|<span data-ttu-id="87c52-126">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="87c52-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="87c52-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="87c52-127">InstanceId</span></span>|<span data-ttu-id="87c52-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="87c52-128">xs:string</span></span>|<span data-ttu-id="87c52-129">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="87c52-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="87c52-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="87c52-130">BookmarkName</span></span>|<span data-ttu-id="87c52-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="87c52-131">xs:string</span></span>|<span data-ttu-id="87c52-132">Der Name des Lesezeichens.</span><span class="sxs-lookup"><span data-stu-id="87c52-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="87c52-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="87c52-133">BookmarkScope</span></span>|<span data-ttu-id="87c52-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="87c52-134">xs:string</span></span>|<span data-ttu-id="87c52-135">Der Bereich des Lesezeichens.</span><span class="sxs-lookup"><span data-stu-id="87c52-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="87c52-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="87c52-136">AppDomain</span></span>|<span data-ttu-id="87c52-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="87c52-137">xs:string</span></span>|<span data-ttu-id="87c52-138">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="87c52-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
