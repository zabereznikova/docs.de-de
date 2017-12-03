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
ms.openlocfilehash: 7c2031a86a8d46a51b65e60a63a352c56b1a3a53
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="1029---schedulefaultworkitem"></a><span data-ttu-id="e9029-102">1029 - ScheduleFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="e9029-102">1029 - ScheduleFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="e9029-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="e9029-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e9029-104">ID</span><span class="sxs-lookup"><span data-stu-id="e9029-104">ID</span></span>|<span data-ttu-id="e9029-105">1029</span><span class="sxs-lookup"><span data-stu-id="e9029-105">1029</span></span>|  
|<span data-ttu-id="e9029-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="e9029-106">Keywords</span></span>|<span data-ttu-id="e9029-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="e9029-107">WFRuntime</span></span>|  
|<span data-ttu-id="e9029-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="e9029-108">Level</span></span>|<span data-ttu-id="e9029-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="e9029-109">Verbose</span></span>|  
|<span data-ttu-id="e9029-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="e9029-110">Channel</span></span>|<span data-ttu-id="e9029-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="e9029-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e9029-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e9029-112">Description</span></span>  
 <span data-ttu-id="e9029-113">Gibt an, dass ein FaultWorkItem geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="e9029-113">Indicates a FaultWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e9029-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="e9029-114">Message</span></span>  
 <span data-ttu-id="e9029-115">Wurde ein FaultWorkItem geplant für die Aktivität '%1', DisplayName: '%2', InstanceId: "%3".</span><span class="sxs-lookup"><span data-stu-id="e9029-115">A FaultWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="e9029-116">Die Ausnahme wurde von der Aktivität '%4', DisplayName: '%5', InstanceId: '%6' propagiert.</span><span class="sxs-lookup"><span data-stu-id="e9029-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e9029-117">Details</span><span class="sxs-lookup"><span data-stu-id="e9029-117">Details</span></span>  
  
|<span data-ttu-id="e9029-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="e9029-118">Data Item Name</span></span>|<span data-ttu-id="e9029-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="e9029-119">Data Item Type</span></span>|<span data-ttu-id="e9029-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e9029-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e9029-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="e9029-121">FaultActivity</span></span>|<span data-ttu-id="e9029-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="e9029-122">xs:string</span></span>|<span data-ttu-id="e9029-123">Der Typname der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="e9029-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="e9029-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="e9029-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="e9029-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="e9029-125">xs:string</span></span>|<span data-ttu-id="e9029-126">Der Anzeigename der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="e9029-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="e9029-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="e9029-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="e9029-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="e9029-128">xs:string</span></span>|<span data-ttu-id="e9029-129">Die Instanz-ID der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="e9029-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="e9029-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="e9029-130">ExceptionActivity</span></span>|<span data-ttu-id="e9029-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="e9029-131">xs:string</span></span>|<span data-ttu-id="e9029-132">Der Typname der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="e9029-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="e9029-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="e9029-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="e9029-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="e9029-134">xs:string</span></span>|<span data-ttu-id="e9029-135">Der Anzeigename der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="e9029-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="e9029-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="e9029-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="e9029-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="e9029-137">xs:string</span></span>|<span data-ttu-id="e9029-138">Die Instanz-ID der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="e9029-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="e9029-139">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="e9029-139">Exception</span></span>|<span data-ttu-id="e9029-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="e9029-140">xs:string</span></span>|<span data-ttu-id="e9029-141">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="e9029-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="e9029-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e9029-142">AppDomain</span></span>|<span data-ttu-id="e9029-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="e9029-143">xs:string</span></span>|<span data-ttu-id="e9029-144">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="e9029-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
