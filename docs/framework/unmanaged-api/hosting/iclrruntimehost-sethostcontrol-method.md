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
ms.openlocfilehash: 46cfaa5870d7bbc7edcbe438ddf57fe5f70ad938
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434964"
---
# <a name="iclrruntimehostsethostcontrol-method"></a><span data-ttu-id="47ffd-102">ICLRRuntimeHost::SetHostControl-Methode</span><span class="sxs-lookup"><span data-stu-id="47ffd-102">ICLRRuntimeHost::SetHostControl Method</span></span>
<span data-ttu-id="47ffd-103">Legt den Schnittstellenzeiger auf, die die common Language Runtime (CLR) verwenden können, die Host-Implementierung der abzurufenden [IHostControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span><span class="sxs-lookup"><span data-stu-id="47ffd-103">Sets the interface pointer that the common language runtime (CLR) can use to get the host's implementation of [IHostControl Interface](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47ffd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="47ffd-104">Syntax</span></span>  
  
```  
HRESULT SetHostControl(  
    [in] IHostControl* pHostControl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="47ffd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="47ffd-105">Parameters</span></span>  
 `pHostControl`  
 <span data-ttu-id="47ffd-106">[in] Einen Schnittstellenzeiger auf dem Host-Implementierung von [IHostControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span><span class="sxs-lookup"><span data-stu-id="47ffd-106">[in] An interface pointer to the host's implementation of [IHostControl Interface](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="47ffd-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="47ffd-107">Return Value</span></span>  
  
|<span data-ttu-id="47ffd-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="47ffd-108">HRESULT</span></span>|<span data-ttu-id="47ffd-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="47ffd-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="47ffd-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="47ffd-110">S_OK</span></span>|<span data-ttu-id="47ffd-111">`SetHostControl` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="47ffd-111">`SetHostControl` returned successfully.</span></span>|  
|<span data-ttu-id="47ffd-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="47ffd-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="47ffd-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="47ffd-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="47ffd-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="47ffd-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="47ffd-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="47ffd-115">The call timed out.</span></span>|  
|<span data-ttu-id="47ffd-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="47ffd-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="47ffd-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="47ffd-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="47ffd-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="47ffd-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="47ffd-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="47ffd-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="47ffd-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="47ffd-120">E_FAIL</span></span>|<span data-ttu-id="47ffd-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="47ffd-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="47ffd-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="47ffd-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="47ffd-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="47ffd-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="47ffd-124">E_CLR_ALREADY_STARTED</span><span class="sxs-lookup"><span data-stu-id="47ffd-124">E_CLR_ALREADY_STARTED</span></span>|<span data-ttu-id="47ffd-125">Die CLR wurde bereits initialisiert.</span><span class="sxs-lookup"><span data-stu-id="47ffd-125">The CLR has already been initialized.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="47ffd-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="47ffd-126">Remarks</span></span>  
 <span data-ttu-id="47ffd-127">Rufen Sie `SetHostControl` , bevor die CLR, d. h. initialisiert wird vor dem Aufruf [Start-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) , oder verwenden Sie keines der [Metadatenschnittstellen](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="47ffd-127">You must call `SetHostControl` before the CLR is initialized, that is, before you call [Start Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) or use any of the [Metadata Interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span></span> <span data-ttu-id="47ffd-128">Es wird empfohlen, Sie rufen `SetHostControl` sofort nach dem Aufruf [CorBindToCurrentRuntime-Funktion](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md) oder [CorBindToRuntimeEx-Funktion](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md).</span><span class="sxs-lookup"><span data-stu-id="47ffd-128">It is recommended that you call `SetHostControl` immediately after calling [CorBindToCurrentRuntime Function](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md) or [CorBindToRuntimeEx Function](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47ffd-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="47ffd-129">Requirements</span></span>  
 <span data-ttu-id="47ffd-130">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47ffd-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47ffd-131">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="47ffd-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="47ffd-132">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="47ffd-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="47ffd-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47ffd-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47ffd-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="47ffd-134">See Also</span></span>  
 [<span data-ttu-id="47ffd-135">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="47ffd-135">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 [<span data-ttu-id="47ffd-136">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="47ffd-136">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
