---
title: ICLRTaskManager-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager
helpviewer_keywords:
- ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: 2bd55e0c-001b-41fd-b29d-f01670fe8216
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 342d7b82802fcfbe9e179d85d6d692205f19e382
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtaskmanager-interface"></a><span data-ttu-id="2b886-102">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2b886-102">ICLRTaskManager Interface</span></span>
<span data-ttu-id="2b886-103">Enthält Methoden, die dem Host explizit anfordern, die die common Language Runtime (CLR) ermöglichen, Erstellen eines neuen Tasks, die aktuell ausgeführte Aufgabe erhalten und die geografische Sprache und Kultur für den Task festlegen.</span><span class="sxs-lookup"><span data-stu-id="2b886-103">Provides methods that allow the host to request explicitly that the common language runtime (CLR) create a new task, get the currently executing task, and set the geographic language and culture for the task.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2b886-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="2b886-104">Methods</span></span>  
  
|<span data-ttu-id="2b886-105">Methode</span><span class="sxs-lookup"><span data-stu-id="2b886-105">Method</span></span>|<span data-ttu-id="2b886-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2b886-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2b886-107">CreateTask-Methode</span><span class="sxs-lookup"><span data-stu-id="2b886-107">CreateTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-createtask-method.md)|<span data-ttu-id="2b886-108">Fordert explizit an, dass die CLR erstellen Sie ein neues [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) Instanz.</span><span class="sxs-lookup"><span data-stu-id="2b886-108">Requests explicitly that the CLR create a new [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance.</span></span>|  
|[<span data-ttu-id="2b886-109">GetCurrentTask-Methode</span><span class="sxs-lookup"><span data-stu-id="2b886-109">GetCurrentTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttask-method.md)|<span data-ttu-id="2b886-110">Ruft die `ICLRTask` -Instanz, die die Aufgabe darstellt, die gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2b886-110">Gets the `ICLRTask` instance that represents the task that is currently executing.</span></span>|  
|[<span data-ttu-id="2b886-111">GetCurrentTaskType-Methode</span><span class="sxs-lookup"><span data-stu-id="2b886-111">GetCurrentTaskType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttasktype-method.md)|<span data-ttu-id="2b886-112">Ruft den Typ der Aufgabe, die gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2b886-112">Gets the type of the task that is currently executing.</span></span>|  
|[<span data-ttu-id="2b886-113">SetLocale-Methode</span><span class="sxs-lookup"><span data-stu-id="2b886-113">SetLocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setlocale-method.md)|<span data-ttu-id="2b886-114">Benachrichtigt die CLR, dass der Host den Gebietsschemabezeichner für die aktuell ausgeführte Aufgabe geändert hat.</span><span class="sxs-lookup"><span data-stu-id="2b886-114">Notifies the CLR that the host has modified the locale identifier on the currently executing task.</span></span>|  
|[<span data-ttu-id="2b886-115">SetUILocale-Methode</span><span class="sxs-lookup"><span data-stu-id="2b886-115">SetUILocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setuilocale-method.md)|<span data-ttu-id="2b886-116">Benachrichtigt der common Language Runtime, dass der Host den Gebietsschemabezeichner der Benutzeroberfläche für die aktuell ausgeführte Aufgabe geändert hat.</span><span class="sxs-lookup"><span data-stu-id="2b886-116">Notifies the common language runtime that the host has modified the user interface locale identifier on the currently executing task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b886-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2b886-117">Remarks</span></span>  
 <span data-ttu-id="2b886-118">Jede Aufgabe, die in einer gehosteten Umgebung ausgeführt wird verfügt über Darstellungen, die beide auf der Hostseite (eine Instanz von [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) und auf der CLR-Seite (eine Instanz von [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)).</span><span class="sxs-lookup"><span data-stu-id="2b886-118">Each task that is running in a hosted environment has representations both on the host side (an instance of [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) and on the CLR side (an instance of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)).</span></span> <span data-ttu-id="2b886-119">Der Host oder die CLR kann die Erstellung einer Aufgabe initiieren, aber die hostseitige Darstellung muss mit einer entsprechenden CLR-Seite-Darstellung, um sicherzustellen, dass erfolgreiche Kommunikation zwischen dem Host und der CLR in Bezug auf die Aufgabe verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="2b886-119">Either the host or the CLR can initiate the creation of a task, but the host-side representation must be associated with a corresponding CLR-side representation to ensure successful communication between the host and the CLR regarding the task.</span></span> <span data-ttu-id="2b886-120">Die beiden Objekte müssen erstellt und instanziiert wird, bevor verwalteter Code auf einem Betriebssystem-Thread ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="2b886-120">The two objects must be created and instantiated before managed code can execute on an operating system thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b886-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2b886-121">Requirements</span></span>  
 <span data-ttu-id="2b886-122">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b886-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b886-123">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2b886-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2b886-124">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2b886-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2b886-125">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b886-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b886-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b886-126">See Also</span></span>  
 [<span data-ttu-id="2b886-127">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2b886-127">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="2b886-128">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2b886-128">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="2b886-129">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2b886-129">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="2b886-130">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="2b886-130">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
