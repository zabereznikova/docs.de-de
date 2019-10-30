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
ms.openlocfilehash: e25a6a03a836b8b4964b8260c974c8e8d8d9998d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092189"
---
# <a name="iclrtaskmanager-interface"></a><span data-ttu-id="f459f-102">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f459f-102">ICLRTaskManager Interface</span></span>
<span data-ttu-id="f459f-103">Stellt Methoden bereit, die es dem Host ermöglichen, explizit anzufordern, dass die Common Language Runtime (CLR) eine neue Aufgabe erstellen, die aktuell ausgeführte Aufgabe erhalten und die geografische Sprache und Kultur für den Task festlegen.</span><span class="sxs-lookup"><span data-stu-id="f459f-103">Provides methods that allow the host to request explicitly that the common language runtime (CLR) create a new task, get the currently executing task, and set the geographic language and culture for the task.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f459f-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="f459f-104">Methods</span></span>  
  
|<span data-ttu-id="f459f-105">Methode</span><span class="sxs-lookup"><span data-stu-id="f459f-105">Method</span></span>|<span data-ttu-id="f459f-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f459f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f459f-107">CreateTask-Methode</span><span class="sxs-lookup"><span data-stu-id="f459f-107">CreateTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-createtask-method.md)|<span data-ttu-id="f459f-108">Fordert explizit an, dass die CLR eine neue [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) -Instanz erstellt.</span><span class="sxs-lookup"><span data-stu-id="f459f-108">Requests explicitly that the CLR create a new [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance.</span></span>|  
|[<span data-ttu-id="f459f-109">GetCurrentTask-Methode</span><span class="sxs-lookup"><span data-stu-id="f459f-109">GetCurrentTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttask-method.md)|<span data-ttu-id="f459f-110">Ruft die `ICLRTask`-Instanz ab, die den derzeit ausgeführten Task darstellt.</span><span class="sxs-lookup"><span data-stu-id="f459f-110">Gets the `ICLRTask` instance that represents the task that is currently executing.</span></span>|  
|[<span data-ttu-id="f459f-111">GetCurrentTaskType-Methode</span><span class="sxs-lookup"><span data-stu-id="f459f-111">GetCurrentTaskType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttasktype-method.md)|<span data-ttu-id="f459f-112">Ruft den Typ der Aufgabe ab, die gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f459f-112">Gets the type of the task that is currently executing.</span></span>|  
|[<span data-ttu-id="f459f-113">SetLocale-Methode</span><span class="sxs-lookup"><span data-stu-id="f459f-113">SetLocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setlocale-method.md)|<span data-ttu-id="f459f-114">Benachrichtigt die CLR, dass der Host den Gebiets Schema Bezeichner für die aktuell ausgeführte Aufgabe geändert hat.</span><span class="sxs-lookup"><span data-stu-id="f459f-114">Notifies the CLR that the host has modified the locale identifier on the currently executing task.</span></span>|  
|[<span data-ttu-id="f459f-115">SetUILocale-Methode</span><span class="sxs-lookup"><span data-stu-id="f459f-115">SetUILocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setuilocale-method.md)|<span data-ttu-id="f459f-116">Benachrichtigt den Common Language Runtime, dass der Host den Gebiets Schema Bezeichner für die Benutzeroberfläche für den aktuell ausgeführten Task geändert hat.</span><span class="sxs-lookup"><span data-stu-id="f459f-116">Notifies the common language runtime that the host has modified the user interface locale identifier on the currently executing task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f459f-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f459f-117">Remarks</span></span>  
 <span data-ttu-id="f459f-118">Jede Aufgabe, die in einer gehosteten Umgebung ausgeführt wird, verfügt über Darstellungen sowohl auf der Host Seite (eine Instanz von [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) als auch auf der CLR-Seite (eine Instanz von [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)).</span><span class="sxs-lookup"><span data-stu-id="f459f-118">Each task that is running in a hosted environment has representations both on the host side (an instance of [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) and on the CLR side (an instance of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)).</span></span> <span data-ttu-id="f459f-119">Entweder der Host oder die CLR kann die Erstellung einer Aufgabe initiieren, aber die Host seitige Darstellung muss einer entsprechenden CLR-seitigen Darstellung zugeordnet sein, um eine erfolgreiche Kommunikation zwischen dem Host und der CLR bezüglich der Aufgabe sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="f459f-119">Either the host or the CLR can initiate the creation of a task, but the host-side representation must be associated with a corresponding CLR-side representation to ensure successful communication between the host and the CLR regarding the task.</span></span> <span data-ttu-id="f459f-120">Die beiden Objekte müssen erstellt und instanziiert werden, bevor verwalteter Code in einem Betriebssystem Thread ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="f459f-120">The two objects must be created and instantiated before managed code can execute on an operating system thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f459f-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f459f-121">Requirements</span></span>  
 <span data-ttu-id="f459f-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f459f-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f459f-123">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="f459f-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f459f-124">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f459f-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f459f-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f459f-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f459f-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f459f-126">See also</span></span>

- [<span data-ttu-id="f459f-127">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f459f-127">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="f459f-128">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f459f-128">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="f459f-129">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f459f-129">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="f459f-130">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f459f-130">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
