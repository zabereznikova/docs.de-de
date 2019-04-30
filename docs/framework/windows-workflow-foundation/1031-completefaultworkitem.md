---
title: 1031 - CompleteFaultWorkItem
ms.date: 03/30/2017
ms.assetid: 95f4ccb0-6be4-41f3-9330-fae43165828f
ms.openlocfilehash: cdcbe516fc8ba7440b3d109a5e5cadc105ecee9f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008797"
---
# <a name="1031---completefaultworkitem"></a><span data-ttu-id="417dd-102">1031 - CompleteFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="417dd-102">1031 - CompleteFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="417dd-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="417dd-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="417dd-104">ID</span><span class="sxs-lookup"><span data-stu-id="417dd-104">ID</span></span>|<span data-ttu-id="417dd-105">1031</span><span class="sxs-lookup"><span data-stu-id="417dd-105">1031</span></span>|  
|<span data-ttu-id="417dd-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="417dd-106">Keywords</span></span>|<span data-ttu-id="417dd-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="417dd-107">WFRuntime</span></span>|  
|<span data-ttu-id="417dd-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="417dd-108">Level</span></span>|<span data-ttu-id="417dd-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="417dd-109">Verbose</span></span>|  
|<span data-ttu-id="417dd-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="417dd-110">Channel</span></span>|<span data-ttu-id="417dd-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="417dd-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="417dd-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="417dd-112">Description</span></span>  
 <span data-ttu-id="417dd-113">Gibt an, dass ein FaultWorkItem abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="417dd-113">Indicates a FaultWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="417dd-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="417dd-114">Message</span></span>  
 <span data-ttu-id="417dd-115">Für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde ein FaultWorkItem abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="417dd-115">A FaultWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="417dd-116">Die Ausnahme wurde von der Aktivität '%4', DisplayName: '%5', InstanceId: '%6' propagiert.</span><span class="sxs-lookup"><span data-stu-id="417dd-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="417dd-117">Details</span><span class="sxs-lookup"><span data-stu-id="417dd-117">Details</span></span>  
  
|<span data-ttu-id="417dd-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="417dd-118">Data Item Name</span></span>|<span data-ttu-id="417dd-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="417dd-119">Data Item Type</span></span>|<span data-ttu-id="417dd-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="417dd-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="417dd-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="417dd-121">FaultActivity</span></span>|<span data-ttu-id="417dd-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="417dd-122">xs:string</span></span>|<span data-ttu-id="417dd-123">Der Typname der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="417dd-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="417dd-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="417dd-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="417dd-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="417dd-125">xs:string</span></span>|<span data-ttu-id="417dd-126">Der Anzeigename der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="417dd-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="417dd-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="417dd-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="417dd-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="417dd-128">xs:string</span></span>|<span data-ttu-id="417dd-129">Die Instanz-ID der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="417dd-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="417dd-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="417dd-130">ExceptionActivity</span></span>|<span data-ttu-id="417dd-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="417dd-131">xs:string</span></span>|<span data-ttu-id="417dd-132">Der Typname der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="417dd-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="417dd-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="417dd-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="417dd-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="417dd-134">xs:string</span></span>|<span data-ttu-id="417dd-135">Der Anzeigename der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="417dd-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="417dd-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="417dd-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="417dd-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="417dd-137">xs:string</span></span>|<span data-ttu-id="417dd-138">Die Instanz-ID der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="417dd-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="417dd-139">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="417dd-139">Exception</span></span>|<span data-ttu-id="417dd-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="417dd-140">xs:string</span></span>|<span data-ttu-id="417dd-141">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="417dd-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="417dd-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="417dd-142">AppDomain</span></span>|<span data-ttu-id="417dd-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="417dd-143">xs:string</span></span>|<span data-ttu-id="417dd-144">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="417dd-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
