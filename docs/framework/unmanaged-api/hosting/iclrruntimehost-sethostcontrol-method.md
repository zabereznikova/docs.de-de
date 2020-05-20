---
title: ICLRRuntimeHost::SetHostControl-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.SetHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::SetHostControl
helpviewer_keywords:
- SetHostControl method [.NET Framework hosting]
- ICLRRuntimeHost::SetHostControl method [.NET Framework hosting]
ms.assetid: 6136be87-e631-4756-81ed-74b66581bad4
topic_type:
- apiref
ms.openlocfilehash: 8d6a4e1ca934c748352b0c4f5120536a4dd24e0b
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703957"
---
# <a name="iclrruntimehostsethostcontrol-method"></a><span data-ttu-id="8ae5e-102">ICLRRuntimeHost::SetHostControl-Methode</span><span class="sxs-lookup"><span data-stu-id="8ae5e-102">ICLRRuntimeHost::SetHostControl Method</span></span>
<span data-ttu-id="8ae5e-103">Legt den Schnittstellen Zeiger fest, den der Common Language Runtime (CLR) verwenden kann, um die Implementierung der [IHostControl-Schnittstelle](ihostcontrol-interface.md)des Hosts zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="8ae5e-103">Sets the interface pointer that the common language runtime (CLR) can use to get the host's implementation of [IHostControl Interface](ihostcontrol-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ae5e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8ae5e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetHostControl(  
    [in] IHostControl* pHostControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ae5e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8ae5e-105">Parameters</span></span>  
 `pHostControl`  
 <span data-ttu-id="8ae5e-106">in Ein Schnittstellen Zeiger auf die Implementierung der [IHostControl-Schnittstelle](ihostcontrol-interface.md)des Hosts.</span><span class="sxs-lookup"><span data-stu-id="8ae5e-106">[in] An interface pointer to the host's implementation of [IHostControl Interface](ihostcontrol-interface.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8ae5e-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8ae5e-107">Return Value</span></span>  
  
|<span data-ttu-id="8ae5e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8ae5e-108">HRESULT</span></span>|<span data-ttu-id="8ae5e-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8ae5e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8ae5e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8ae5e-110">S_OK</span></span>|<span data-ttu-id="8ae5e-111">`SetHostControl`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8ae5e-111">`SetHostControl` returned successfully.</span></span>|  
|<span data-ttu-id="8ae5e-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8ae5e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8ae5e-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="8ae5e-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8ae5e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8ae5e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8ae5e-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="8ae5e-115">The call timed out.</span></span>|  
|<span data-ttu-id="8ae5e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8ae5e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8ae5e-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="8ae5e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8ae5e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8ae5e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8ae5e-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="8ae5e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8ae5e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8ae5e-120">E_FAIL</span></span>|<span data-ttu-id="8ae5e-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8ae5e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8ae5e-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="8ae5e-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8ae5e-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="8ae5e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8ae5e-124">E_CLR_ALREADY_STARTED</span><span class="sxs-lookup"><span data-stu-id="8ae5e-124">E_CLR_ALREADY_STARTED</span></span>|<span data-ttu-id="8ae5e-125">Die CLR wurde bereits initialisiert.</span><span class="sxs-lookup"><span data-stu-id="8ae5e-125">The CLR has already been initialized.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ae5e-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8ae5e-126">Remarks</span></span>  
 <span data-ttu-id="8ae5e-127">Sie müssen `SetHostControl` vor dem Initialisieren der CLR aufzurufen, d. h. bevor Sie die [Start-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) aufruft oder eine der [Metadatenschnittstellen](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)verwenden.</span><span class="sxs-lookup"><span data-stu-id="8ae5e-127">You must call `SetHostControl` before the CLR is initialized, that is, before you call [Start Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) or use any of the [Metadata Interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span></span> <span data-ttu-id="8ae5e-128">Es wird empfohlen, dass Sie `SetHostControl` sofort nach dem Aufrufen der [CorBindToCurrentRuntime-Funktion](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md) oder der [CorBindToRuntimeEx-Funktion](corbindtoruntimeex-function.md)aufrufen.</span><span class="sxs-lookup"><span data-stu-id="8ae5e-128">It is recommended that you call `SetHostControl` immediately after calling [CorBindToCurrentRuntime Function](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md) or [CorBindToRuntimeEx Function](corbindtoruntimeex-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ae5e-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8ae5e-129">Requirements</span></span>  
 <span data-ttu-id="8ae5e-130">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ae5e-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ae5e-131">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="8ae5e-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8ae5e-132">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8ae5e-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8ae5e-133">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ae5e-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ae5e-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8ae5e-134">See also</span></span>

- [<span data-ttu-id="8ae5e-135">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8ae5e-135">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
- [<span data-ttu-id="8ae5e-136">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8ae5e-136">IHostControl Interface</span></span>](ihostcontrol-interface.md)
