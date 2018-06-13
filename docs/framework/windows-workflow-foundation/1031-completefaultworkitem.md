---
title: 1031 - CompleteFaultWorkItem
ms.date: 03/30/2017
ms.assetid: 95f4ccb0-6be4-41f3-9330-fae43165828f
ms.openlocfilehash: cdcbe516fc8ba7440b3d109a5e5cadc105ecee9f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509742"
---
# <a name="1031---completefaultworkitem"></a><span data-ttu-id="b6961-102">1031 - CompleteFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="b6961-102">1031 - CompleteFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="b6961-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="b6961-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b6961-104">ID</span><span class="sxs-lookup"><span data-stu-id="b6961-104">ID</span></span>|<span data-ttu-id="b6961-105">1031</span><span class="sxs-lookup"><span data-stu-id="b6961-105">1031</span></span>|  
|<span data-ttu-id="b6961-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="b6961-106">Keywords</span></span>|<span data-ttu-id="b6961-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="b6961-107">WFRuntime</span></span>|  
|<span data-ttu-id="b6961-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="b6961-108">Level</span></span>|<span data-ttu-id="b6961-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="b6961-109">Verbose</span></span>|  
|<span data-ttu-id="b6961-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="b6961-110">Channel</span></span>|<span data-ttu-id="b6961-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="b6961-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b6961-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b6961-112">Description</span></span>  
 <span data-ttu-id="b6961-113">Gibt an, dass ein FaultWorkItem abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="b6961-113">Indicates a FaultWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b6961-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="b6961-114">Message</span></span>  
 <span data-ttu-id="b6961-115">Für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde ein FaultWorkItem abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="b6961-115">A FaultWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="b6961-116">Die Ausnahme wurde von der Aktivität '%4', DisplayName: '%5', InstanceId: '%6' propagiert.</span><span class="sxs-lookup"><span data-stu-id="b6961-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b6961-117">Details</span><span class="sxs-lookup"><span data-stu-id="b6961-117">Details</span></span>  
  
|<span data-ttu-id="b6961-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="b6961-118">Data Item Name</span></span>|<span data-ttu-id="b6961-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="b6961-119">Data Item Type</span></span>|<span data-ttu-id="b6961-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b6961-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b6961-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="b6961-121">FaultActivity</span></span>|<span data-ttu-id="b6961-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="b6961-122">xs:string</span></span>|<span data-ttu-id="b6961-123">Der Typname der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="b6961-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="b6961-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="b6961-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="b6961-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="b6961-125">xs:string</span></span>|<span data-ttu-id="b6961-126">Der Anzeigename der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="b6961-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="b6961-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="b6961-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="b6961-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="b6961-128">xs:string</span></span>|<span data-ttu-id="b6961-129">Die Instanz-ID der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="b6961-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="b6961-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="b6961-130">ExceptionActivity</span></span>|<span data-ttu-id="b6961-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="b6961-131">xs:string</span></span>|<span data-ttu-id="b6961-132">Der Typname der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="b6961-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="b6961-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="b6961-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="b6961-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="b6961-134">xs:string</span></span>|<span data-ttu-id="b6961-135">Der Anzeigename der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="b6961-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="b6961-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="b6961-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="b6961-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="b6961-137">xs:string</span></span>|<span data-ttu-id="b6961-138">Die Instanz-ID der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="b6961-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="b6961-139">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="b6961-139">Exception</span></span>|<span data-ttu-id="b6961-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="b6961-140">xs:string</span></span>|<span data-ttu-id="b6961-141">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="b6961-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="b6961-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b6961-142">AppDomain</span></span>|<span data-ttu-id="b6961-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="b6961-143">xs:string</span></span>|<span data-ttu-id="b6961-144">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="b6961-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
