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
ms.openlocfilehash: 1170b29c01275b108a6ccdf6e324c96d97c10c82
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732449"
---
# <a name="iclrtaskmanager-interface"></a><span data-ttu-id="093af-102">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="093af-102">ICLRTaskManager Interface</span></span>

<span data-ttu-id="093af-103">Stellt Methoden bereit, die es dem Host ermöglichen, explizit anzufordern, dass die Common Language Runtime (CLR) eine neue Aufgabe erstellen, die aktuell ausgeführte Aufgabe erhalten und die geografische Sprache und Kultur für den Task festlegen.</span><span class="sxs-lookup"><span data-stu-id="093af-103">Provides methods that allow the host to request explicitly that the common language runtime (CLR) create a new task, get the currently executing task, and set the geographic language and culture for the task.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="093af-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="093af-104">Methods</span></span>  
  
|<span data-ttu-id="093af-105">Methode</span><span class="sxs-lookup"><span data-stu-id="093af-105">Method</span></span>|<span data-ttu-id="093af-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="093af-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="093af-107">CreateTask-Methode</span><span class="sxs-lookup"><span data-stu-id="093af-107">CreateTask Method</span></span>](iclrtaskmanager-createtask-method.md)|<span data-ttu-id="093af-108">Fordert explizit an, dass die CLR eine neue [ICLRTask](iclrtask-interface.md) -Instanz erstellt.</span><span class="sxs-lookup"><span data-stu-id="093af-108">Requests explicitly that the CLR create a new [ICLRTask](iclrtask-interface.md) instance.</span></span>|  
|[<span data-ttu-id="093af-109">GetCurrentTask-Methode</span><span class="sxs-lookup"><span data-stu-id="093af-109">GetCurrentTask Method</span></span>](iclrtaskmanager-getcurrenttask-method.md)|<span data-ttu-id="093af-110">Ruft die- `ICLRTask` Instanz ab, die den derzeit ausgeführten Task darstellt.</span><span class="sxs-lookup"><span data-stu-id="093af-110">Gets the `ICLRTask` instance that represents the task that is currently executing.</span></span>|  
|[<span data-ttu-id="093af-111">GetCurrentTaskType-Methode</span><span class="sxs-lookup"><span data-stu-id="093af-111">GetCurrentTaskType Method</span></span>](iclrtaskmanager-getcurrenttasktype-method.md)|<span data-ttu-id="093af-112">Ruft den Typ der Aufgabe ab, die gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="093af-112">Gets the type of the task that is currently executing.</span></span>|  
|[<span data-ttu-id="093af-113">SetLocale-Methode</span><span class="sxs-lookup"><span data-stu-id="093af-113">SetLocale Method</span></span>](iclrtaskmanager-setlocale-method.md)|<span data-ttu-id="093af-114">Benachrichtigt die CLR, dass der Host den Gebiets Schema Bezeichner für die aktuell ausgeführte Aufgabe geändert hat.</span><span class="sxs-lookup"><span data-stu-id="093af-114">Notifies the CLR that the host has modified the locale identifier on the currently executing task.</span></span>|  
|[<span data-ttu-id="093af-115">SetUILocale-Methode</span><span class="sxs-lookup"><span data-stu-id="093af-115">SetUILocale Method</span></span>](iclrtaskmanager-setuilocale-method.md)|<span data-ttu-id="093af-116">Benachrichtigt den Common Language Runtime, dass der Host den Gebiets Schema Bezeichner für die Benutzeroberfläche für den aktuell ausgeführten Task geändert hat.</span><span class="sxs-lookup"><span data-stu-id="093af-116">Notifies the common language runtime that the host has modified the user interface locale identifier on the currently executing task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="093af-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="093af-117">Remarks</span></span>  

 <span data-ttu-id="093af-118">Jede Aufgabe, die in einer gehosteten Umgebung ausgeführt wird, verfügt über Darstellungen sowohl auf der Host Seite (eine Instanz von [IHostTask](ihosttask-interface.md)) als auch auf der CLR-Seite (eine Instanz von [ICLRTask](iclrtask-interface.md)).</span><span class="sxs-lookup"><span data-stu-id="093af-118">Each task that is running in a hosted environment has representations both on the host side (an instance of [IHostTask](ihosttask-interface.md)) and on the CLR side (an instance of [ICLRTask](iclrtask-interface.md)).</span></span> <span data-ttu-id="093af-119">Entweder der Host oder die CLR kann die Erstellung einer Aufgabe initiieren, aber die Host seitige Darstellung muss einer entsprechenden CLR-seitigen Darstellung zugeordnet sein, um eine erfolgreiche Kommunikation zwischen dem Host und der CLR bezüglich der Aufgabe sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="093af-119">Either the host or the CLR can initiate the creation of a task, but the host-side representation must be associated with a corresponding CLR-side representation to ensure successful communication between the host and the CLR regarding the task.</span></span> <span data-ttu-id="093af-120">Die beiden Objekte müssen erstellt und instanziiert werden, bevor verwalteter Code in einem Betriebssystem Thread ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="093af-120">The two objects must be created and instantiated before managed code can execute on an operating system thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="093af-121">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="093af-121">Requirements</span></span>  

 <span data-ttu-id="093af-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="093af-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="093af-123">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="093af-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="093af-124">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="093af-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="093af-125">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="093af-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="093af-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="093af-126">See also</span></span>

- [<span data-ttu-id="093af-127">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="093af-127">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="093af-128">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="093af-128">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="093af-129">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="093af-129">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="093af-130">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="093af-130">Hosting Interfaces</span></span>](hosting-interfaces.md)
