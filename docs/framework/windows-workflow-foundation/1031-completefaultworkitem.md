---
title: 1031 - CompleteFaultWorkItem
ms.date: 03/30/2017
ms.assetid: 95f4ccb0-6be4-41f3-9330-fae43165828f
ms.openlocfilehash: 557155fab35a37bdbaa45efb26d6bc025ad825c4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96281832"
---
# <a name="1031---completefaultworkitem"></a><span data-ttu-id="2f84e-102">1031 - CompleteFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="2f84e-102">1031 - CompleteFaultWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="2f84e-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="2f84e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2f84e-104">id</span><span class="sxs-lookup"><span data-stu-id="2f84e-104">ID</span></span>|<span data-ttu-id="2f84e-105">1031</span><span class="sxs-lookup"><span data-stu-id="2f84e-105">1031</span></span>|  
|<span data-ttu-id="2f84e-106">Keywords</span><span class="sxs-lookup"><span data-stu-id="2f84e-106">Keywords</span></span>|<span data-ttu-id="2f84e-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="2f84e-107">WFRuntime</span></span>|  
|<span data-ttu-id="2f84e-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="2f84e-108">Level</span></span>|<span data-ttu-id="2f84e-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="2f84e-109">Verbose</span></span>|  
|<span data-ttu-id="2f84e-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="2f84e-110">Channel</span></span>|<span data-ttu-id="2f84e-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="2f84e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2f84e-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2f84e-112">Description</span></span>  

 <span data-ttu-id="2f84e-113">Gibt an, dass ein FaultWorkItem abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="2f84e-113">Indicates a FaultWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2f84e-114">`Message`</span><span class="sxs-lookup"><span data-stu-id="2f84e-114">Message</span></span>  

 <span data-ttu-id="2f84e-115">Für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde ein FaultWorkItem abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="2f84e-115">A FaultWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="2f84e-116">Die Ausnahme wurde von der Aktivität '%4', DisplayName: '%5', InstanceId: '%6' propagiert.</span><span class="sxs-lookup"><span data-stu-id="2f84e-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2f84e-117">Details</span><span class="sxs-lookup"><span data-stu-id="2f84e-117">Details</span></span>  
  
|<span data-ttu-id="2f84e-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="2f84e-118">Data Item Name</span></span>|<span data-ttu-id="2f84e-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="2f84e-119">Data Item Type</span></span>|<span data-ttu-id="2f84e-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2f84e-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2f84e-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="2f84e-121">FaultActivity</span></span>|<span data-ttu-id="2f84e-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="2f84e-122">xs:string</span></span>|<span data-ttu-id="2f84e-123">Der Typname der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="2f84e-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="2f84e-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="2f84e-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="2f84e-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="2f84e-125">xs:string</span></span>|<span data-ttu-id="2f84e-126">Der Anzeigename der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="2f84e-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="2f84e-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="2f84e-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="2f84e-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="2f84e-128">xs:string</span></span>|<span data-ttu-id="2f84e-129">Die Instanz-ID der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="2f84e-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="2f84e-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="2f84e-130">ExceptionActivity</span></span>|<span data-ttu-id="2f84e-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="2f84e-131">xs:string</span></span>|<span data-ttu-id="2f84e-132">Der Typname der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="2f84e-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="2f84e-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="2f84e-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="2f84e-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="2f84e-134">xs:string</span></span>|<span data-ttu-id="2f84e-135">Der Anzeigename der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="2f84e-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="2f84e-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="2f84e-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="2f84e-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="2f84e-137">xs:string</span></span>|<span data-ttu-id="2f84e-138">Die Instanz-ID der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="2f84e-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="2f84e-139">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="2f84e-139">Exception</span></span>|<span data-ttu-id="2f84e-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="2f84e-140">xs:string</span></span>|<span data-ttu-id="2f84e-141">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="2f84e-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="2f84e-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2f84e-142">AppDomain</span></span>|<span data-ttu-id="2f84e-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="2f84e-143">xs:string</span></span>|<span data-ttu-id="2f84e-144">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="2f84e-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
