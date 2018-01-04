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
ms.workload: dotnet
ms.openlocfilehash: 4a0d8cc3d17ecd13d9312b42554ef5347cccf213
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="1009---activityscheduled"></a><span data-ttu-id="07a2c-102">1009 - ActivityScheduled</span><span class="sxs-lookup"><span data-stu-id="07a2c-102">1009 - ActivityScheduled</span></span>
## <a name="properties"></a><span data-ttu-id="07a2c-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="07a2c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="07a2c-104">ID</span><span class="sxs-lookup"><span data-stu-id="07a2c-104">ID</span></span>|<span data-ttu-id="07a2c-105">1009</span><span class="sxs-lookup"><span data-stu-id="07a2c-105">1009</span></span>|  
|<span data-ttu-id="07a2c-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="07a2c-106">Keywords</span></span>|<span data-ttu-id="07a2c-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="07a2c-107">WFRuntime</span></span>|  
|<span data-ttu-id="07a2c-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="07a2c-108">Level</span></span>|<span data-ttu-id="07a2c-109">Information</span><span class="sxs-lookup"><span data-stu-id="07a2c-109">Information</span></span>|  
|<span data-ttu-id="07a2c-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="07a2c-110">Channel</span></span>|<span data-ttu-id="07a2c-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="07a2c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="07a2c-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="07a2c-112">Description</span></span>  
 <span data-ttu-id="07a2c-113">Gibt an, dass die Ausführung einer Aktivität geplant wird.</span><span class="sxs-lookup"><span data-stu-id="07a2c-113">Indicates an activity is being scheduled for execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="07a2c-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="07a2c-114">Message</span></span>  
 <span data-ttu-id="07a2c-115">Die übergeordnete Aktivität '%1', DisplayName: '%2', InstanceId: '%3' hat die untergeordnete Aktivität '%4', DisplayName: '%5', InstanceId: '%6' geplant.</span><span class="sxs-lookup"><span data-stu-id="07a2c-115">Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="07a2c-116">Details</span><span class="sxs-lookup"><span data-stu-id="07a2c-116">Details</span></span>  
  
|<span data-ttu-id="07a2c-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="07a2c-117">Data Item Name</span></span>|<span data-ttu-id="07a2c-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="07a2c-118">Data Item Type</span></span>|<span data-ttu-id="07a2c-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="07a2c-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="07a2c-120">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="07a2c-120">ParentActivity</span></span>|<span data-ttu-id="07a2c-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="07a2c-121">xs:string</span></span>|<span data-ttu-id="07a2c-122">Der Typname der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="07a2c-122">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="07a2c-123">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="07a2c-123">ParentDisplayName</span></span>|<span data-ttu-id="07a2c-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="07a2c-124">xs:string</span></span>|<span data-ttu-id="07a2c-125">Der Anzeigename der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="07a2c-125">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="07a2c-126">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="07a2c-126">ParentInstanceId</span></span>|<span data-ttu-id="07a2c-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="07a2c-127">xs:string</span></span>|<span data-ttu-id="07a2c-128">Die Instanz-ID der übergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="07a2c-128">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="07a2c-129">ChildActivity</span><span class="sxs-lookup"><span data-stu-id="07a2c-129">ChildActivity</span></span>|<span data-ttu-id="07a2c-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="07a2c-130">xs:string</span></span>|<span data-ttu-id="07a2c-131">Der Typname der untergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="07a2c-131">The type name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="07a2c-132">ChildDisplayName</span><span class="sxs-lookup"><span data-stu-id="07a2c-132">ChildDisplayName</span></span>|<span data-ttu-id="07a2c-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="07a2c-133">xs:string</span></span>|<span data-ttu-id="07a2c-134">Der Anzeigename der untergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="07a2c-134">The display name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="07a2c-135">ChildInstanceId</span><span class="sxs-lookup"><span data-stu-id="07a2c-135">ChildInstanceId</span></span>|<span data-ttu-id="07a2c-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="07a2c-136">xs:string</span></span>|<span data-ttu-id="07a2c-137">Die Instanz-ID der geplanten untergeordneten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="07a2c-137">The instance id of the scheduled child activity.</span></span>|  
|<span data-ttu-id="07a2c-138">AppDomain</span><span class="sxs-lookup"><span data-stu-id="07a2c-138">AppDomain</span></span>|<span data-ttu-id="07a2c-139">xs:string</span><span class="sxs-lookup"><span data-stu-id="07a2c-139">xs:string</span></span>|<span data-ttu-id="07a2c-140">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="07a2c-140">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
