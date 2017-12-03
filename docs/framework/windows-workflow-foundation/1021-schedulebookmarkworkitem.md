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
ms.openlocfilehash: 781f4b6d064ac90f762e10e03783422c64a1bf05
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="1021---schedulebookmarkworkitem"></a><span data-ttu-id="8390d-102">1021 - ScheduleBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="8390d-102">1021 - ScheduleBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="8390d-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8390d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8390d-104">ID</span><span class="sxs-lookup"><span data-stu-id="8390d-104">ID</span></span>|<span data-ttu-id="8390d-105">1021</span><span class="sxs-lookup"><span data-stu-id="8390d-105">1021</span></span>|  
|<span data-ttu-id="8390d-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="8390d-106">Keywords</span></span>|<span data-ttu-id="8390d-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="8390d-107">WFRuntime</span></span>|  
|<span data-ttu-id="8390d-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="8390d-108">Level</span></span>|<span data-ttu-id="8390d-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="8390d-109">Verbose</span></span>|  
|<span data-ttu-id="8390d-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="8390d-110">Channel</span></span>|<span data-ttu-id="8390d-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="8390d-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8390d-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8390d-112">Description</span></span>  
 <span data-ttu-id="8390d-113">Gibt an, dass ein BookmarkWorkItem geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="8390d-113">Indicates a BookmarkWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8390d-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="8390d-114">Message</span></span>  
 <span data-ttu-id="8390d-115">Wurde ein BookmarkWorkItem geplant für die Aktivität '%1', DisplayName: '%2', InstanceId: "%3".</span><span class="sxs-lookup"><span data-stu-id="8390d-115">A BookmarkWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="8390d-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="8390d-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8390d-117">Details</span><span class="sxs-lookup"><span data-stu-id="8390d-117">Details</span></span>  
  
|<span data-ttu-id="8390d-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="8390d-118">Data Item Name</span></span>|<span data-ttu-id="8390d-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="8390d-119">Data Item Type</span></span>|<span data-ttu-id="8390d-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8390d-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8390d-121">Aktivität</span><span class="sxs-lookup"><span data-stu-id="8390d-121">Activity</span></span>|<span data-ttu-id="8390d-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="8390d-122">xs:string</span></span>|<span data-ttu-id="8390d-123">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="8390d-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="8390d-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="8390d-124">DisplayName</span></span>|<span data-ttu-id="8390d-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="8390d-125">xs:string</span></span>|<span data-ttu-id="8390d-126">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="8390d-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="8390d-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="8390d-127">InstanceId</span></span>|<span data-ttu-id="8390d-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="8390d-128">xs:string</span></span>|<span data-ttu-id="8390d-129">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="8390d-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="8390d-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="8390d-130">BookmarkName</span></span>|<span data-ttu-id="8390d-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="8390d-131">xs:string</span></span>|<span data-ttu-id="8390d-132">Der Name des Lesezeichens.</span><span class="sxs-lookup"><span data-stu-id="8390d-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="8390d-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="8390d-133">BookmarkScope</span></span>|<span data-ttu-id="8390d-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="8390d-134">xs:string</span></span>|<span data-ttu-id="8390d-135">Der Bereich des Lesezeichens.</span><span class="sxs-lookup"><span data-stu-id="8390d-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="8390d-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8390d-136">AppDomain</span></span>|<span data-ttu-id="8390d-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="8390d-137">xs:string</span></span>|<span data-ttu-id="8390d-138">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="8390d-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
