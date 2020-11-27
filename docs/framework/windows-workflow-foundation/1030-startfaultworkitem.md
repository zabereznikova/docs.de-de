---
title: 1030 - StartFaultWorkItem
ms.date: 03/30/2017
ms.assetid: e1601fb9-0bc6-4dbe-816f-f24914063d34
ms.openlocfilehash: 52034f7cc7c6f6749fbbbf06db9267ecb6279ee1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96281858"
---
# <a name="1030---startfaultworkitem"></a><span data-ttu-id="f8522-102">1030 - StartFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="f8522-102">1030 - StartFaultWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="f8522-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f8522-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f8522-104">id</span><span class="sxs-lookup"><span data-stu-id="f8522-104">ID</span></span>|<span data-ttu-id="f8522-105">1030</span><span class="sxs-lookup"><span data-stu-id="f8522-105">1030</span></span>|  
|<span data-ttu-id="f8522-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="f8522-106">Keywords</span></span>|<span data-ttu-id="f8522-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="f8522-107">WFRuntime</span></span>|  
|<span data-ttu-id="f8522-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="f8522-108">Level</span></span>|<span data-ttu-id="f8522-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="f8522-109">Verbose</span></span>|  
|<span data-ttu-id="f8522-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="f8522-110">Channel</span></span>|<span data-ttu-id="f8522-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="f8522-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f8522-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f8522-112">Description</span></span>  

 <span data-ttu-id="f8522-113">Gibt an, dass ein FaultWorkItem mit der Ausführung beginnt.</span><span class="sxs-lookup"><span data-stu-id="f8522-113">Indicates a FaultWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f8522-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="f8522-114">Message</span></span>  

 <span data-ttu-id="f8522-115">Die Ausführung eines "fehlerworkitem" für die Aktivität "%1", Display Name: "%2", InstanceId: "%3" wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="f8522-115">Starting execution of a FaultWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="f8522-116">Die Ausnahme wurde von der Aktivität '%4', DisplayName: '%5', InstanceId: '%6' propagiert.</span><span class="sxs-lookup"><span data-stu-id="f8522-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f8522-117">Details</span><span class="sxs-lookup"><span data-stu-id="f8522-117">Details</span></span>  
  
|<span data-ttu-id="f8522-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="f8522-118">Data Item Name</span></span>|<span data-ttu-id="f8522-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="f8522-119">Data Item Type</span></span>|<span data-ttu-id="f8522-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f8522-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f8522-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="f8522-121">FaultActivity</span></span>|<span data-ttu-id="f8522-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="f8522-122">xs:string</span></span>|<span data-ttu-id="f8522-123">Der Typname der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="f8522-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="f8522-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="f8522-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="f8522-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="f8522-125">xs:string</span></span>|<span data-ttu-id="f8522-126">Der Anzeigename der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="f8522-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="f8522-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="f8522-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="f8522-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="f8522-128">xs:string</span></span>|<span data-ttu-id="f8522-129">Die Instanz-ID der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="f8522-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="f8522-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="f8522-130">ExceptionActivity</span></span>|<span data-ttu-id="f8522-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="f8522-131">xs:string</span></span>|<span data-ttu-id="f8522-132">Der Typname der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="f8522-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="f8522-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="f8522-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="f8522-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="f8522-134">xs:string</span></span>|<span data-ttu-id="f8522-135">Der Anzeigename der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="f8522-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="f8522-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="f8522-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="f8522-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="f8522-137">xs:string</span></span>|<span data-ttu-id="f8522-138">Die Instanz-ID der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="f8522-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="f8522-139">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="f8522-139">Exception</span></span>|<span data-ttu-id="f8522-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="f8522-140">xs:string</span></span>|<span data-ttu-id="f8522-141">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="f8522-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="f8522-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f8522-142">AppDomain</span></span>|<span data-ttu-id="f8522-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="f8522-143">xs:string</span></span>|<span data-ttu-id="f8522-144">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="f8522-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
