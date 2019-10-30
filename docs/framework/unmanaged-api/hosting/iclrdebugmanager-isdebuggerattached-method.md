---
title: ICLRDebugManager::IsDebuggerAttached-Methode
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.IsDebuggerAttached
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::IsDebuggerAttached
helpviewer_keywords:
- IsDebuggerAttached method, ICLRDebugManager interface [.NET Framework hosting]
- ICLRDebugManager::IsDebuggerAttached method [.NET Framework hosting]
ms.assetid: 2f105fe0-f52d-49c5-bda5-583fb27e3aa6
topic_type:
- apiref
ms.openlocfilehash: a58fcb6c1fa2aad96cdd29194a21eaf590536cdd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129392"
---
# <a name="iclrdebugmanagerisdebuggerattached-method"></a><span data-ttu-id="a5cf6-102">ICLRDebugManager::IsDebuggerAttached-Methode</span><span class="sxs-lookup"><span data-stu-id="a5cf6-102">ICLRDebugManager::IsDebuggerAttached Method</span></span>
<span data-ttu-id="a5cf6-103">Ruft einen Wert ab, der angibt, ob ein Debugger an den Prozess angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="a5cf6-103">Gets a value that indicates whether a debugger is attached to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5cf6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a5cf6-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5cf6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a5cf6-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="a5cf6-106">[out] `true`, wenn ein Debugger an den Prozess angefügt ist. Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="a5cf6-106">[out] `true` if a debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a5cf6-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a5cf6-107">Return Value</span></span>  
  
|<span data-ttu-id="a5cf6-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a5cf6-108">HRESULT</span></span>|<span data-ttu-id="a5cf6-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a5cf6-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a5cf6-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a5cf6-110">S_OK</span></span>|<span data-ttu-id="a5cf6-111">`IsDebuggerAttached` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a5cf6-111">`IsDebuggerAttached` returned successfully.</span></span>|  
|<span data-ttu-id="a5cf6-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a5cf6-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a5cf6-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="a5cf6-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a5cf6-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a5cf6-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a5cf6-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="a5cf6-115">The call timed out.</span></span>|  
|<span data-ttu-id="a5cf6-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a5cf6-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a5cf6-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="a5cf6-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a5cf6-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a5cf6-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a5cf6-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="a5cf6-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a5cf6-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a5cf6-120">E_FAIL</span></span>|<span data-ttu-id="a5cf6-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="a5cf6-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a5cf6-122">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR nicht mehr innerhalb des Prozesses verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a5cf6-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a5cf6-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="a5cf6-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5cf6-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a5cf6-124">Remarks</span></span>  
 <span data-ttu-id="a5cf6-125">`IsDebuggerAttached` ermöglicht es dem Host, die CLR abzufragen, um zu bestimmen, ob ein Debugger an den Prozess angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="a5cf6-125">`IsDebuggerAttached` allows the host to query the CLR to determine whether a debugger is attached to the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5cf6-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a5cf6-126">Requirements</span></span>  
 <span data-ttu-id="a5cf6-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5cf6-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5cf6-128">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="a5cf6-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a5cf6-129">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a5cf6-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a5cf6-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5cf6-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5cf6-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a5cf6-131">See also</span></span>

- [<span data-ttu-id="a5cf6-132">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a5cf6-132">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="a5cf6-133">ICLRDebugManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a5cf6-133">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="a5cf6-134">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a5cf6-134">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
