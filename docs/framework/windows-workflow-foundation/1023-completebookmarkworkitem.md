---
title: 1023 - CompleteBookmarkWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc5dac57-b3eb-4826-b505-c6d269e4774d
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5db5b106a6bc92c288aefe309d33625f57b0ddad
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="1023---completebookmarkworkitem"></a><span data-ttu-id="37620-102">1023 - CompleteBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="37620-102">1023 - CompleteBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="37620-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="37620-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="37620-104">ID</span><span class="sxs-lookup"><span data-stu-id="37620-104">ID</span></span>|<span data-ttu-id="37620-105">1023</span><span class="sxs-lookup"><span data-stu-id="37620-105">1023</span></span>|  
|<span data-ttu-id="37620-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="37620-106">Keywords</span></span>|<span data-ttu-id="37620-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="37620-107">WFRuntime</span></span>|  
|<span data-ttu-id="37620-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="37620-108">Level</span></span>|<span data-ttu-id="37620-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="37620-109">Verbose</span></span>|  
|<span data-ttu-id="37620-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="37620-110">Channel</span></span>|<span data-ttu-id="37620-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="37620-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="37620-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="37620-112">Description</span></span>  
 <span data-ttu-id="37620-113">Gibt an, dass ein BookmarkWorkItem abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="37620-113">Indicates a BookmarkWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="37620-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="37620-114">Message</span></span>  
 <span data-ttu-id="37620-115">Für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde ein BookmarkWorkItem abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="37620-115">A BookmarkWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="37620-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="37620-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="37620-117">Details</span><span class="sxs-lookup"><span data-stu-id="37620-117">Details</span></span>  
  
|<span data-ttu-id="37620-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="37620-118">Data Item Name</span></span>|<span data-ttu-id="37620-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="37620-119">Data Item Type</span></span>|<span data-ttu-id="37620-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="37620-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="37620-121">Aktivität</span><span class="sxs-lookup"><span data-stu-id="37620-121">Activity</span></span>|<span data-ttu-id="37620-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="37620-122">xs:string</span></span>|<span data-ttu-id="37620-123">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="37620-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="37620-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="37620-124">DisplayName</span></span>|<span data-ttu-id="37620-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="37620-125">xs:string</span></span>|<span data-ttu-id="37620-126">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="37620-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="37620-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="37620-127">InstanceId</span></span>|<span data-ttu-id="37620-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="37620-128">xs:string</span></span>|<span data-ttu-id="37620-129">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="37620-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="37620-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="37620-130">BookmarkName</span></span>|<span data-ttu-id="37620-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="37620-131">xs:string</span></span>|<span data-ttu-id="37620-132">Der Name des Lesezeichens.</span><span class="sxs-lookup"><span data-stu-id="37620-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="37620-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="37620-133">BookmarkScope</span></span>|<span data-ttu-id="37620-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="37620-134">xs:string</span></span>|<span data-ttu-id="37620-135">Der Bereich des Lesezeichens.</span><span class="sxs-lookup"><span data-stu-id="37620-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="37620-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="37620-136">AppDomain</span></span>|<span data-ttu-id="37620-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="37620-137">xs:string</span></span>|<span data-ttu-id="37620-138">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="37620-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
