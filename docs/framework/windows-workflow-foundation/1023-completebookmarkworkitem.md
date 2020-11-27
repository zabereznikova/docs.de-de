---
title: 1023 - CompleteBookmarkWorkItem
ms.date: 03/30/2017
ms.assetid: fc5dac57-b3eb-4826-b505-c6d269e4774d
ms.openlocfilehash: cb99fd72165182788955021fbedd2aa657b3a098
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275322"
---
# <a name="1023---completebookmarkworkitem"></a><span data-ttu-id="e959e-102">1023 - CompleteBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="e959e-102">1023 - CompleteBookmarkWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="e959e-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="e959e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e959e-104">id</span><span class="sxs-lookup"><span data-stu-id="e959e-104">ID</span></span>|<span data-ttu-id="e959e-105">1023</span><span class="sxs-lookup"><span data-stu-id="e959e-105">1023</span></span>|  
|<span data-ttu-id="e959e-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="e959e-106">Keywords</span></span>|<span data-ttu-id="e959e-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="e959e-107">WFRuntime</span></span>|  
|<span data-ttu-id="e959e-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="e959e-108">Level</span></span>|<span data-ttu-id="e959e-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="e959e-109">Verbose</span></span>|  
|<span data-ttu-id="e959e-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="e959e-110">Channel</span></span>|<span data-ttu-id="e959e-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="e959e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e959e-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e959e-112">Description</span></span>  

 <span data-ttu-id="e959e-113">Gibt an, dass ein BookmarkWorkItem abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="e959e-113">Indicates a BookmarkWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e959e-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="e959e-114">Message</span></span>  

 <span data-ttu-id="e959e-115">Für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde ein BookmarkWorkItem abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="e959e-115">A BookmarkWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="e959e-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="e959e-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e959e-117">Details</span><span class="sxs-lookup"><span data-stu-id="e959e-117">Details</span></span>  
  
|<span data-ttu-id="e959e-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="e959e-118">Data Item Name</span></span>|<span data-ttu-id="e959e-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="e959e-119">Data Item Type</span></span>|<span data-ttu-id="e959e-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e959e-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e959e-121">Aktivität</span><span class="sxs-lookup"><span data-stu-id="e959e-121">Activity</span></span>|<span data-ttu-id="e959e-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="e959e-122">xs:string</span></span>|<span data-ttu-id="e959e-123">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="e959e-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="e959e-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="e959e-124">DisplayName</span></span>|<span data-ttu-id="e959e-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="e959e-125">xs:string</span></span>|<span data-ttu-id="e959e-126">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="e959e-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="e959e-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="e959e-127">InstanceId</span></span>|<span data-ttu-id="e959e-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="e959e-128">xs:string</span></span>|<span data-ttu-id="e959e-129">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="e959e-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="e959e-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="e959e-130">BookmarkName</span></span>|<span data-ttu-id="e959e-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="e959e-131">xs:string</span></span>|<span data-ttu-id="e959e-132">Der Name des Lesezeichens.</span><span class="sxs-lookup"><span data-stu-id="e959e-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="e959e-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="e959e-133">BookmarkScope</span></span>|<span data-ttu-id="e959e-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="e959e-134">xs:string</span></span>|<span data-ttu-id="e959e-135">Der Bereich des Lesezeichens.</span><span class="sxs-lookup"><span data-stu-id="e959e-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="e959e-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e959e-136">AppDomain</span></span>|<span data-ttu-id="e959e-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="e959e-137">xs:string</span></span>|<span data-ttu-id="e959e-138">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="e959e-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
