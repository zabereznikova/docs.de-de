---
title: ICLRTaskManager-Schnittstelle
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 19ef7cb78791496de76e5741f8254ee88563c776
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59134653"
---
# <a name="iclrtaskmanager-interface"></a><span data-ttu-id="d87af-102">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d87af-102">ICLRTaskManager Interface</span></span>
<span data-ttu-id="d87af-103">Stellt Methoden, die dem Host explizit anfordern, die die common Language Runtime (CLR) ermöglichen Erstellen eines neuen Tasks, die aktuell ausgeführte Aufgabe zu erhalten, und legen Sie die geografische Sprache und Kultur für den Task.</span><span class="sxs-lookup"><span data-stu-id="d87af-103">Provides methods that allow the host to request explicitly that the common language runtime (CLR) create a new task, get the currently executing task, and set the geographic language and culture for the task.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d87af-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="d87af-104">Methods</span></span>  
  
|<span data-ttu-id="d87af-105">Methode</span><span class="sxs-lookup"><span data-stu-id="d87af-105">Method</span></span>|<span data-ttu-id="d87af-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d87af-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d87af-107">CreateTask-Methode</span><span class="sxs-lookup"><span data-stu-id="d87af-107">CreateTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-createtask-method.md)|<span data-ttu-id="d87af-108">Fordert explizit an, dass die CLR erstellen Sie ein neues [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) Instanz.</span><span class="sxs-lookup"><span data-stu-id="d87af-108">Requests explicitly that the CLR create a new [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance.</span></span>|  
|[<span data-ttu-id="d87af-109">GetCurrentTask-Methode</span><span class="sxs-lookup"><span data-stu-id="d87af-109">GetCurrentTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttask-method.md)|<span data-ttu-id="d87af-110">Ruft die `ICLRTask` -Instanz, die die Aufgabe darstellt, die gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d87af-110">Gets the `ICLRTask` instance that represents the task that is currently executing.</span></span>|  
|[<span data-ttu-id="d87af-111">GetCurrentTaskType-Methode</span><span class="sxs-lookup"><span data-stu-id="d87af-111">GetCurrentTaskType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttasktype-method.md)|<span data-ttu-id="d87af-112">Ruft den Typ der Aufgabe, die gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d87af-112">Gets the type of the task that is currently executing.</span></span>|  
|[<span data-ttu-id="d87af-113">SetLocale-Methode</span><span class="sxs-lookup"><span data-stu-id="d87af-113">SetLocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setlocale-method.md)|<span data-ttu-id="d87af-114">Benachrichtigt die CLR, dass der Host den Gebietsschemabezeichner für die aktuell ausgeführte Aufgabe geändert hat.</span><span class="sxs-lookup"><span data-stu-id="d87af-114">Notifies the CLR that the host has modified the locale identifier on the currently executing task.</span></span>|  
|[<span data-ttu-id="d87af-115">SetUILocale-Methode</span><span class="sxs-lookup"><span data-stu-id="d87af-115">SetUILocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setuilocale-method.md)|<span data-ttu-id="d87af-116">Benachrichtigt, dass der Host den Gebietsschemabezeichner der Benutzeroberfläche für die derzeit ausgeführte Aufgabe geändert hat der common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="d87af-116">Notifies the common language runtime that the host has modified the user interface locale identifier on the currently executing task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d87af-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d87af-117">Remarks</span></span>  
 <span data-ttu-id="d87af-118">Jede Aufgabe, die in einer gehosteten Umgebung ausgeführt wird verfügt über Darstellungen, die beide auf der Hostseite (eine Instanz von [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) und auf der CLR-Seite (eine Instanz von [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)).</span><span class="sxs-lookup"><span data-stu-id="d87af-118">Each task that is running in a hosted environment has representations both on the host side (an instance of [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) and on the CLR side (an instance of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)).</span></span> <span data-ttu-id="d87af-119">Entweder der Host oder die CLR kann die Erstellung einer Aufgabe initiieren, aber die Hostseite Darstellung muss mit einer entsprechenden CLR-Seite-Darstellung, um sicherzustellen, dass erfolgreiche Kommunikation zwischen dem Host und die CLR in Bezug auf die Aufgabe verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="d87af-119">Either the host or the CLR can initiate the creation of a task, but the host-side representation must be associated with a corresponding CLR-side representation to ensure successful communication between the host and the CLR regarding the task.</span></span> <span data-ttu-id="d87af-120">Die beiden Objekte müssen erstellt und instanziiert wird, bevor verwalteter Code in einem Betriebssystem-Thread ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="d87af-120">The two objects must be created and instantiated before managed code can execute on an operating system thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d87af-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d87af-121">Requirements</span></span>  
 <span data-ttu-id="d87af-122">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d87af-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d87af-123">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d87af-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d87af-124">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d87af-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d87af-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d87af-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d87af-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d87af-126">See also</span></span>

- [<span data-ttu-id="d87af-127">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d87af-127">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="d87af-128">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d87af-128">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="d87af-129">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d87af-129">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="d87af-130">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d87af-130">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
