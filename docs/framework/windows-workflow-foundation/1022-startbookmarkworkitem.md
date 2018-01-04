---
title: 1022 - StartBookmarkWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4415fbdb-0329-4019-803f-aea66e75f3da
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cdb6af10c45e7a93e9a68e6150e5d239002cce04
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="1022---startbookmarkworkitem"></a><span data-ttu-id="8442c-102">1022 - StartBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="8442c-102">1022 - StartBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="8442c-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8442c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8442c-104">ID</span><span class="sxs-lookup"><span data-stu-id="8442c-104">ID</span></span>|<span data-ttu-id="8442c-105">1022</span><span class="sxs-lookup"><span data-stu-id="8442c-105">1022</span></span>|  
|<span data-ttu-id="8442c-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="8442c-106">Keywords</span></span>|<span data-ttu-id="8442c-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="8442c-107">WFRuntime</span></span>|  
|<span data-ttu-id="8442c-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="8442c-108">Level</span></span>|<span data-ttu-id="8442c-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="8442c-109">Verbose</span></span>|  
|<span data-ttu-id="8442c-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="8442c-110">Channel</span></span>|<span data-ttu-id="8442c-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="8442c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8442c-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8442c-112">Description</span></span>  
 <span data-ttu-id="8442c-113">Gibt an, dass ein BookmarkWorkItem mit der Ausführung begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="8442c-113">Indicates a BookmarkWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8442c-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="8442c-114">Message</span></span>  
 <span data-ttu-id="8442c-115">Starten der Ausführung ein BookmarkWorkItem für die Aktivität '%1', DisplayName: '%2', InstanceId: "%3".</span><span class="sxs-lookup"><span data-stu-id="8442c-115">Starting execution of a BookmarkWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="8442c-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="8442c-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8442c-117">Details</span><span class="sxs-lookup"><span data-stu-id="8442c-117">Details</span></span>  
  
|<span data-ttu-id="8442c-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="8442c-118">Data Item Name</span></span>|<span data-ttu-id="8442c-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="8442c-119">Data Item Type</span></span>|<span data-ttu-id="8442c-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8442c-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8442c-121">Aktivität</span><span class="sxs-lookup"><span data-stu-id="8442c-121">Activity</span></span>|<span data-ttu-id="8442c-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="8442c-122">xs:string</span></span>|<span data-ttu-id="8442c-123">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="8442c-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="8442c-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="8442c-124">DisplayName</span></span>|<span data-ttu-id="8442c-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="8442c-125">xs:string</span></span>|<span data-ttu-id="8442c-126">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="8442c-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="8442c-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="8442c-127">InstanceId</span></span>|<span data-ttu-id="8442c-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="8442c-128">xs:string</span></span>|<span data-ttu-id="8442c-129">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="8442c-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="8442c-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="8442c-130">BookmarkName</span></span>|<span data-ttu-id="8442c-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="8442c-131">xs:string</span></span>|<span data-ttu-id="8442c-132">Der Name des Lesezeichens.</span><span class="sxs-lookup"><span data-stu-id="8442c-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="8442c-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="8442c-133">BookmarkScope</span></span>|<span data-ttu-id="8442c-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="8442c-134">xs:string</span></span>|<span data-ttu-id="8442c-135">Der Bereich des Lesezeichens.</span><span class="sxs-lookup"><span data-stu-id="8442c-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="8442c-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8442c-136">AppDomain</span></span>|<span data-ttu-id="8442c-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="8442c-137">xs:string</span></span>|<span data-ttu-id="8442c-138">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="8442c-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
