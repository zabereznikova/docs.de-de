---
title: 1021 - ScheduleBookmarkWorkItem
ms.date: 03/30/2017
ms.assetid: 2e0da311-b219-4637-9460-90cdafcc4ecd
ms.openlocfilehash: 42ed23654622e29df8ffc210c8d5ba572fa69fd4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275348"
---
# <a name="1021---schedulebookmarkworkitem"></a><span data-ttu-id="60cff-102">1021 - ScheduleBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="60cff-102">1021 - ScheduleBookmarkWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="60cff-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="60cff-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="60cff-104">id</span><span class="sxs-lookup"><span data-stu-id="60cff-104">ID</span></span>|<span data-ttu-id="60cff-105">1021</span><span class="sxs-lookup"><span data-stu-id="60cff-105">1021</span></span>|  
|<span data-ttu-id="60cff-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="60cff-106">Keywords</span></span>|<span data-ttu-id="60cff-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="60cff-107">WFRuntime</span></span>|  
|<span data-ttu-id="60cff-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="60cff-108">Level</span></span>|<span data-ttu-id="60cff-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="60cff-109">Verbose</span></span>|  
|<span data-ttu-id="60cff-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="60cff-110">Channel</span></span>|<span data-ttu-id="60cff-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="60cff-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="60cff-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="60cff-112">Description</span></span>  

 <span data-ttu-id="60cff-113">Gibt an, dass ein BookmarkWorkItem geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="60cff-113">Indicates a BookmarkWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="60cff-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="60cff-114">Message</span></span>  

 <span data-ttu-id="60cff-115">Für die Aktivität ' %1 ', Display Name: ' %2 ', InstanceId: ' %3 ' wurde ein bookmarkworkitem geplant.</span><span class="sxs-lookup"><span data-stu-id="60cff-115">A BookmarkWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="60cff-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="60cff-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="60cff-117">Details</span><span class="sxs-lookup"><span data-stu-id="60cff-117">Details</span></span>  
  
|<span data-ttu-id="60cff-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="60cff-118">Data Item Name</span></span>|<span data-ttu-id="60cff-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="60cff-119">Data Item Type</span></span>|<span data-ttu-id="60cff-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="60cff-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="60cff-121">Aktivität</span><span class="sxs-lookup"><span data-stu-id="60cff-121">Activity</span></span>|<span data-ttu-id="60cff-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="60cff-122">xs:string</span></span>|<span data-ttu-id="60cff-123">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="60cff-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="60cff-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="60cff-124">DisplayName</span></span>|<span data-ttu-id="60cff-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="60cff-125">xs:string</span></span>|<span data-ttu-id="60cff-126">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="60cff-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="60cff-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="60cff-127">InstanceId</span></span>|<span data-ttu-id="60cff-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="60cff-128">xs:string</span></span>|<span data-ttu-id="60cff-129">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="60cff-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="60cff-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="60cff-130">BookmarkName</span></span>|<span data-ttu-id="60cff-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="60cff-131">xs:string</span></span>|<span data-ttu-id="60cff-132">Der Name des Lesezeichens.</span><span class="sxs-lookup"><span data-stu-id="60cff-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="60cff-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="60cff-133">BookmarkScope</span></span>|<span data-ttu-id="60cff-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="60cff-134">xs:string</span></span>|<span data-ttu-id="60cff-135">Der Bereich des Lesezeichens.</span><span class="sxs-lookup"><span data-stu-id="60cff-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="60cff-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="60cff-136">AppDomain</span></span>|<span data-ttu-id="60cff-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="60cff-137">xs:string</span></span>|<span data-ttu-id="60cff-138">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="60cff-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
