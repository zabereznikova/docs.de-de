---
title: IHostTask::Start-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTask.Start
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTask::Start
helpviewer_keywords:
- IHostTask::Start method [.NET Framework hosting]
- Start method, IHostTask interface [.NET Framework hosting]
ms.assetid: b18742b0-d8c4-401c-ae89-e6eccdaa81d0
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f1a289099245228b8806639cb98f579bc56317b0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskstart-method"></a><span data-ttu-id="4a1fb-102">IHostTask::Start-Methode</span><span class="sxs-lookup"><span data-stu-id="4a1fb-102">IHostTask::Start Method</span></span>
<span data-ttu-id="4a1fb-103">Fordert an, dass der Host die Aufgabe, die vom aktuellen verschieben [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) -Instanz anhand einer angehaltenen in einen aktiven Zustand, in dem Code ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="4a1fb-103">Requests that the host move the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance from a suspended to a live state, in which code can be executed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a1fb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4a1fb-104">Syntax</span></span>  
  
```  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="4a1fb-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4a1fb-105">Return Value</span></span>  
  
|<span data-ttu-id="4a1fb-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4a1fb-106">HRESULT</span></span>|<span data-ttu-id="4a1fb-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4a1fb-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4a1fb-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="4a1fb-108">S_OK</span></span>|<span data-ttu-id="4a1fb-109">Start wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4a1fb-109">Start returned successfully.</span></span>|  
|<span data-ttu-id="4a1fb-110">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4a1fb-110">E_FAIL</span></span>|<span data-ttu-id="4a1fb-111">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="4a1fb-111">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4a1fb-112">Wenn eine Methode E_FAIL zurückgibt, ist die common Language Runtime (CLR) nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="4a1fb-112">When a method returns E_FAIL, the common language runtime (CLR) is no longer usable within the process.</span></span> <span data-ttu-id="4a1fb-113">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="4a1fb-113">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a1fb-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4a1fb-114">Remarks</span></span>  
 <span data-ttu-id="4a1fb-115">`Start`Gibt immer einen HRESULT-Wert von S_OK zurück, außer in Fällen, in dem nach ein schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="4a1fb-115">`Start` always returns an HRESULT value of S_OK, except in cases where a catastrophic failure has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a1fb-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4a1fb-116">Requirements</span></span>  
 <span data-ttu-id="4a1fb-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a1fb-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a1fb-118">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4a1fb-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4a1fb-119">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="4a1fb-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4a1fb-120">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a1fb-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a1fb-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4a1fb-121">See Also</span></span>  
 [<span data-ttu-id="4a1fb-122">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4a1fb-122">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="4a1fb-123">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4a1fb-123">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="4a1fb-124">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4a1fb-124">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="4a1fb-125">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4a1fb-125">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
