---
title: 1009 - ActivityScheduled
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 307e38b6-d47e-47a4-9708-e74d8314b1a1
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bdaa8ca4efeffb3895e0056303721b13cdc1ae27
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="1009---activityscheduled"></a><span data-ttu-id="5951a-102">1009 - ActivityScheduled</span><span class="sxs-lookup"><span data-stu-id="5951a-102">1009 - ActivityScheduled</span></span>
## <a name="properties"></a><span data-ttu-id="5951a-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="5951a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5951a-104">ID</span><span class="sxs-lookup"><span data-stu-id="5951a-104">ID</span></span>|<span data-ttu-id="5951a-105">1009</span><span class="sxs-lookup"><span data-stu-id="5951a-105">1009</span></span>|  
|<span data-ttu-id="5951a-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="5951a-106">Keywords</span></span>|<span data-ttu-id="5951a-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="5951a-107">WFRuntime</span></span>|  
|<span data-ttu-id="5951a-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="5951a-108">Level</span></span>|<span data-ttu-id="5951a-109">Information</span><span class="sxs-lookup"><span data-stu-id="5951a-109">Information</span></span>|  
|<span data-ttu-id="5951a-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="5951a-110">Channel</span></span>|<span data-ttu-id="5951a-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="5951a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5951a-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5951a-112">Description</span></span>  
 <span data-ttu-id="5951a-113">Gibt an, dass die Ausführung einer Aktivität geplant wird.</span><span class="sxs-lookup"><span data-stu-id="5951a-113">Indicates an activity is being scheduled for execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5951a-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="5951a-114">Message</span></span>  
 <span data-ttu-id="5951a-115">Die übergeordnete Aktivität '%1', DisplayName: '%2', InstanceId: '%3' hat die untergeordnete Aktivität '%4', DisplayName: '%5', InstanceId: '%6' geplant.</span><span class="sxs-lookup"><span data-stu-id="5951a-115">Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5951a-116">Details</span><span class="sxs-lookup"><span data-stu-id="5951a-116">Details</span></span>  
  
|<span data-ttu-id="5951a-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="5951a-117">Data Item Name</span></span>|<span data-ttu-id="5951a-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="5951a-118">Data Item Type</span></span>|<span data-ttu-id="5951a-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5951a-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5951a-120">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="5951a-120">ParentActivity</span></span>|<span data-ttu-id="5951a-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="5951a-121">xs:string</span></span>|<span data-ttu-id="5951a-122">Der Typname der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="5951a-122">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="5951a-123">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="5951a-123">ParentDisplayName</span></span>|<span data-ttu-id="5951a-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="5951a-124">xs:string</span></span>|<span data-ttu-id="5951a-125">Der Anzeigename der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="5951a-125">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="5951a-126">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="5951a-126">ParentInstanceId</span></span>|<span data-ttu-id="5951a-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="5951a-127">xs:string</span></span>|<span data-ttu-id="5951a-128">Die Instanz-ID der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="5951a-128">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="5951a-129">ChildActivity</span><span class="sxs-lookup"><span data-stu-id="5951a-129">ChildActivity</span></span>|<span data-ttu-id="5951a-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="5951a-130">xs:string</span></span>|<span data-ttu-id="5951a-131">Der Typname der untergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="5951a-131">The type name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="5951a-132">ChildDisplayName</span><span class="sxs-lookup"><span data-stu-id="5951a-132">ChildDisplayName</span></span>|<span data-ttu-id="5951a-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="5951a-133">xs:string</span></span>|<span data-ttu-id="5951a-134">Der Anzeigename der untergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="5951a-134">The display name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="5951a-135">ChildInstanceId</span><span class="sxs-lookup"><span data-stu-id="5951a-135">ChildInstanceId</span></span>|<span data-ttu-id="5951a-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="5951a-136">xs:string</span></span>|<span data-ttu-id="5951a-137">Die Instanz-ID der geplanten untergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="5951a-137">The instance id of the scheduled child activity.</span></span>|  
|<span data-ttu-id="5951a-138">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5951a-138">AppDomain</span></span>|<span data-ttu-id="5951a-139">xs:string</span><span class="sxs-lookup"><span data-stu-id="5951a-139">xs:string</span></span>|<span data-ttu-id="5951a-140">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="5951a-140">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
