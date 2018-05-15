---
title: 1029 - ScheduleFaultWorkItem
ms.date: 03/30/2017
ms.assetid: 3a56b29e-f740-459d-8576-d81e58bf5a03
ms.openlocfilehash: f5beab91f7dd39a3f8ed3b76d6c0a1ddd9bd77c3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="1029---schedulefaultworkitem"></a><span data-ttu-id="ec977-102">1029 - ScheduleFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="ec977-102">1029 - ScheduleFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="ec977-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="ec977-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ec977-104">ID</span><span class="sxs-lookup"><span data-stu-id="ec977-104">ID</span></span>|<span data-ttu-id="ec977-105">1029</span><span class="sxs-lookup"><span data-stu-id="ec977-105">1029</span></span>|  
|<span data-ttu-id="ec977-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="ec977-106">Keywords</span></span>|<span data-ttu-id="ec977-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ec977-107">WFRuntime</span></span>|  
|<span data-ttu-id="ec977-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="ec977-108">Level</span></span>|<span data-ttu-id="ec977-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="ec977-109">Verbose</span></span>|  
|<span data-ttu-id="ec977-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="ec977-110">Channel</span></span>|<span data-ttu-id="ec977-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="ec977-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ec977-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ec977-112">Description</span></span>  
 <span data-ttu-id="ec977-113">Gibt an, dass ein FaultWorkItem geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="ec977-113">Indicates a FaultWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ec977-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="ec977-114">Message</span></span>  
 <span data-ttu-id="ec977-115">Wurde ein FaultWorkItem geplant für die Aktivität '%1', DisplayName: '%2', InstanceId: "%3".</span><span class="sxs-lookup"><span data-stu-id="ec977-115">A FaultWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="ec977-116">Die Ausnahme wurde von der Aktivität '%4', DisplayName: '%5', InstanceId: '%6' propagiert.</span><span class="sxs-lookup"><span data-stu-id="ec977-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ec977-117">Details</span><span class="sxs-lookup"><span data-stu-id="ec977-117">Details</span></span>  
  
|<span data-ttu-id="ec977-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="ec977-118">Data Item Name</span></span>|<span data-ttu-id="ec977-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="ec977-119">Data Item Type</span></span>|<span data-ttu-id="ec977-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ec977-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ec977-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="ec977-121">FaultActivity</span></span>|<span data-ttu-id="ec977-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="ec977-122">xs:string</span></span>|<span data-ttu-id="ec977-123">Der Typname der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="ec977-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="ec977-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="ec977-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="ec977-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="ec977-125">xs:string</span></span>|<span data-ttu-id="ec977-126">Der Anzeigename der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="ec977-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="ec977-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="ec977-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="ec977-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="ec977-128">xs:string</span></span>|<span data-ttu-id="ec977-129">Die Instanz-ID der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="ec977-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="ec977-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="ec977-130">ExceptionActivity</span></span>|<span data-ttu-id="ec977-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="ec977-131">xs:string</span></span>|<span data-ttu-id="ec977-132">Der Typname der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="ec977-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="ec977-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="ec977-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="ec977-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="ec977-134">xs:string</span></span>|<span data-ttu-id="ec977-135">Der Anzeigename der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="ec977-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="ec977-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="ec977-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="ec977-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="ec977-137">xs:string</span></span>|<span data-ttu-id="ec977-138">Die Instanz-ID der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="ec977-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="ec977-139">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="ec977-139">Exception</span></span>|<span data-ttu-id="ec977-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="ec977-140">xs:string</span></span>|<span data-ttu-id="ec977-141">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="ec977-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="ec977-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ec977-142">AppDomain</span></span>|<span data-ttu-id="ec977-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="ec977-143">xs:string</span></span>|<span data-ttu-id="ec977-144">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="ec977-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
