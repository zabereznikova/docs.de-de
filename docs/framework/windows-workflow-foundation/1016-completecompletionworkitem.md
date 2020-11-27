---
title: 1016 - CompleteCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 246929fb-6f14-440a-814b-cd8349350644
ms.openlocfilehash: a192ffe19777ca3e2e9784f6506a0c2929ced000
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275530"
---
# <a name="1016---completecompletionworkitem"></a><span data-ttu-id="60e59-102">1016 - CompleteCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="60e59-102">1016 - CompleteCompletionWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="60e59-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="60e59-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="60e59-104">id</span><span class="sxs-lookup"><span data-stu-id="60e59-104">ID</span></span>|<span data-ttu-id="60e59-105">1016</span><span class="sxs-lookup"><span data-stu-id="60e59-105">1016</span></span>|  
|<span data-ttu-id="60e59-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="60e59-106">Keywords</span></span>|<span data-ttu-id="60e59-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="60e59-107">WFRuntime</span></span>|  
|<span data-ttu-id="60e59-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="60e59-108">Level</span></span>|<span data-ttu-id="60e59-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="60e59-109">Verbose</span></span>|  
|<span data-ttu-id="60e59-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="60e59-110">Channel</span></span>|<span data-ttu-id="60e59-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="60e59-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="60e59-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="60e59-112">Description</span></span>  

 <span data-ttu-id="60e59-113">Gibt an, dass ein CompletionWorkItem abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="60e59-113">Indicates a CompletionWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="60e59-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="60e59-114">Message</span></span>  

 <span data-ttu-id="60e59-115">Für die übergeordnete Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde eine CompletionWorkItem abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="60e59-115">A CompletionWorkItem has completed for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="60e59-116">Abgeschlossene Aktivität '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="60e59-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="60e59-117">Details</span><span class="sxs-lookup"><span data-stu-id="60e59-117">Details</span></span>  
  
|<span data-ttu-id="60e59-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="60e59-118">Data Item Name</span></span>|<span data-ttu-id="60e59-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="60e59-119">Data Item Type</span></span>|<span data-ttu-id="60e59-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="60e59-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="60e59-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="60e59-121">ParentActivity</span></span>|<span data-ttu-id="60e59-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="60e59-122">xs:string</span></span>|<span data-ttu-id="60e59-123">Der Typname der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="60e59-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="60e59-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="60e59-124">ParentDisplayName</span></span>|<span data-ttu-id="60e59-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="60e59-125">xs:string</span></span>|<span data-ttu-id="60e59-126">Der Anzeigename der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="60e59-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="60e59-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="60e59-127">ParentInstanceId</span></span>|<span data-ttu-id="60e59-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="60e59-128">xs:string</span></span>|<span data-ttu-id="60e59-129">Die Instanz-ID der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="60e59-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="60e59-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="60e59-130">CompletedActivity</span></span>|<span data-ttu-id="60e59-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="60e59-131">xs:string</span></span>|<span data-ttu-id="60e59-132">Der Typname der abgeschlossenen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="60e59-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="60e59-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="60e59-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="60e59-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="60e59-134">xs:string</span></span>|<span data-ttu-id="60e59-135">Der Anzeigename der abgeschlossenen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="60e59-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="60e59-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="60e59-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="60e59-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="60e59-137">xs:string</span></span>|<span data-ttu-id="60e59-138">Die Instanz-ID der abgeschlossenen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="60e59-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="60e59-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="60e59-139">AppDomain</span></span>|<span data-ttu-id="60e59-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="60e59-140">xs:string</span></span>|<span data-ttu-id="60e59-141">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="60e59-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
