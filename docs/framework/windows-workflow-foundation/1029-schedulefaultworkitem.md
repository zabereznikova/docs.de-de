---
title: 1029 - ScheduleFaultWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3a56b29e-f740-459d-8576-d81e58bf5a03
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dfa9553c25f607ec25fd968c2e8c6db061fb49dc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="1029---schedulefaultworkitem"></a><span data-ttu-id="6c4c0-102">1029 - ScheduleFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="6c4c0-102">1029 - ScheduleFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="6c4c0-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="6c4c0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6c4c0-104">ID</span><span class="sxs-lookup"><span data-stu-id="6c4c0-104">ID</span></span>|<span data-ttu-id="6c4c0-105">1029</span><span class="sxs-lookup"><span data-stu-id="6c4c0-105">1029</span></span>|  
|<span data-ttu-id="6c4c0-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="6c4c0-106">Keywords</span></span>|<span data-ttu-id="6c4c0-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="6c4c0-107">WFRuntime</span></span>|  
|<span data-ttu-id="6c4c0-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="6c4c0-108">Level</span></span>|<span data-ttu-id="6c4c0-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="6c4c0-109">Verbose</span></span>|  
|<span data-ttu-id="6c4c0-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="6c4c0-110">Channel</span></span>|<span data-ttu-id="6c4c0-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="6c4c0-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6c4c0-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6c4c0-112">Description</span></span>  
 <span data-ttu-id="6c4c0-113">Gibt an, dass ein FaultWorkItem geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="6c4c0-113">Indicates a FaultWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6c4c0-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="6c4c0-114">Message</span></span>  
 <span data-ttu-id="6c4c0-115">Wurde ein FaultWorkItem geplant für die Aktivität '%1', DisplayName: '%2', InstanceId: "%3".</span><span class="sxs-lookup"><span data-stu-id="6c4c0-115">A FaultWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="6c4c0-116">Die Ausnahme wurde von der Aktivität '%4', DisplayName: '%5', InstanceId: '%6' propagiert.</span><span class="sxs-lookup"><span data-stu-id="6c4c0-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6c4c0-117">Details</span><span class="sxs-lookup"><span data-stu-id="6c4c0-117">Details</span></span>  
  
|<span data-ttu-id="6c4c0-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="6c4c0-118">Data Item Name</span></span>|<span data-ttu-id="6c4c0-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="6c4c0-119">Data Item Type</span></span>|<span data-ttu-id="6c4c0-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6c4c0-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6c4c0-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="6c4c0-121">FaultActivity</span></span>|<span data-ttu-id="6c4c0-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="6c4c0-122">xs:string</span></span>|<span data-ttu-id="6c4c0-123">Der Typname der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="6c4c0-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="6c4c0-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="6c4c0-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="6c4c0-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="6c4c0-125">xs:string</span></span>|<span data-ttu-id="6c4c0-126">Der Anzeigename der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="6c4c0-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="6c4c0-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="6c4c0-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="6c4c0-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="6c4c0-128">xs:string</span></span>|<span data-ttu-id="6c4c0-129">Die Instanz-ID der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="6c4c0-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="6c4c0-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="6c4c0-130">ExceptionActivity</span></span>|<span data-ttu-id="6c4c0-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="6c4c0-131">xs:string</span></span>|<span data-ttu-id="6c4c0-132">Der Typname der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="6c4c0-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="6c4c0-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="6c4c0-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="6c4c0-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="6c4c0-134">xs:string</span></span>|<span data-ttu-id="6c4c0-135">Der Anzeigename der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="6c4c0-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="6c4c0-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="6c4c0-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="6c4c0-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="6c4c0-137">xs:string</span></span>|<span data-ttu-id="6c4c0-138">Die Instanz-ID der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="6c4c0-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="6c4c0-139">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="6c4c0-139">Exception</span></span>|<span data-ttu-id="6c4c0-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="6c4c0-140">xs:string</span></span>|<span data-ttu-id="6c4c0-141">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="6c4c0-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="6c4c0-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6c4c0-142">AppDomain</span></span>|<span data-ttu-id="6c4c0-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="6c4c0-143">xs:string</span></span>|<span data-ttu-id="6c4c0-144">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="6c4c0-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
