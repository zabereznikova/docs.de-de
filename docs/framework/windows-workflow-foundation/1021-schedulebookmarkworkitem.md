---
title: 1021 - ScheduleBookmarkWorkItem
ms.date: 03/30/2017
ms.assetid: 2e0da311-b219-4637-9460-90cdafcc4ecd
ms.openlocfilehash: abc026165568d05faef619da28c94f27f37eea27
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924422"
---
# <a name="1021---schedulebookmarkworkitem"></a><span data-ttu-id="39640-102">1021 - ScheduleBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="39640-102">1021 - ScheduleBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="39640-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="39640-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="39640-104">ID</span><span class="sxs-lookup"><span data-stu-id="39640-104">ID</span></span>|<span data-ttu-id="39640-105">1021</span><span class="sxs-lookup"><span data-stu-id="39640-105">1021</span></span>|  
|<span data-ttu-id="39640-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="39640-106">Keywords</span></span>|<span data-ttu-id="39640-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="39640-107">WFRuntime</span></span>|  
|<span data-ttu-id="39640-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="39640-108">Level</span></span>|<span data-ttu-id="39640-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="39640-109">Verbose</span></span>|  
|<span data-ttu-id="39640-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="39640-110">Channel</span></span>|<span data-ttu-id="39640-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="39640-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="39640-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="39640-112">Description</span></span>  
 <span data-ttu-id="39640-113">Gibt an, dass ein BookmarkWorkItem geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="39640-113">Indicates a BookmarkWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="39640-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="39640-114">Message</span></span>  
 <span data-ttu-id="39640-115">A BookmarkWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="39640-115">A BookmarkWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="39640-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="39640-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="39640-117">Details</span><span class="sxs-lookup"><span data-stu-id="39640-117">Details</span></span>  
  
|<span data-ttu-id="39640-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="39640-118">Data Item Name</span></span>|<span data-ttu-id="39640-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="39640-119">Data Item Type</span></span>|<span data-ttu-id="39640-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="39640-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="39640-121">Aktivität</span><span class="sxs-lookup"><span data-stu-id="39640-121">Activity</span></span>|<span data-ttu-id="39640-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="39640-122">xs:string</span></span>|<span data-ttu-id="39640-123">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="39640-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="39640-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="39640-124">DisplayName</span></span>|<span data-ttu-id="39640-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="39640-125">xs:string</span></span>|<span data-ttu-id="39640-126">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="39640-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="39640-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="39640-127">InstanceId</span></span>|<span data-ttu-id="39640-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="39640-128">xs:string</span></span>|<span data-ttu-id="39640-129">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="39640-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="39640-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="39640-130">BookmarkName</span></span>|<span data-ttu-id="39640-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="39640-131">xs:string</span></span>|<span data-ttu-id="39640-132">Der Name des Lesezeichens.</span><span class="sxs-lookup"><span data-stu-id="39640-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="39640-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="39640-133">BookmarkScope</span></span>|<span data-ttu-id="39640-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="39640-134">xs:string</span></span>|<span data-ttu-id="39640-135">Der Bereich des Lesezeichens.</span><span class="sxs-lookup"><span data-stu-id="39640-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="39640-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="39640-136">AppDomain</span></span>|<span data-ttu-id="39640-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="39640-137">xs:string</span></span>|<span data-ttu-id="39640-138">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="39640-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
