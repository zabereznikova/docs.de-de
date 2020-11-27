---
title: 1015 - StartCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 96fd1d4e-c5d0-46ad-8a71-4b4b49ac7262
ms.openlocfilehash: c0d8572f192a8faa22327fd671cd9ea49c5054ca
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275543"
---
# <a name="1015---startcompletionworkitem"></a><span data-ttu-id="785e9-102">1015 - StartCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="785e9-102">1015 - StartCompletionWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="785e9-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="785e9-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="785e9-104">id</span><span class="sxs-lookup"><span data-stu-id="785e9-104">ID</span></span>|<span data-ttu-id="785e9-105">1015</span><span class="sxs-lookup"><span data-stu-id="785e9-105">1015</span></span>|  
|<span data-ttu-id="785e9-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="785e9-106">Keywords</span></span>|<span data-ttu-id="785e9-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="785e9-107">WFRuntime</span></span>|  
|<span data-ttu-id="785e9-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="785e9-108">Level</span></span>|<span data-ttu-id="785e9-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="785e9-109">Verbose</span></span>|  
|<span data-ttu-id="785e9-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="785e9-110">Channel</span></span>|<span data-ttu-id="785e9-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="785e9-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="785e9-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="785e9-112">Description</span></span>  

 <span data-ttu-id="785e9-113">Gibt an, dass ein CompletionWorkItem mit der Ausführung beginnt.</span><span class="sxs-lookup"><span data-stu-id="785e9-113">Indicates a CompletionWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="785e9-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="785e9-114">Message</span></span>  

 <span data-ttu-id="785e9-115">Die Ausführung einer CompletionWorkItem für die übergeordnete Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="785e9-115">Starting execution of a CompletionWorkItem for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="785e9-116">Abgeschlossene Aktivität '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="785e9-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="785e9-117">Details</span><span class="sxs-lookup"><span data-stu-id="785e9-117">Details</span></span>  
  
|<span data-ttu-id="785e9-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="785e9-118">Data Item Name</span></span>|<span data-ttu-id="785e9-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="785e9-119">Data Item Type</span></span>|<span data-ttu-id="785e9-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="785e9-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="785e9-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="785e9-121">ParentActivity</span></span>|<span data-ttu-id="785e9-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="785e9-122">xs:string</span></span>|<span data-ttu-id="785e9-123">Der Typname der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="785e9-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="785e9-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="785e9-124">ParentDisplayName</span></span>|<span data-ttu-id="785e9-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="785e9-125">xs:string</span></span>|<span data-ttu-id="785e9-126">Der Anzeigename der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="785e9-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="785e9-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="785e9-127">ParentInstanceId</span></span>|<span data-ttu-id="785e9-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="785e9-128">xs:string</span></span>|<span data-ttu-id="785e9-129">Die Instanz-ID der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="785e9-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="785e9-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="785e9-130">CompletedActivity</span></span>|<span data-ttu-id="785e9-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="785e9-131">xs:string</span></span>|<span data-ttu-id="785e9-132">Der Typname der abgeschlossenen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="785e9-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="785e9-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="785e9-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="785e9-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="785e9-134">xs:string</span></span>|<span data-ttu-id="785e9-135">Der Anzeigename der abgeschlossenen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="785e9-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="785e9-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="785e9-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="785e9-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="785e9-137">xs:string</span></span>|<span data-ttu-id="785e9-138">Die Instanz-ID der abgeschlossenen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="785e9-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="785e9-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="785e9-139">AppDomain</span></span>|<span data-ttu-id="785e9-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="785e9-140">xs:string</span></span>|<span data-ttu-id="785e9-141">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="785e9-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
