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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 260647b56d945600afea5609f06d36385fa66014
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="1031---completefaultworkitem"></a><span data-ttu-id="d543a-102">1031 - CompleteFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="d543a-102">1031 - CompleteFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="d543a-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d543a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d543a-104">ID</span><span class="sxs-lookup"><span data-stu-id="d543a-104">ID</span></span>|<span data-ttu-id="d543a-105">1031</span><span class="sxs-lookup"><span data-stu-id="d543a-105">1031</span></span>|  
|<span data-ttu-id="d543a-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d543a-106">Keywords</span></span>|<span data-ttu-id="d543a-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="d543a-107">WFRuntime</span></span>|  
|<span data-ttu-id="d543a-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="d543a-108">Level</span></span>|<span data-ttu-id="d543a-109">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="d543a-109">Verbose</span></span>|  
|<span data-ttu-id="d543a-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="d543a-110">Channel</span></span>|<span data-ttu-id="d543a-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="d543a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d543a-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d543a-112">Description</span></span>  
 <span data-ttu-id="d543a-113">Gibt an, dass ein FaultWorkItem abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="d543a-113">Indicates a FaultWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d543a-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="d543a-114">Message</span></span>  
 <span data-ttu-id="d543a-115">Für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde ein FaultWorkItem abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="d543a-115">A FaultWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="d543a-116">Die Ausnahme wurde von der Aktivität '%4', DisplayName: '%5', InstanceId: '%6' propagiert.</span><span class="sxs-lookup"><span data-stu-id="d543a-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d543a-117">Details</span><span class="sxs-lookup"><span data-stu-id="d543a-117">Details</span></span>  
  
|<span data-ttu-id="d543a-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="d543a-118">Data Item Name</span></span>|<span data-ttu-id="d543a-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="d543a-119">Data Item Type</span></span>|<span data-ttu-id="d543a-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d543a-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d543a-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="d543a-121">FaultActivity</span></span>|<span data-ttu-id="d543a-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="d543a-122">xs:string</span></span>|<span data-ttu-id="d543a-123">Der Typname der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="d543a-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="d543a-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="d543a-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="d543a-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="d543a-125">xs:string</span></span>|<span data-ttu-id="d543a-126">Der Anzeigename der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="d543a-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="d543a-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="d543a-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="d543a-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="d543a-128">xs:string</span></span>|<span data-ttu-id="d543a-129">Die Instanz-ID der fault-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="d543a-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="d543a-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="d543a-130">ExceptionActivity</span></span>|<span data-ttu-id="d543a-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="d543a-131">xs:string</span></span>|<span data-ttu-id="d543a-132">Der Typname der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="d543a-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="d543a-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="d543a-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="d543a-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="d543a-134">xs:string</span></span>|<span data-ttu-id="d543a-135">Der Anzeigename der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="d543a-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="d543a-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="d543a-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="d543a-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="d543a-137">xs:string</span></span>|<span data-ttu-id="d543a-138">Die Instanz-ID der Aktivität, die die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="d543a-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="d543a-139">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="d543a-139">Exception</span></span>|<span data-ttu-id="d543a-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="d543a-140">xs:string</span></span>|<span data-ttu-id="d543a-141">Die Ausnahmedetails der Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="d543a-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="d543a-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d543a-142">AppDomain</span></span>|<span data-ttu-id="d543a-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="d543a-143">xs:string</span></span>|<span data-ttu-id="d543a-144">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="d543a-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
