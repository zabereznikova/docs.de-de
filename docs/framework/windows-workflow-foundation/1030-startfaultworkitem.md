---
title: 1030 - StartFaultWorkItem
ms.date: 03/30/2017
ms.assetid: e1601fb9-0bc6-4dbe-816f-f24914063d34
ms.openlocfilehash: 3848d644e77041a62a52eb2eae5eeef286dfe334
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924318"
---
# <a name="1030---startfaultworkitem"></a><span data-ttu-id="5acd2-102">1030 - StartFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="5acd2-102">1030 - StartFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="5acd2-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="5acd2-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5acd2-104">ID</span><span class="sxs-lookup"><span data-stu-id="5acd2-104">ID</span></span>|<span data-ttu-id="5acd2-105">1030</span><span class="sxs-lookup"><span data-stu-id="5acd2-105">1030</span></span>|  
|<span data-ttu-id="5acd2-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="5acd2-106">Keywords</span></span>|<span data-ttu-id="5acd2-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="5acd2-107">WFRuntime</span></span>|  
|<span data-ttu-id="5acd2-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="5acd2-108">Level</span></span>|<span data-ttu-id="5acd2-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="5acd2-109">Verbose</span></span>|  
|<span data-ttu-id="5acd2-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="5acd2-110">Channel</span></span>|<span data-ttu-id="5acd2-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="5acd2-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5acd2-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5acd2-112">Description</span></span>  
 <span data-ttu-id="5acd2-113">Gibt an, dass ein FaultWorkItem mit der Ausführung beginnt.</span><span class="sxs-lookup"><span data-stu-id="5acd2-113">Indicates a FaultWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5acd2-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="5acd2-114">Message</span></span>  
 <span data-ttu-id="5acd2-115">Starting execution of a FaultWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="5acd2-115">Starting execution of a FaultWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="5acd2-116">Die Ausnahme wurde von der Aktivität '%4', DisplayName: '%5', InstanceId: '%6' propagiert.</span><span class="sxs-lookup"><span data-stu-id="5acd2-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5acd2-117">Details</span><span class="sxs-lookup"><span data-stu-id="5acd2-117">Details</span></span>  
  
|<span data-ttu-id="5acd2-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="5acd2-118">Data Item Name</span></span>|<span data-ttu-id="5acd2-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="5acd2-119">Data Item Type</span></span>|<span data-ttu-id="5acd2-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5acd2-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5acd2-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="5acd2-121">FaultActivity</span></span>|<span data-ttu-id="5acd2-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="5acd2-122">xs:string</span></span>|<span data-ttu-id="5acd2-123">Der Typname der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="5acd2-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="5acd2-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="5acd2-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="5acd2-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="5acd2-125">xs:string</span></span>|<span data-ttu-id="5acd2-126">Der Anzeigename der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="5acd2-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="5acd2-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="5acd2-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="5acd2-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="5acd2-128">xs:string</span></span>|<span data-ttu-id="5acd2-129">Die Instanz-ID der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="5acd2-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="5acd2-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="5acd2-130">ExceptionActivity</span></span>|<span data-ttu-id="5acd2-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="5acd2-131">xs:string</span></span>|<span data-ttu-id="5acd2-132">Der Typname der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="5acd2-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="5acd2-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="5acd2-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="5acd2-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="5acd2-134">xs:string</span></span>|<span data-ttu-id="5acd2-135">Der Anzeigename der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="5acd2-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="5acd2-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="5acd2-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="5acd2-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="5acd2-137">xs:string</span></span>|<span data-ttu-id="5acd2-138">Die Instanz-ID der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="5acd2-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="5acd2-139">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="5acd2-139">Exception</span></span>|<span data-ttu-id="5acd2-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="5acd2-140">xs:string</span></span>|<span data-ttu-id="5acd2-141">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="5acd2-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="5acd2-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5acd2-142">AppDomain</span></span>|<span data-ttu-id="5acd2-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="5acd2-143">xs:string</span></span>|<span data-ttu-id="5acd2-144">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="5acd2-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
