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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1ba1ae69caff2e08da58e824d35341d3781ea8ef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="1029---schedulefaultworkitem"></a><span data-ttu-id="da360-102">1029 - ScheduleFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="da360-102">1029 - ScheduleFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="da360-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="da360-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="da360-104">ID</span><span class="sxs-lookup"><span data-stu-id="da360-104">ID</span></span>|<span data-ttu-id="da360-105">1029</span><span class="sxs-lookup"><span data-stu-id="da360-105">1029</span></span>|  
|<span data-ttu-id="da360-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="da360-106">Keywords</span></span>|<span data-ttu-id="da360-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="da360-107">WFRuntime</span></span>|  
|<span data-ttu-id="da360-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="da360-108">Level</span></span>|<span data-ttu-id="da360-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="da360-109">Verbose</span></span>|  
|<span data-ttu-id="da360-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="da360-110">Channel</span></span>|<span data-ttu-id="da360-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="da360-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="da360-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="da360-112">Description</span></span>  
 <span data-ttu-id="da360-113">Gibt an, dass ein FaultWorkItem geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="da360-113">Indicates a FaultWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="da360-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="da360-114">Message</span></span>  
 <span data-ttu-id="da360-115">Wurde ein FaultWorkItem geplant für die Aktivität '%1', DisplayName: '%2', InstanceId: "%3".</span><span class="sxs-lookup"><span data-stu-id="da360-115">A FaultWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="da360-116">Die Ausnahme wurde von der Aktivität '%4', DisplayName: '%5', InstanceId: '%6' propagiert.</span><span class="sxs-lookup"><span data-stu-id="da360-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="da360-117">Details</span><span class="sxs-lookup"><span data-stu-id="da360-117">Details</span></span>  
  
|<span data-ttu-id="da360-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="da360-118">Data Item Name</span></span>|<span data-ttu-id="da360-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="da360-119">Data Item Type</span></span>|<span data-ttu-id="da360-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="da360-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="da360-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="da360-121">FaultActivity</span></span>|<span data-ttu-id="da360-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="da360-122">xs:string</span></span>|<span data-ttu-id="da360-123">Der Typname der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="da360-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="da360-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="da360-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="da360-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="da360-125">xs:string</span></span>|<span data-ttu-id="da360-126">Der Anzeigename der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="da360-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="da360-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="da360-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="da360-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="da360-128">xs:string</span></span>|<span data-ttu-id="da360-129">Die Instanz-ID der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="da360-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="da360-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="da360-130">ExceptionActivity</span></span>|<span data-ttu-id="da360-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="da360-131">xs:string</span></span>|<span data-ttu-id="da360-132">Der Typname der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="da360-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="da360-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="da360-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="da360-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="da360-134">xs:string</span></span>|<span data-ttu-id="da360-135">Der Anzeigename der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="da360-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="da360-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="da360-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="da360-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="da360-137">xs:string</span></span>|<span data-ttu-id="da360-138">Die Instanz-ID der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="da360-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="da360-139">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="da360-139">Exception</span></span>|<span data-ttu-id="da360-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="da360-140">xs:string</span></span>|<span data-ttu-id="da360-141">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="da360-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="da360-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="da360-142">AppDomain</span></span>|<span data-ttu-id="da360-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="da360-143">xs:string</span></span>|<span data-ttu-id="da360-144">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="da360-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
