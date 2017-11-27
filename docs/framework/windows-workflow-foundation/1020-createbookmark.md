---
title: 1020 - CreateBookmark
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4bee948d-816f-4803-85cc-3883b5e23d10
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d0584c6eeaf0e08e92ad94e01e1fca765616440f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="1020---createbookmark"></a><span data-ttu-id="49be6-102">1020 - CreateBookmark</span><span class="sxs-lookup"><span data-stu-id="49be6-102">1020 - CreateBookmark</span></span>
## <a name="properties"></a><span data-ttu-id="49be6-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="49be6-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="49be6-104">ID</span><span class="sxs-lookup"><span data-stu-id="49be6-104">ID</span></span>|<span data-ttu-id="49be6-105">1020</span><span class="sxs-lookup"><span data-stu-id="49be6-105">1020</span></span>|  
|<span data-ttu-id="49be6-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="49be6-106">Keywords</span></span>|<span data-ttu-id="49be6-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="49be6-107">WFRuntime</span></span>|  
|<span data-ttu-id="49be6-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="49be6-108">Level</span></span>|<span data-ttu-id="49be6-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="49be6-109">Verbose</span></span>|  
|<span data-ttu-id="49be6-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="49be6-110">Channel</span></span>|<span data-ttu-id="49be6-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="49be6-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="49be6-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="49be6-112">Description</span></span>  
 <span data-ttu-id="49be6-113">Gibt an, dass für eine Aktivität ein Lesezeichen erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="49be6-113">Indicates a bookmark has been created for an activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="49be6-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="49be6-114">Message</span></span>  
 <span data-ttu-id="49be6-115">Ein Lesezeichen erstellt wurde, für die Aktivität '%1', DisplayName: '%2', InstanceId: "%3".</span><span class="sxs-lookup"><span data-stu-id="49be6-115">A Bookmark has been created for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="49be6-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="49be6-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="49be6-117">Details</span><span class="sxs-lookup"><span data-stu-id="49be6-117">Details</span></span>  
  
|<span data-ttu-id="49be6-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="49be6-118">Data Item Name</span></span>|<span data-ttu-id="49be6-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="49be6-119">Data Item Type</span></span>|<span data-ttu-id="49be6-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="49be6-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="49be6-121">Aktivität</span><span class="sxs-lookup"><span data-stu-id="49be6-121">Activity</span></span>|<span data-ttu-id="49be6-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="49be6-122">xs:string</span></span>|<span data-ttu-id="49be6-123">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="49be6-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="49be6-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="49be6-124">DisplayName</span></span>|<span data-ttu-id="49be6-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="49be6-125">xs:string</span></span>|<span data-ttu-id="49be6-126">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="49be6-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="49be6-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="49be6-127">InstanceId</span></span>|<span data-ttu-id="49be6-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="49be6-128">xs:string</span></span>|<span data-ttu-id="49be6-129">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="49be6-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="49be6-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="49be6-130">BookmarkName</span></span>|<span data-ttu-id="49be6-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="49be6-131">xs:string</span></span>|<span data-ttu-id="49be6-132">Der Name des Lesezeichens.</span><span class="sxs-lookup"><span data-stu-id="49be6-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="49be6-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="49be6-133">BookmarkScope</span></span>|<span data-ttu-id="49be6-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="49be6-134">xs:string</span></span>|<span data-ttu-id="49be6-135">Der Bereich des Lesezeichens.</span><span class="sxs-lookup"><span data-stu-id="49be6-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="49be6-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="49be6-136">AppDomain</span></span>|<span data-ttu-id="49be6-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="49be6-137">xs:string</span></span>|<span data-ttu-id="49be6-138">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="49be6-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
