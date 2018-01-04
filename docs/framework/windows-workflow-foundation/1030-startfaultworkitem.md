---
title: 1030 - StartFaultWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e1601fb9-0bc6-4dbe-816f-f24914063d34
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 436a0323fcf4498a1d707f7af9bd8204885fd645
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="1030---startfaultworkitem"></a><span data-ttu-id="0a025-102">1030 - StartFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="0a025-102">1030 - StartFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="0a025-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="0a025-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0a025-104">ID</span><span class="sxs-lookup"><span data-stu-id="0a025-104">ID</span></span>|<span data-ttu-id="0a025-105">1030</span><span class="sxs-lookup"><span data-stu-id="0a025-105">1030</span></span>|  
|<span data-ttu-id="0a025-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="0a025-106">Keywords</span></span>|<span data-ttu-id="0a025-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="0a025-107">WFRuntime</span></span>|  
|<span data-ttu-id="0a025-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="0a025-108">Level</span></span>|<span data-ttu-id="0a025-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="0a025-109">Verbose</span></span>|  
|<span data-ttu-id="0a025-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="0a025-110">Channel</span></span>|<span data-ttu-id="0a025-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="0a025-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0a025-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0a025-112">Description</span></span>  
 <span data-ttu-id="0a025-113">Gibt an, dass ein FaultWorkItem mit der Ausführung beginnt.</span><span class="sxs-lookup"><span data-stu-id="0a025-113">Indicates a FaultWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0a025-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="0a025-114">Message</span></span>  
 <span data-ttu-id="0a025-115">Starten der Ausführung ein FaultWorkItem für die Aktivität '%1', DisplayName: '%2', InstanceId: "%3".</span><span class="sxs-lookup"><span data-stu-id="0a025-115">Starting execution of a FaultWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="0a025-116">Die Ausnahme wurde von der Aktivität '%4', DisplayName: '%5', InstanceId: '%6' propagiert.</span><span class="sxs-lookup"><span data-stu-id="0a025-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0a025-117">Details</span><span class="sxs-lookup"><span data-stu-id="0a025-117">Details</span></span>  
  
|<span data-ttu-id="0a025-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="0a025-118">Data Item Name</span></span>|<span data-ttu-id="0a025-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="0a025-119">Data Item Type</span></span>|<span data-ttu-id="0a025-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0a025-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0a025-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="0a025-121">FaultActivity</span></span>|<span data-ttu-id="0a025-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="0a025-122">xs:string</span></span>|<span data-ttu-id="0a025-123">Der Typname der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="0a025-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="0a025-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="0a025-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="0a025-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="0a025-125">xs:string</span></span>|<span data-ttu-id="0a025-126">Der Anzeigename der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="0a025-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="0a025-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="0a025-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="0a025-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="0a025-128">xs:string</span></span>|<span data-ttu-id="0a025-129">Die Instanz-ID der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="0a025-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="0a025-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="0a025-130">ExceptionActivity</span></span>|<span data-ttu-id="0a025-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="0a025-131">xs:string</span></span>|<span data-ttu-id="0a025-132">Der Typname der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="0a025-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="0a025-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="0a025-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="0a025-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="0a025-134">xs:string</span></span>|<span data-ttu-id="0a025-135">Der Anzeigename der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="0a025-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="0a025-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="0a025-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="0a025-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="0a025-137">xs:string</span></span>|<span data-ttu-id="0a025-138">Die Instanz-ID der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="0a025-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="0a025-139">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="0a025-139">Exception</span></span>|<span data-ttu-id="0a025-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="0a025-140">xs:string</span></span>|<span data-ttu-id="0a025-141">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="0a025-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="0a025-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0a025-142">AppDomain</span></span>|<span data-ttu-id="0a025-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="0a025-143">xs:string</span></span>|<span data-ttu-id="0a025-144">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="0a025-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
