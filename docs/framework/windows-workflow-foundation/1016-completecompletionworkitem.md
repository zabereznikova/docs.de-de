---
title: 1016 - CompleteCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 246929fb-6f14-440a-814b-cd8349350644
ms.openlocfilehash: 3f0904a561a242cd3be528c9707a409b6f98e0fe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510295"
---
# <a name="1016---completecompletionworkitem"></a><span data-ttu-id="69801-102">1016 - CompleteCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="69801-102">1016 - CompleteCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="69801-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="69801-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="69801-104">ID</span><span class="sxs-lookup"><span data-stu-id="69801-104">ID</span></span>|<span data-ttu-id="69801-105">1016</span><span class="sxs-lookup"><span data-stu-id="69801-105">1016</span></span>|  
|<span data-ttu-id="69801-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="69801-106">Keywords</span></span>|<span data-ttu-id="69801-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="69801-107">WFRuntime</span></span>|  
|<span data-ttu-id="69801-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="69801-108">Level</span></span>|<span data-ttu-id="69801-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="69801-109">Verbose</span></span>|  
|<span data-ttu-id="69801-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="69801-110">Channel</span></span>|<span data-ttu-id="69801-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="69801-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="69801-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="69801-112">Description</span></span>  
 <span data-ttu-id="69801-113">Gibt an, dass ein CompletionWorkItem abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="69801-113">Indicates a CompletionWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="69801-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="69801-114">Message</span></span>  
 <span data-ttu-id="69801-115">Für die übergeordnete Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde eine CompletionWorkItem abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="69801-115">A CompletionWorkItem has completed for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="69801-116">Abgeschlossene Aktivität '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="69801-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="69801-117">Details</span><span class="sxs-lookup"><span data-stu-id="69801-117">Details</span></span>  
  
|<span data-ttu-id="69801-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="69801-118">Data Item Name</span></span>|<span data-ttu-id="69801-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="69801-119">Data Item Type</span></span>|<span data-ttu-id="69801-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="69801-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="69801-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="69801-121">ParentActivity</span></span>|<span data-ttu-id="69801-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="69801-122">xs:string</span></span>|<span data-ttu-id="69801-123">Der Typname der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="69801-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="69801-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="69801-124">ParentDisplayName</span></span>|<span data-ttu-id="69801-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="69801-125">xs:string</span></span>|<span data-ttu-id="69801-126">Der Anzeigename der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="69801-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="69801-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="69801-127">ParentInstanceId</span></span>|<span data-ttu-id="69801-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="69801-128">xs:string</span></span>|<span data-ttu-id="69801-129">Die Instanz-ID der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="69801-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="69801-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="69801-130">CompletedActivity</span></span>|<span data-ttu-id="69801-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="69801-131">xs:string</span></span>|<span data-ttu-id="69801-132">Der Typname der abgeschlossenen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="69801-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="69801-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="69801-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="69801-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="69801-134">xs:string</span></span>|<span data-ttu-id="69801-135">Der Anzeigename der abgeschlossenen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="69801-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="69801-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="69801-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="69801-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="69801-137">xs:string</span></span>|<span data-ttu-id="69801-138">Die Instanz-ID der abgeschlossenen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="69801-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="69801-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="69801-139">AppDomain</span></span>|<span data-ttu-id="69801-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="69801-140">xs:string</span></span>|<span data-ttu-id="69801-141">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="69801-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
