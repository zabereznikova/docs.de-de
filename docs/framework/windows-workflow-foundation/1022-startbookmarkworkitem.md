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
ms.openlocfilehash: d7df39bd0f6d6d4d309cf5c599ecd3795eb92067
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="1022---startbookmarkworkitem"></a><span data-ttu-id="00024-102">1022 - StartBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="00024-102">1022 - StartBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="00024-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="00024-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="00024-104">ID</span><span class="sxs-lookup"><span data-stu-id="00024-104">ID</span></span>|<span data-ttu-id="00024-105">1022</span><span class="sxs-lookup"><span data-stu-id="00024-105">1022</span></span>|  
|<span data-ttu-id="00024-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="00024-106">Keywords</span></span>|<span data-ttu-id="00024-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="00024-107">WFRuntime</span></span>|  
|<span data-ttu-id="00024-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="00024-108">Level</span></span>|<span data-ttu-id="00024-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="00024-109">Verbose</span></span>|  
|<span data-ttu-id="00024-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="00024-110">Channel</span></span>|<span data-ttu-id="00024-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="00024-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="00024-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00024-112">Description</span></span>  
 <span data-ttu-id="00024-113">Gibt an, dass ein BookmarkWorkItem mit der Ausführung begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="00024-113">Indicates a BookmarkWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="00024-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="00024-114">Message</span></span>  
 <span data-ttu-id="00024-115">Starten der Ausführung ein BookmarkWorkItem für die Aktivität '%1', DisplayName: '%2', InstanceId: "%3".</span><span class="sxs-lookup"><span data-stu-id="00024-115">Starting execution of a BookmarkWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="00024-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="00024-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="00024-117">Details</span><span class="sxs-lookup"><span data-stu-id="00024-117">Details</span></span>  
  
|<span data-ttu-id="00024-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="00024-118">Data Item Name</span></span>|<span data-ttu-id="00024-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="00024-119">Data Item Type</span></span>|<span data-ttu-id="00024-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00024-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="00024-121">Aktivität</span><span class="sxs-lookup"><span data-stu-id="00024-121">Activity</span></span>|<span data-ttu-id="00024-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="00024-122">xs:string</span></span>|<span data-ttu-id="00024-123">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="00024-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="00024-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="00024-124">DisplayName</span></span>|<span data-ttu-id="00024-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="00024-125">xs:string</span></span>|<span data-ttu-id="00024-126">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="00024-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="00024-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="00024-127">InstanceId</span></span>|<span data-ttu-id="00024-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="00024-128">xs:string</span></span>|<span data-ttu-id="00024-129">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="00024-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="00024-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="00024-130">BookmarkName</span></span>|<span data-ttu-id="00024-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="00024-131">xs:string</span></span>|<span data-ttu-id="00024-132">Der Name des Lesezeichens.</span><span class="sxs-lookup"><span data-stu-id="00024-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="00024-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="00024-133">BookmarkScope</span></span>|<span data-ttu-id="00024-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="00024-134">xs:string</span></span>|<span data-ttu-id="00024-135">Der Bereich des Lesezeichens.</span><span class="sxs-lookup"><span data-stu-id="00024-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="00024-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="00024-136">AppDomain</span></span>|<span data-ttu-id="00024-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="00024-137">xs:string</span></span>|<span data-ttu-id="00024-138">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="00024-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
