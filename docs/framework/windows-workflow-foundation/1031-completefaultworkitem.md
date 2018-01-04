---
title: 1031 - CompleteFaultWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95f4ccb0-6be4-41f3-9330-fae43165828f
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a87ecb0a50437d83dd3c80d213553c8ac2143968
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="1031---completefaultworkitem"></a><span data-ttu-id="ab4cf-102">1031 - CompleteFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="ab4cf-102">1031 - CompleteFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="ab4cf-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="ab4cf-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ab4cf-104">ID</span><span class="sxs-lookup"><span data-stu-id="ab4cf-104">ID</span></span>|<span data-ttu-id="ab4cf-105">1031</span><span class="sxs-lookup"><span data-stu-id="ab4cf-105">1031</span></span>|  
|<span data-ttu-id="ab4cf-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="ab4cf-106">Keywords</span></span>|<span data-ttu-id="ab4cf-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ab4cf-107">WFRuntime</span></span>|  
|<span data-ttu-id="ab4cf-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="ab4cf-108">Level</span></span>|<span data-ttu-id="ab4cf-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="ab4cf-109">Verbose</span></span>|  
|<span data-ttu-id="ab4cf-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="ab4cf-110">Channel</span></span>|<span data-ttu-id="ab4cf-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="ab4cf-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ab4cf-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ab4cf-112">Description</span></span>  
 <span data-ttu-id="ab4cf-113">Gibt an, dass ein FaultWorkItem abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="ab4cf-113">Indicates a FaultWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ab4cf-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="ab4cf-114">Message</span></span>  
 <span data-ttu-id="ab4cf-115">Für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde ein FaultWorkItem abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="ab4cf-115">A FaultWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="ab4cf-116">Die Ausnahme wurde von der Aktivität '%4', DisplayName: '%5', InstanceId: '%6' propagiert.</span><span class="sxs-lookup"><span data-stu-id="ab4cf-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ab4cf-117">Details</span><span class="sxs-lookup"><span data-stu-id="ab4cf-117">Details</span></span>  
  
|<span data-ttu-id="ab4cf-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="ab4cf-118">Data Item Name</span></span>|<span data-ttu-id="ab4cf-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="ab4cf-119">Data Item Type</span></span>|<span data-ttu-id="ab4cf-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ab4cf-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ab4cf-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="ab4cf-121">FaultActivity</span></span>|<span data-ttu-id="ab4cf-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="ab4cf-122">xs:string</span></span>|<span data-ttu-id="ab4cf-123">Der Typname der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="ab4cf-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="ab4cf-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="ab4cf-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="ab4cf-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="ab4cf-125">xs:string</span></span>|<span data-ttu-id="ab4cf-126">Der Anzeigename der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="ab4cf-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="ab4cf-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="ab4cf-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="ab4cf-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="ab4cf-128">xs:string</span></span>|<span data-ttu-id="ab4cf-129">Die Instanz-ID der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="ab4cf-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="ab4cf-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="ab4cf-130">ExceptionActivity</span></span>|<span data-ttu-id="ab4cf-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="ab4cf-131">xs:string</span></span>|<span data-ttu-id="ab4cf-132">Der Typname der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="ab4cf-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="ab4cf-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="ab4cf-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="ab4cf-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="ab4cf-134">xs:string</span></span>|<span data-ttu-id="ab4cf-135">Der Anzeigename der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="ab4cf-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="ab4cf-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="ab4cf-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="ab4cf-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="ab4cf-137">xs:string</span></span>|<span data-ttu-id="ab4cf-138">Die Instanz-ID der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="ab4cf-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="ab4cf-139">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="ab4cf-139">Exception</span></span>|<span data-ttu-id="ab4cf-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="ab4cf-140">xs:string</span></span>|<span data-ttu-id="ab4cf-141">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="ab4cf-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="ab4cf-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ab4cf-142">AppDomain</span></span>|<span data-ttu-id="ab4cf-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="ab4cf-143">xs:string</span></span>|<span data-ttu-id="ab4cf-144">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="ab4cf-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
