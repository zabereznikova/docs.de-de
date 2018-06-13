---
title: 1030 - StartFaultWorkItem
ms.date: 03/30/2017
ms.assetid: e1601fb9-0bc6-4dbe-816f-f24914063d34
ms.openlocfilehash: 3848d644e77041a62a52eb2eae5eeef286dfe334
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509679"
---
# <a name="1030---startfaultworkitem"></a><span data-ttu-id="d27b3-102">1030 - StartFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="d27b3-102">1030 - StartFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="d27b3-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d27b3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d27b3-104">ID</span><span class="sxs-lookup"><span data-stu-id="d27b3-104">ID</span></span>|<span data-ttu-id="d27b3-105">1030</span><span class="sxs-lookup"><span data-stu-id="d27b3-105">1030</span></span>|  
|<span data-ttu-id="d27b3-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d27b3-106">Keywords</span></span>|<span data-ttu-id="d27b3-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="d27b3-107">WFRuntime</span></span>|  
|<span data-ttu-id="d27b3-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="d27b3-108">Level</span></span>|<span data-ttu-id="d27b3-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="d27b3-109">Verbose</span></span>|  
|<span data-ttu-id="d27b3-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="d27b3-110">Channel</span></span>|<span data-ttu-id="d27b3-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="d27b3-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d27b3-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d27b3-112">Description</span></span>  
 <span data-ttu-id="d27b3-113">Gibt an, dass ein FaultWorkItem mit der Ausführung beginnt.</span><span class="sxs-lookup"><span data-stu-id="d27b3-113">Indicates a FaultWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d27b3-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="d27b3-114">Message</span></span>  
 <span data-ttu-id="d27b3-115">Starten der Ausführung ein FaultWorkItem für die Aktivität '%1', DisplayName: '%2', InstanceId: "%3".</span><span class="sxs-lookup"><span data-stu-id="d27b3-115">Starting execution of a FaultWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="d27b3-116">Die Ausnahme wurde von der Aktivität '%4', DisplayName: '%5', InstanceId: '%6' propagiert.</span><span class="sxs-lookup"><span data-stu-id="d27b3-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d27b3-117">Details</span><span class="sxs-lookup"><span data-stu-id="d27b3-117">Details</span></span>  
  
|<span data-ttu-id="d27b3-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="d27b3-118">Data Item Name</span></span>|<span data-ttu-id="d27b3-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="d27b3-119">Data Item Type</span></span>|<span data-ttu-id="d27b3-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d27b3-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d27b3-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="d27b3-121">FaultActivity</span></span>|<span data-ttu-id="d27b3-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="d27b3-122">xs:string</span></span>|<span data-ttu-id="d27b3-123">Der Typname der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="d27b3-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="d27b3-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="d27b3-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="d27b3-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="d27b3-125">xs:string</span></span>|<span data-ttu-id="d27b3-126">Der Anzeigename der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="d27b3-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="d27b3-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="d27b3-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="d27b3-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="d27b3-128">xs:string</span></span>|<span data-ttu-id="d27b3-129">Die Instanz-ID der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="d27b3-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="d27b3-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="d27b3-130">ExceptionActivity</span></span>|<span data-ttu-id="d27b3-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="d27b3-131">xs:string</span></span>|<span data-ttu-id="d27b3-132">Der Typname der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="d27b3-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="d27b3-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="d27b3-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="d27b3-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="d27b3-134">xs:string</span></span>|<span data-ttu-id="d27b3-135">Der Anzeigename der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="d27b3-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="d27b3-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="d27b3-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="d27b3-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="d27b3-137">xs:string</span></span>|<span data-ttu-id="d27b3-138">Die Instanz-ID der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="d27b3-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="d27b3-139">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="d27b3-139">Exception</span></span>|<span data-ttu-id="d27b3-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="d27b3-140">xs:string</span></span>|<span data-ttu-id="d27b3-141">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="d27b3-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="d27b3-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d27b3-142">AppDomain</span></span>|<span data-ttu-id="d27b3-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="d27b3-143">xs:string</span></span>|<span data-ttu-id="d27b3-144">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="d27b3-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
