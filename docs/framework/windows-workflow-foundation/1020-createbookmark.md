---
title: 1020 - CreateBookmark
ms.date: 03/30/2017
ms.assetid: 4bee948d-816f-4803-85cc-3883b5e23d10
ms.openlocfilehash: 8c9c20fd4fb74f80779c1d2ef8f29ac3d44050d9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275374"
---
# <a name="1020---createbookmark"></a><span data-ttu-id="b1c88-102">1020 - CreateBookmark</span><span class="sxs-lookup"><span data-stu-id="b1c88-102">1020 - CreateBookmark</span></span>

## <a name="properties"></a><span data-ttu-id="b1c88-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="b1c88-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b1c88-104">id</span><span class="sxs-lookup"><span data-stu-id="b1c88-104">ID</span></span>|<span data-ttu-id="b1c88-105">1020</span><span class="sxs-lookup"><span data-stu-id="b1c88-105">1020</span></span>|  
|<span data-ttu-id="b1c88-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="b1c88-106">Keywords</span></span>|<span data-ttu-id="b1c88-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="b1c88-107">WFRuntime</span></span>|  
|<span data-ttu-id="b1c88-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="b1c88-108">Level</span></span>|<span data-ttu-id="b1c88-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="b1c88-109">Verbose</span></span>|  
|<span data-ttu-id="b1c88-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="b1c88-110">Channel</span></span>|<span data-ttu-id="b1c88-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="b1c88-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b1c88-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b1c88-112">Description</span></span>  

 <span data-ttu-id="b1c88-113">Gibt an, dass für eine Aktivität ein Lesezeichen erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="b1c88-113">Indicates a bookmark has been created for an activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b1c88-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="b1c88-114">Message</span></span>  

 <span data-ttu-id="b1c88-115">Für die Aktivität ' %1 ', Display Name: ' %2 ', InstanceId: ' %3 ' wurde ein Lesezeichen erstellt.</span><span class="sxs-lookup"><span data-stu-id="b1c88-115">A Bookmark has been created for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="b1c88-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="b1c88-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b1c88-117">Details</span><span class="sxs-lookup"><span data-stu-id="b1c88-117">Details</span></span>  
  
|<span data-ttu-id="b1c88-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="b1c88-118">Data Item Name</span></span>|<span data-ttu-id="b1c88-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="b1c88-119">Data Item Type</span></span>|<span data-ttu-id="b1c88-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b1c88-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b1c88-121">Aktivität</span><span class="sxs-lookup"><span data-stu-id="b1c88-121">Activity</span></span>|<span data-ttu-id="b1c88-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="b1c88-122">xs:string</span></span>|<span data-ttu-id="b1c88-123">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="b1c88-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="b1c88-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="b1c88-124">DisplayName</span></span>|<span data-ttu-id="b1c88-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="b1c88-125">xs:string</span></span>|<span data-ttu-id="b1c88-126">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="b1c88-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="b1c88-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="b1c88-127">InstanceId</span></span>|<span data-ttu-id="b1c88-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="b1c88-128">xs:string</span></span>|<span data-ttu-id="b1c88-129">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="b1c88-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="b1c88-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="b1c88-130">BookmarkName</span></span>|<span data-ttu-id="b1c88-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="b1c88-131">xs:string</span></span>|<span data-ttu-id="b1c88-132">Der Name des Lesezeichens.</span><span class="sxs-lookup"><span data-stu-id="b1c88-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="b1c88-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="b1c88-133">BookmarkScope</span></span>|<span data-ttu-id="b1c88-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="b1c88-134">xs:string</span></span>|<span data-ttu-id="b1c88-135">Der Bereich des Lesezeichens.</span><span class="sxs-lookup"><span data-stu-id="b1c88-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="b1c88-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b1c88-136">AppDomain</span></span>|<span data-ttu-id="b1c88-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="b1c88-137">xs:string</span></span>|<span data-ttu-id="b1c88-138">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="b1c88-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
