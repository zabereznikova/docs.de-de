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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3dc30100cb134740f51e6b2b38c00b2054d2ab0a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="1021---schedulebookmarkworkitem"></a><span data-ttu-id="877c2-102">1021 - ScheduleBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="877c2-102">1021 - ScheduleBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="877c2-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="877c2-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="877c2-104">ID</span><span class="sxs-lookup"><span data-stu-id="877c2-104">ID</span></span>|<span data-ttu-id="877c2-105">1021</span><span class="sxs-lookup"><span data-stu-id="877c2-105">1021</span></span>|  
|<span data-ttu-id="877c2-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="877c2-106">Keywords</span></span>|<span data-ttu-id="877c2-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="877c2-107">WFRuntime</span></span>|  
|<span data-ttu-id="877c2-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="877c2-108">Level</span></span>|<span data-ttu-id="877c2-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="877c2-109">Verbose</span></span>|  
|<span data-ttu-id="877c2-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="877c2-110">Channel</span></span>|<span data-ttu-id="877c2-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="877c2-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="877c2-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="877c2-112">Description</span></span>  
 <span data-ttu-id="877c2-113">Gibt an, dass ein BookmarkWorkItem geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="877c2-113">Indicates a BookmarkWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="877c2-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="877c2-114">Message</span></span>  
 <span data-ttu-id="877c2-115">Wurde ein BookmarkWorkItem geplant für die Aktivität '%1', DisplayName: '%2', InstanceId: "%3".</span><span class="sxs-lookup"><span data-stu-id="877c2-115">A BookmarkWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="877c2-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="877c2-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="877c2-117">Details</span><span class="sxs-lookup"><span data-stu-id="877c2-117">Details</span></span>  
  
|<span data-ttu-id="877c2-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="877c2-118">Data Item Name</span></span>|<span data-ttu-id="877c2-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="877c2-119">Data Item Type</span></span>|<span data-ttu-id="877c2-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="877c2-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="877c2-121">Aktivität</span><span class="sxs-lookup"><span data-stu-id="877c2-121">Activity</span></span>|<span data-ttu-id="877c2-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="877c2-122">xs:string</span></span>|<span data-ttu-id="877c2-123">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="877c2-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="877c2-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="877c2-124">DisplayName</span></span>|<span data-ttu-id="877c2-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="877c2-125">xs:string</span></span>|<span data-ttu-id="877c2-126">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="877c2-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="877c2-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="877c2-127">InstanceId</span></span>|<span data-ttu-id="877c2-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="877c2-128">xs:string</span></span>|<span data-ttu-id="877c2-129">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="877c2-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="877c2-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="877c2-130">BookmarkName</span></span>|<span data-ttu-id="877c2-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="877c2-131">xs:string</span></span>|<span data-ttu-id="877c2-132">Der Name des Lesezeichens.</span><span class="sxs-lookup"><span data-stu-id="877c2-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="877c2-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="877c2-133">BookmarkScope</span></span>|<span data-ttu-id="877c2-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="877c2-134">xs:string</span></span>|<span data-ttu-id="877c2-135">Der Bereich des Lesezeichens.</span><span class="sxs-lookup"><span data-stu-id="877c2-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="877c2-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="877c2-136">AppDomain</span></span>|<span data-ttu-id="877c2-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="877c2-137">xs:string</span></span>|<span data-ttu-id="877c2-138">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="877c2-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
