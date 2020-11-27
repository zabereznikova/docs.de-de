---
title: 1022 - StartBookmarkWorkItem
ms.date: 03/30/2017
ms.assetid: 4415fbdb-0329-4019-803f-aea66e75f3da
ms.openlocfilehash: ca1f4244fb1a5144cb2d86eaacb9b31137d317c2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275335"
---
# <a name="1022---startbookmarkworkitem"></a><span data-ttu-id="297be-102">1022 - StartBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="297be-102">1022 - StartBookmarkWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="297be-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="297be-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="297be-104">id</span><span class="sxs-lookup"><span data-stu-id="297be-104">ID</span></span>|<span data-ttu-id="297be-105">1022</span><span class="sxs-lookup"><span data-stu-id="297be-105">1022</span></span>|  
|<span data-ttu-id="297be-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="297be-106">Keywords</span></span>|<span data-ttu-id="297be-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="297be-107">WFRuntime</span></span>|  
|<span data-ttu-id="297be-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="297be-108">Level</span></span>|<span data-ttu-id="297be-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="297be-109">Verbose</span></span>|  
|<span data-ttu-id="297be-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="297be-110">Channel</span></span>|<span data-ttu-id="297be-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="297be-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="297be-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="297be-112">Description</span></span>  

 <span data-ttu-id="297be-113">Gibt an, dass ein BookmarkWorkItem mit der Ausführung begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="297be-113">Indicates a BookmarkWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="297be-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="297be-114">Message</span></span>  

 <span data-ttu-id="297be-115">Die Ausführung eines bookmarkworkitem für die Aktivität ' %1 ', Display Name: ' %2 ', InstanceId: ' %3 ' wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="297be-115">Starting execution of a BookmarkWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="297be-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="297be-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="297be-117">Details</span><span class="sxs-lookup"><span data-stu-id="297be-117">Details</span></span>  
  
|<span data-ttu-id="297be-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="297be-118">Data Item Name</span></span>|<span data-ttu-id="297be-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="297be-119">Data Item Type</span></span>|<span data-ttu-id="297be-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="297be-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="297be-121">Aktivität</span><span class="sxs-lookup"><span data-stu-id="297be-121">Activity</span></span>|<span data-ttu-id="297be-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="297be-122">xs:string</span></span>|<span data-ttu-id="297be-123">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="297be-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="297be-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="297be-124">DisplayName</span></span>|<span data-ttu-id="297be-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="297be-125">xs:string</span></span>|<span data-ttu-id="297be-126">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="297be-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="297be-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="297be-127">InstanceId</span></span>|<span data-ttu-id="297be-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="297be-128">xs:string</span></span>|<span data-ttu-id="297be-129">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="297be-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="297be-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="297be-130">BookmarkName</span></span>|<span data-ttu-id="297be-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="297be-131">xs:string</span></span>|<span data-ttu-id="297be-132">Der Name des Lesezeichens.</span><span class="sxs-lookup"><span data-stu-id="297be-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="297be-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="297be-133">BookmarkScope</span></span>|<span data-ttu-id="297be-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="297be-134">xs:string</span></span>|<span data-ttu-id="297be-135">Der Bereich des Lesezeichens.</span><span class="sxs-lookup"><span data-stu-id="297be-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="297be-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="297be-136">AppDomain</span></span>|<span data-ttu-id="297be-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="297be-137">xs:string</span></span>|<span data-ttu-id="297be-138">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="297be-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
