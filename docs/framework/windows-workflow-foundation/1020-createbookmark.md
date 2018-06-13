---
title: 1020 - CreateBookmark
ms.date: 03/30/2017
ms.assetid: 4bee948d-816f-4803-85cc-3883b5e23d10
ms.openlocfilehash: 2a382a2f12f4800cd70286a553af253e2af64c9b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510458"
---
# <a name="1020---createbookmark"></a><span data-ttu-id="53f11-102">1020 - CreateBookmark</span><span class="sxs-lookup"><span data-stu-id="53f11-102">1020 - CreateBookmark</span></span>
## <a name="properties"></a><span data-ttu-id="53f11-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="53f11-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="53f11-104">ID</span><span class="sxs-lookup"><span data-stu-id="53f11-104">ID</span></span>|<span data-ttu-id="53f11-105">1020</span><span class="sxs-lookup"><span data-stu-id="53f11-105">1020</span></span>|  
|<span data-ttu-id="53f11-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="53f11-106">Keywords</span></span>|<span data-ttu-id="53f11-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="53f11-107">WFRuntime</span></span>|  
|<span data-ttu-id="53f11-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="53f11-108">Level</span></span>|<span data-ttu-id="53f11-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="53f11-109">Verbose</span></span>|  
|<span data-ttu-id="53f11-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="53f11-110">Channel</span></span>|<span data-ttu-id="53f11-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="53f11-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="53f11-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="53f11-112">Description</span></span>  
 <span data-ttu-id="53f11-113">Gibt an, dass für eine Aktivität ein Lesezeichen erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="53f11-113">Indicates a bookmark has been created for an activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="53f11-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="53f11-114">Message</span></span>  
 <span data-ttu-id="53f11-115">Ein Lesezeichen erstellt wurde, für die Aktivität '%1', DisplayName: '%2', InstanceId: "%3".</span><span class="sxs-lookup"><span data-stu-id="53f11-115">A Bookmark has been created for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="53f11-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="53f11-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="53f11-117">Details</span><span class="sxs-lookup"><span data-stu-id="53f11-117">Details</span></span>  
  
|<span data-ttu-id="53f11-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="53f11-118">Data Item Name</span></span>|<span data-ttu-id="53f11-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="53f11-119">Data Item Type</span></span>|<span data-ttu-id="53f11-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="53f11-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="53f11-121">Aktivität</span><span class="sxs-lookup"><span data-stu-id="53f11-121">Activity</span></span>|<span data-ttu-id="53f11-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="53f11-122">xs:string</span></span>|<span data-ttu-id="53f11-123">Der Typname der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="53f11-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="53f11-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="53f11-124">DisplayName</span></span>|<span data-ttu-id="53f11-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="53f11-125">xs:string</span></span>|<span data-ttu-id="53f11-126">Der Anzeigename der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="53f11-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="53f11-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="53f11-127">InstanceId</span></span>|<span data-ttu-id="53f11-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="53f11-128">xs:string</span></span>|<span data-ttu-id="53f11-129">Die Instanz-ID der Aktivität.</span><span class="sxs-lookup"><span data-stu-id="53f11-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="53f11-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="53f11-130">BookmarkName</span></span>|<span data-ttu-id="53f11-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="53f11-131">xs:string</span></span>|<span data-ttu-id="53f11-132">Der Name des Lesezeichens.</span><span class="sxs-lookup"><span data-stu-id="53f11-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="53f11-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="53f11-133">BookmarkScope</span></span>|<span data-ttu-id="53f11-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="53f11-134">xs:string</span></span>|<span data-ttu-id="53f11-135">Der Bereich des Lesezeichens.</span><span class="sxs-lookup"><span data-stu-id="53f11-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="53f11-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="53f11-136">AppDomain</span></span>|<span data-ttu-id="53f11-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="53f11-137">xs:string</span></span>|<span data-ttu-id="53f11-138">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="53f11-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
