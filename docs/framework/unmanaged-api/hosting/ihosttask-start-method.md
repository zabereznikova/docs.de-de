---
title: IHostTask::Start-Methode
ms.date: 03/30/2017
api_name:
- IHostTask.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::Start
helpviewer_keywords:
- IHostTask::Start method [.NET Framework hosting]
- Start method, IHostTask interface [.NET Framework hosting]
ms.assetid: b18742b0-d8c4-401c-ae89-e6eccdaa81d0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2bc996973a98f3b8596b449e1524d5c93b4456e3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749808"
---
# <a name="ihosttaskstart-method"></a><span data-ttu-id="64df7-102">IHostTask::Start-Methode</span><span class="sxs-lookup"><span data-stu-id="64df7-102">IHostTask::Start Method</span></span>
<span data-ttu-id="64df7-103">Fordert an, dass der Host verschieben Sie die Aufgabe, die vom aktuellen [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) Instanz aus einem Ruhezustand in einen aktiven Zustand, in dem Code ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="64df7-103">Requests that the host move the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance from a suspended to a live state, in which code can be executed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64df7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="64df7-104">Syntax</span></span>  
  
```cpp  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="64df7-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="64df7-105">Return Value</span></span>  
  
|<span data-ttu-id="64df7-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="64df7-106">HRESULT</span></span>|<span data-ttu-id="64df7-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="64df7-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="64df7-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="64df7-108">S_OK</span></span>|<span data-ttu-id="64df7-109">Start wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="64df7-109">Start returned successfully.</span></span>|  
|<span data-ttu-id="64df7-110">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="64df7-110">E_FAIL</span></span>|<span data-ttu-id="64df7-111">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="64df7-111">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="64df7-112">Wenn eine Methode E_FAIL zurückgibt, ist die common Language Runtime (CLR) nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="64df7-112">When a method returns E_FAIL, the common language runtime (CLR) is no longer usable within the process.</span></span> <span data-ttu-id="64df7-113">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="64df7-113">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64df7-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="64df7-114">Remarks</span></span>  
 <span data-ttu-id="64df7-115">`Start` immer gibt einen HRESULT-Wert von S_OK zurück, es sei denn, ein schwerwiegender Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="64df7-115">`Start` always returns an HRESULT value of S_OK, except in cases where a catastrophic failure has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64df7-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="64df7-116">Requirements</span></span>  
 <span data-ttu-id="64df7-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64df7-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64df7-118">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="64df7-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="64df7-119">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="64df7-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="64df7-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64df7-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64df7-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="64df7-121">See also</span></span>

- [<span data-ttu-id="64df7-122">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="64df7-122">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="64df7-123">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="64df7-123">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="64df7-124">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="64df7-124">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="64df7-125">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="64df7-125">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
