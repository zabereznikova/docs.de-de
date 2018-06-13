---
title: 1022 - StartBookmarkWorkItem
ms.date: 03/30/2017
ms.assetid: 4415fbdb-0329-4019-803f-aea66e75f3da
ms.openlocfilehash: 93d906b32b51effaa709da6763f535708cd6f821
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509807"
---
# <a name="1022---startbookmarkworkitem"></a><span data-ttu-id="8e8b9-102">1022 - StartBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="8e8b9-102">1022 - StartBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="8e8b9-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8e8b9-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8e8b9-104">ID</span><span class="sxs-lookup"><span data-stu-id="8e8b9-104">ID</span></span>|<span data-ttu-id="8e8b9-105">1022</span><span class="sxs-lookup"><span data-stu-id="8e8b9-105">1022</span></span>|  
|<span data-ttu-id="8e8b9-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="8e8b9-106">Keywords</span></span>|<span data-ttu-id="8e8b9-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="8e8b9-107">WFRuntime</span></span>|  
|<span data-ttu-id="8e8b9-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="8e8b9-108">Level</span></span>|<span data-ttu-id="8e8b9-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="8e8b9-109">Verbose</span></span>|  
|<span data-ttu-id="8e8b9-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="8e8b9-110">Channel</span></span>|<span data-ttu-id="8e8b9-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="8e8b9-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8e8b9-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8e8b9-112">Description</span></span>  
 <span data-ttu-id="8e8b9-113">Gibt an, dass ein BookmarkWorkItem mit der Ausführung begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="8e8b9-113">Indicates a BookmarkWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8e8b9-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="8e8b9-114">Message</span></span>  
 <span data-ttu-id="8e8b9-115">Starten der Ausführung ein BookmarkWorkItem für die Aktivität '%1', DisplayName: '%2', InstanceId: "%3".</span><span class="sxs-lookup"><span data-stu-id="8e8b9-115">Starting execution of a BookmarkWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="8e8b9-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="8e8b9-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8e8b9-117">Details</span><span class="sxs-lookup"><span data-stu-id="8e8b9-117">Details</span></span>  
  
|<span data-ttu-id="8e8b9-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="8e8b9-118">Data Item Name</span></span>|<span data-ttu-id="8e8b9-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="8e8b9-119">Data Item Type</span></span>|<span data-ttu-id="8e8b9-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8e8b9-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8e8b9-121">Aktivität</span><span class="sxs-lookup"><span data-stu-id="8e8b9-121">Activity</span></span>|<span data-ttu-id="8e8b9-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="8e8b9-122">xs:string</span></span>|<span data-ttu-id="8e8b9-123">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="8e8b9-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="8e8b9-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="8e8b9-124">DisplayName</span></span>|<span data-ttu-id="8e8b9-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="8e8b9-125">xs:string</span></span>|<span data-ttu-id="8e8b9-126">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="8e8b9-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="8e8b9-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="8e8b9-127">InstanceId</span></span>|<span data-ttu-id="8e8b9-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="8e8b9-128">xs:string</span></span>|<span data-ttu-id="8e8b9-129">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="8e8b9-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="8e8b9-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="8e8b9-130">BookmarkName</span></span>|<span data-ttu-id="8e8b9-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="8e8b9-131">xs:string</span></span>|<span data-ttu-id="8e8b9-132">Der Name des Lesezeichens.</span><span class="sxs-lookup"><span data-stu-id="8e8b9-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="8e8b9-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="8e8b9-133">BookmarkScope</span></span>|<span data-ttu-id="8e8b9-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="8e8b9-134">xs:string</span></span>|<span data-ttu-id="8e8b9-135">Der Bereich des Lesezeichens.</span><span class="sxs-lookup"><span data-stu-id="8e8b9-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="8e8b9-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8e8b9-136">AppDomain</span></span>|<span data-ttu-id="8e8b9-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="8e8b9-137">xs:string</span></span>|<span data-ttu-id="8e8b9-138">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="8e8b9-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
