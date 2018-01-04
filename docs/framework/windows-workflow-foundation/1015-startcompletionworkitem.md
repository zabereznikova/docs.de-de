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
ms.workload: dotnet
ms.openlocfilehash: bc317157ed7658a52aa60c9b74942f9e84d47257
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="1015---startcompletionworkitem"></a><span data-ttu-id="0979b-102">1015 - StartCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="0979b-102">1015 - StartCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="0979b-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="0979b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0979b-104">ID</span><span class="sxs-lookup"><span data-stu-id="0979b-104">ID</span></span>|<span data-ttu-id="0979b-105">1015</span><span class="sxs-lookup"><span data-stu-id="0979b-105">1015</span></span>|  
|<span data-ttu-id="0979b-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="0979b-106">Keywords</span></span>|<span data-ttu-id="0979b-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="0979b-107">WFRuntime</span></span>|  
|<span data-ttu-id="0979b-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="0979b-108">Level</span></span>|<span data-ttu-id="0979b-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="0979b-109">Verbose</span></span>|  
|<span data-ttu-id="0979b-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="0979b-110">Channel</span></span>|<span data-ttu-id="0979b-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="0979b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0979b-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0979b-112">Description</span></span>  
 <span data-ttu-id="0979b-113">Gibt an, dass ein CompletionWorkItem mit der Ausführung beginnt.</span><span class="sxs-lookup"><span data-stu-id="0979b-113">Indicates a CompletionWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0979b-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="0979b-114">Message</span></span>  
 <span data-ttu-id="0979b-115">Die Ausführung einer CompletionWorkItem für die übergeordnete Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="0979b-115">Starting execution of a CompletionWorkItem for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="0979b-116">Abgeschlossene Aktivität '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="0979b-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0979b-117">Details</span><span class="sxs-lookup"><span data-stu-id="0979b-117">Details</span></span>  
  
|<span data-ttu-id="0979b-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="0979b-118">Data Item Name</span></span>|<span data-ttu-id="0979b-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="0979b-119">Data Item Type</span></span>|<span data-ttu-id="0979b-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0979b-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0979b-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="0979b-121">ParentActivity</span></span>|<span data-ttu-id="0979b-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="0979b-122">xs:string</span></span>|<span data-ttu-id="0979b-123">Der Typname der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="0979b-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="0979b-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="0979b-124">ParentDisplayName</span></span>|<span data-ttu-id="0979b-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="0979b-125">xs:string</span></span>|<span data-ttu-id="0979b-126">Der Anzeigename der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="0979b-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="0979b-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="0979b-127">ParentInstanceId</span></span>|<span data-ttu-id="0979b-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="0979b-128">xs:string</span></span>|<span data-ttu-id="0979b-129">Die Instanz-ID der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="0979b-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="0979b-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="0979b-130">CompletedActivity</span></span>|<span data-ttu-id="0979b-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="0979b-131">xs:string</span></span>|<span data-ttu-id="0979b-132">Der Typname der abgeschlossenen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="0979b-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="0979b-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="0979b-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="0979b-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="0979b-134">xs:string</span></span>|<span data-ttu-id="0979b-135">Der Anzeigename der abgeschlossenen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="0979b-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="0979b-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="0979b-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="0979b-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="0979b-137">xs:string</span></span>|<span data-ttu-id="0979b-138">Die Instanz-ID der abgeschlossenen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="0979b-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="0979b-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0979b-139">AppDomain</span></span>|<span data-ttu-id="0979b-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="0979b-140">xs:string</span></span>|<span data-ttu-id="0979b-141">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="0979b-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
