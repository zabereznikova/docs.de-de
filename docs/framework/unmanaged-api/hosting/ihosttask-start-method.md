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
ms.openlocfilehash: d45c5b09358430535438734b38e5dce5d1bcdd3e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59101626"
---
# <a name="ihosttaskstart-method"></a><span data-ttu-id="fea46-102">IHostTask::Start-Methode</span><span class="sxs-lookup"><span data-stu-id="fea46-102">IHostTask::Start Method</span></span>
<span data-ttu-id="fea46-103">Fordert an, dass der Host verschieben Sie die Aufgabe, die vom aktuellen [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) Instanz aus einem Ruhezustand in einen aktiven Zustand, in dem Code ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="fea46-103">Requests that the host move the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance from a suspended to a live state, in which code can be executed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fea46-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fea46-104">Syntax</span></span>  
  
```  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="fea46-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fea46-105">Return Value</span></span>  
  
|<span data-ttu-id="fea46-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fea46-106">HRESULT</span></span>|<span data-ttu-id="fea46-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fea46-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fea46-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="fea46-108">S_OK</span></span>|<span data-ttu-id="fea46-109">Start wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="fea46-109">Start returned successfully.</span></span>|  
|<span data-ttu-id="fea46-110">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fea46-110">E_FAIL</span></span>|<span data-ttu-id="fea46-111">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="fea46-111">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fea46-112">Wenn eine Methode E_FAIL zurückgibt, ist die common Language Runtime (CLR) nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fea46-112">When a method returns E_FAIL, the common language runtime (CLR) is no longer usable within the process.</span></span> <span data-ttu-id="fea46-113">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="fea46-113">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fea46-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fea46-114">Remarks</span></span>  
 `Start` <span data-ttu-id="fea46-115">immer gibt einen HRESULT-Wert von S_OK zurück, es sei denn, ein schwerwiegender Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="fea46-115">always returns an HRESULT value of S_OK, except in cases where a catastrophic failure has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fea46-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fea46-116">Requirements</span></span>  
 <span data-ttu-id="fea46-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fea46-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fea46-118">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fea46-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fea46-119">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="fea46-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="fea46-120">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="fea46-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fea46-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fea46-121">See also</span></span>

- [<span data-ttu-id="fea46-122">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fea46-122">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="fea46-123">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fea46-123">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="fea46-124">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fea46-124">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="fea46-125">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fea46-125">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
