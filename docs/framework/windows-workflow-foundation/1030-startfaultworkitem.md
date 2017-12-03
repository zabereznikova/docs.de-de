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
ms.openlocfilehash: c639de96bd72670b2641707e7283be2642801dbe
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="1030---startfaultworkitem"></a><span data-ttu-id="46af5-102">1030 - StartFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="46af5-102">1030 - StartFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="46af5-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="46af5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="46af5-104">ID</span><span class="sxs-lookup"><span data-stu-id="46af5-104">ID</span></span>|<span data-ttu-id="46af5-105">1030</span><span class="sxs-lookup"><span data-stu-id="46af5-105">1030</span></span>|  
|<span data-ttu-id="46af5-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="46af5-106">Keywords</span></span>|<span data-ttu-id="46af5-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="46af5-107">WFRuntime</span></span>|  
|<span data-ttu-id="46af5-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="46af5-108">Level</span></span>|<span data-ttu-id="46af5-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="46af5-109">Verbose</span></span>|  
|<span data-ttu-id="46af5-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="46af5-110">Channel</span></span>|<span data-ttu-id="46af5-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="46af5-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="46af5-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="46af5-112">Description</span></span>  
 <span data-ttu-id="46af5-113">Gibt an, dass ein FaultWorkItem mit der Ausführung beginnt.</span><span class="sxs-lookup"><span data-stu-id="46af5-113">Indicates a FaultWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="46af5-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="46af5-114">Message</span></span>  
 <span data-ttu-id="46af5-115">Starten der Ausführung ein FaultWorkItem für die Aktivität '%1', DisplayName: '%2', InstanceId: "%3".</span><span class="sxs-lookup"><span data-stu-id="46af5-115">Starting execution of a FaultWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="46af5-116">Die Ausnahme wurde von der Aktivität '%4', DisplayName: '%5', InstanceId: '%6' propagiert.</span><span class="sxs-lookup"><span data-stu-id="46af5-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="46af5-117">Details</span><span class="sxs-lookup"><span data-stu-id="46af5-117">Details</span></span>  
  
|<span data-ttu-id="46af5-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="46af5-118">Data Item Name</span></span>|<span data-ttu-id="46af5-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="46af5-119">Data Item Type</span></span>|<span data-ttu-id="46af5-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="46af5-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="46af5-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="46af5-121">FaultActivity</span></span>|<span data-ttu-id="46af5-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="46af5-122">xs:string</span></span>|<span data-ttu-id="46af5-123">Der Typname der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="46af5-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="46af5-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="46af5-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="46af5-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="46af5-125">xs:string</span></span>|<span data-ttu-id="46af5-126">Der Anzeigename der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="46af5-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="46af5-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="46af5-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="46af5-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="46af5-128">xs:string</span></span>|<span data-ttu-id="46af5-129">Die Instanz-ID der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="46af5-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="46af5-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="46af5-130">ExceptionActivity</span></span>|<span data-ttu-id="46af5-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="46af5-131">xs:string</span></span>|<span data-ttu-id="46af5-132">Der Typname der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="46af5-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="46af5-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="46af5-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="46af5-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="46af5-134">xs:string</span></span>|<span data-ttu-id="46af5-135">Der Anzeigename der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="46af5-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="46af5-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="46af5-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="46af5-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="46af5-137">xs:string</span></span>|<span data-ttu-id="46af5-138">Die Instanz-ID der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="46af5-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="46af5-139">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="46af5-139">Exception</span></span>|<span data-ttu-id="46af5-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="46af5-140">xs:string</span></span>|<span data-ttu-id="46af5-141">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="46af5-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="46af5-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="46af5-142">AppDomain</span></span>|<span data-ttu-id="46af5-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="46af5-143">xs:string</span></span>|<span data-ttu-id="46af5-144">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="46af5-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
