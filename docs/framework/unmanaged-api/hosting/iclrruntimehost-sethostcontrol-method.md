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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1cf6255bfd23b38be63cd609798643f9fa1e1f93
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765769"
---
# <a name="iclrruntimehostsethostcontrol-method"></a><span data-ttu-id="50762-102">ICLRRuntimeHost::SetHostControl-Methode</span><span class="sxs-lookup"><span data-stu-id="50762-102">ICLRRuntimeHost::SetHostControl Method</span></span>
<span data-ttu-id="50762-103">Legt den Schnittstellenzeiger auf, die die common Language Runtime (CLR) verwenden können, um die die Implementierung der Hosts erhalten [IHostControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span><span class="sxs-lookup"><span data-stu-id="50762-103">Sets the interface pointer that the common language runtime (CLR) can use to get the host's implementation of [IHostControl Interface](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50762-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="50762-104">Syntax</span></span>  
  
```cpp  
HRESULT SetHostControl(  
    [in] IHostControl* pHostControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50762-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="50762-105">Parameters</span></span>  
 `pHostControl`  
 <span data-ttu-id="50762-106">[in] Einen Schnittstellenzeiger auf das die Implementierung der Hosts [IHostControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span><span class="sxs-lookup"><span data-stu-id="50762-106">[in] An interface pointer to the host's implementation of [IHostControl Interface](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="50762-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="50762-107">Return Value</span></span>  
  
|<span data-ttu-id="50762-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="50762-108">HRESULT</span></span>|<span data-ttu-id="50762-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="50762-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="50762-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="50762-110">S_OK</span></span>|<span data-ttu-id="50762-111">`SetHostControl` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="50762-111">`SetHostControl` returned successfully.</span></span>|  
|<span data-ttu-id="50762-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="50762-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="50762-113">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="50762-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="50762-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="50762-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="50762-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="50762-115">The call timed out.</span></span>|  
|<span data-ttu-id="50762-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="50762-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="50762-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="50762-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="50762-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="50762-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="50762-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="50762-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="50762-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="50762-120">E_FAIL</span></span>|<span data-ttu-id="50762-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="50762-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="50762-122">Wenn eine Methode E_FAIL zurückgegeben wird, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="50762-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="50762-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="50762-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="50762-124">E_CLR_ALREADY_STARTED</span><span class="sxs-lookup"><span data-stu-id="50762-124">E_CLR_ALREADY_STARTED</span></span>|<span data-ttu-id="50762-125">Die CLR wurde bereits initialisiert.</span><span class="sxs-lookup"><span data-stu-id="50762-125">The CLR has already been initialized.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50762-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="50762-126">Remarks</span></span>  
 <span data-ttu-id="50762-127">Rufen Sie `SetHostControl` bevor die CLR, d. h. initialisiert wird vor dem Aufruf [Methode starten](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) oder eines der [Metadatenschnittstellen](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="50762-127">You must call `SetHostControl` before the CLR is initialized, that is, before you call [Start Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) or use any of the [Metadata Interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span></span> <span data-ttu-id="50762-128">Es wird empfohlen, die Sie aufrufen `SetHostControl` sofort nach dem Aufruf [CorBindToCurrentRuntime-Funktion](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md) oder [CorBindToRuntimeEx-Funktion](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md).</span><span class="sxs-lookup"><span data-stu-id="50762-128">It is recommended that you call `SetHostControl` immediately after calling [CorBindToCurrentRuntime Function](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md) or [CorBindToRuntimeEx Function](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50762-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="50762-129">Requirements</span></span>  
 <span data-ttu-id="50762-130">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50762-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50762-131">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="50762-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="50762-132">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="50762-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="50762-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50762-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50762-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="50762-134">See also</span></span>

- [<span data-ttu-id="50762-135">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="50762-135">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [<span data-ttu-id="50762-136">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="50762-136">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
