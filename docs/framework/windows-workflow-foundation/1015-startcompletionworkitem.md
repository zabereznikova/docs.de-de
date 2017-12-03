---
title: 1015 - StartCompletionWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 96fd1d4e-c5d0-46ad-8a71-4b4b49ac7262
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 44ef71e254a2407b416a0efc4b560bf2f6013a74
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="1015---startcompletionworkitem"></a><span data-ttu-id="0a442-102">1015 - StartCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="0a442-102">1015 - StartCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="0a442-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="0a442-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0a442-104">ID</span><span class="sxs-lookup"><span data-stu-id="0a442-104">ID</span></span>|<span data-ttu-id="0a442-105">1015</span><span class="sxs-lookup"><span data-stu-id="0a442-105">1015</span></span>|  
|<span data-ttu-id="0a442-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="0a442-106">Keywords</span></span>|<span data-ttu-id="0a442-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="0a442-107">WFRuntime</span></span>|  
|<span data-ttu-id="0a442-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="0a442-108">Level</span></span>|<span data-ttu-id="0a442-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="0a442-109">Verbose</span></span>|  
|<span data-ttu-id="0a442-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="0a442-110">Channel</span></span>|<span data-ttu-id="0a442-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="0a442-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0a442-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0a442-112">Description</span></span>  
 <span data-ttu-id="0a442-113">Gibt an, dass ein CompletionWorkItem mit der Ausführung beginnt.</span><span class="sxs-lookup"><span data-stu-id="0a442-113">Indicates a CompletionWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0a442-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="0a442-114">Message</span></span>  
 <span data-ttu-id="0a442-115">Die Ausführung einer CompletionWorkItem für die übergeordnete Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="0a442-115">Starting execution of a CompletionWorkItem for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="0a442-116">Abgeschlossene Aktivität '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="0a442-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0a442-117">Details</span><span class="sxs-lookup"><span data-stu-id="0a442-117">Details</span></span>  
  
|<span data-ttu-id="0a442-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="0a442-118">Data Item Name</span></span>|<span data-ttu-id="0a442-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="0a442-119">Data Item Type</span></span>|<span data-ttu-id="0a442-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0a442-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0a442-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="0a442-121">ParentActivity</span></span>|<span data-ttu-id="0a442-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="0a442-122">xs:string</span></span>|<span data-ttu-id="0a442-123">Der Typname der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="0a442-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="0a442-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="0a442-124">ParentDisplayName</span></span>|<span data-ttu-id="0a442-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="0a442-125">xs:string</span></span>|<span data-ttu-id="0a442-126">Der Anzeigename der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="0a442-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="0a442-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="0a442-127">ParentInstanceId</span></span>|<span data-ttu-id="0a442-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="0a442-128">xs:string</span></span>|<span data-ttu-id="0a442-129">Die Instanz-ID der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="0a442-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="0a442-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="0a442-130">CompletedActivity</span></span>|<span data-ttu-id="0a442-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="0a442-131">xs:string</span></span>|<span data-ttu-id="0a442-132">Der Typname der abgeschlossenen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="0a442-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="0a442-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="0a442-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="0a442-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="0a442-134">xs:string</span></span>|<span data-ttu-id="0a442-135">Der Anzeigename der abgeschlossenen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="0a442-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="0a442-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="0a442-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="0a442-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="0a442-137">xs:string</span></span>|<span data-ttu-id="0a442-138">Die Instanz-ID der abgeschlossenen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="0a442-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="0a442-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0a442-139">AppDomain</span></span>|<span data-ttu-id="0a442-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="0a442-140">xs:string</span></span>|<span data-ttu-id="0a442-141">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="0a442-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
