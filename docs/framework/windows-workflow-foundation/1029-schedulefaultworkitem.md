---
title: 1029 - ScheduleFaultWorkItem
ms.date: 03/30/2017
ms.assetid: 3a56b29e-f740-459d-8576-d81e58bf5a03
ms.openlocfilehash: f5beab91f7dd39a3f8ed3b76d6c0a1ddd9bd77c3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924357"
---
# <a name="1029---schedulefaultworkitem"></a><span data-ttu-id="6173c-102">1029 - ScheduleFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="6173c-102">1029 - ScheduleFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="6173c-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="6173c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6173c-104">ID</span><span class="sxs-lookup"><span data-stu-id="6173c-104">ID</span></span>|<span data-ttu-id="6173c-105">1029</span><span class="sxs-lookup"><span data-stu-id="6173c-105">1029</span></span>|  
|<span data-ttu-id="6173c-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="6173c-106">Keywords</span></span>|<span data-ttu-id="6173c-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="6173c-107">WFRuntime</span></span>|  
|<span data-ttu-id="6173c-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="6173c-108">Level</span></span>|<span data-ttu-id="6173c-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="6173c-109">Verbose</span></span>|  
|<span data-ttu-id="6173c-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="6173c-110">Channel</span></span>|<span data-ttu-id="6173c-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="6173c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6173c-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6173c-112">Description</span></span>  
 <span data-ttu-id="6173c-113">Gibt an, dass ein FaultWorkItem geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="6173c-113">Indicates a FaultWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6173c-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="6173c-114">Message</span></span>  
 <span data-ttu-id="6173c-115">Wurde ein FaultWorkItem geplant für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="6173c-115">A FaultWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="6173c-116">Die Ausnahme wurde von der Aktivität '%4', DisplayName: '%5', InstanceId: '%6' propagiert.</span><span class="sxs-lookup"><span data-stu-id="6173c-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6173c-117">Details</span><span class="sxs-lookup"><span data-stu-id="6173c-117">Details</span></span>  
  
|<span data-ttu-id="6173c-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="6173c-118">Data Item Name</span></span>|<span data-ttu-id="6173c-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="6173c-119">Data Item Type</span></span>|<span data-ttu-id="6173c-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6173c-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6173c-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="6173c-121">FaultActivity</span></span>|<span data-ttu-id="6173c-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="6173c-122">xs:string</span></span>|<span data-ttu-id="6173c-123">Der Typname der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="6173c-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="6173c-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="6173c-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="6173c-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="6173c-125">xs:string</span></span>|<span data-ttu-id="6173c-126">Der Anzeigename der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="6173c-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="6173c-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="6173c-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="6173c-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="6173c-128">xs:string</span></span>|<span data-ttu-id="6173c-129">Die Instanz-ID der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="6173c-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="6173c-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="6173c-130">ExceptionActivity</span></span>|<span data-ttu-id="6173c-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="6173c-131">xs:string</span></span>|<span data-ttu-id="6173c-132">Der Typname der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="6173c-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="6173c-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="6173c-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="6173c-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="6173c-134">xs:string</span></span>|<span data-ttu-id="6173c-135">Der Anzeigename der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="6173c-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="6173c-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="6173c-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="6173c-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="6173c-137">xs:string</span></span>|<span data-ttu-id="6173c-138">Die Instanz-ID der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="6173c-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="6173c-139">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="6173c-139">Exception</span></span>|<span data-ttu-id="6173c-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="6173c-140">xs:string</span></span>|<span data-ttu-id="6173c-141">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="6173c-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="6173c-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6173c-142">AppDomain</span></span>|<span data-ttu-id="6173c-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="6173c-143">xs:string</span></span>|<span data-ttu-id="6173c-144">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="6173c-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
