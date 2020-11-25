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
ms.openlocfilehash: 71e11d7db3bd679e7972fb2f6ce098edc3399885
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731019"
---
# <a name="iclrdebugmanagerisdebuggerattached-method"></a><span data-ttu-id="31948-102">ICLRDebugManager::IsDebuggerAttached-Methode</span><span class="sxs-lookup"><span data-stu-id="31948-102">ICLRDebugManager::IsDebuggerAttached Method</span></span>

<span data-ttu-id="31948-103">Ruft einen Wert ab, der angibt, ob ein Debugger an den Prozess angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="31948-103">Gets a value that indicates whether a debugger is attached to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31948-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="31948-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31948-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="31948-105">Parameters</span></span>  

 `pbAttached`  
 <span data-ttu-id="31948-106">[out] `true` , wenn ein Debugger an den Prozess angefügt ist. andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="31948-106">[out] `true` if a debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="31948-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="31948-107">Return Value</span></span>  
  
|<span data-ttu-id="31948-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="31948-108">HRESULT</span></span>|<span data-ttu-id="31948-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="31948-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="31948-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="31948-110">S_OK</span></span>|<span data-ttu-id="31948-111">`IsDebuggerAttached` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="31948-111">`IsDebuggerAttached` returned successfully.</span></span>|  
|<span data-ttu-id="31948-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="31948-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="31948-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="31948-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="31948-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="31948-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="31948-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="31948-115">The call timed out.</span></span>|  
|<span data-ttu-id="31948-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="31948-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="31948-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="31948-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="31948-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="31948-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="31948-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="31948-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="31948-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="31948-120">E_FAIL</span></span>|<span data-ttu-id="31948-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="31948-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="31948-122">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="31948-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="31948-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="31948-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="31948-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="31948-124">Remarks</span></span>  

 <span data-ttu-id="31948-125">`IsDebuggerAttached` ermöglicht dem Host, die CLR abzufragen, um zu bestimmen, ob ein Debugger an den Prozess angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="31948-125">`IsDebuggerAttached` allows the host to query the CLR to determine whether a debugger is attached to the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31948-126">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="31948-126">Requirements</span></span>  

 <span data-ttu-id="31948-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31948-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31948-128">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="31948-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="31948-129">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="31948-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="31948-130">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31948-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31948-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="31948-131">See also</span></span>

- [<span data-ttu-id="31948-132">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="31948-132">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="31948-133">ICLRDebugManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="31948-133">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
- [<span data-ttu-id="31948-134">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="31948-134">IHostControl Interface</span></span>](ihostcontrol-interface.md)
