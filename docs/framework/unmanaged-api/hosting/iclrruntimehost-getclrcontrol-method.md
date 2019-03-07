---
title: ICLRRuntimeHost::GetCLRControl-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.GetCLRControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::GetCLRControl
helpviewer_keywords:
- ICLRRuntimeHost::GetCLRControl method [.NET Framework hosting]
- GetCLRControl method [.NET Framework hosting]
ms.assetid: e47e3655-efd5-4572-a1dc-50c69bf2a468
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 06c3b060aaeb73b2d834c053cf47f0384ca4a38f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57488461"
---
# <a name="iclrruntimehostgetclrcontrol-method"></a><span data-ttu-id="29e7e-102">ICLRRuntimeHost::GetCLRControl-Methode</span><span class="sxs-lookup"><span data-stu-id="29e7e-102">ICLRRuntimeHost::GetCLRControl Method</span></span>
<span data-ttu-id="29e7e-103">Ruft einen Schnittstellenzeiger vom Typ [ICLRControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) Hosts verwenden können, um Aspekte der common Language Runtime (CLR) anpassen.</span><span class="sxs-lookup"><span data-stu-id="29e7e-103">Gets an interface pointer of type [ICLRControl Interface](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29e7e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="29e7e-104">Syntax</span></span>  
  
```  
HRESULT GetCLRControl(  
    [out] ICLRControl** pCLRControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29e7e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="29e7e-105">Parameters</span></span>  
 `pCLRControl`  
 <span data-ttu-id="29e7e-106">[out] Einen Schnittstellenzeiger vom Typ [ICLRControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) , der Hosts so konfigurieren Sie zusätzliche Aspekte der CLR ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="29e7e-106">[out] An interface pointer of type [ICLRControl Interface](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that enables hosts to configure additional aspects of the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="29e7e-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="29e7e-107">Return Value</span></span>  
  
|<span data-ttu-id="29e7e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="29e7e-108">HRESULT</span></span>|<span data-ttu-id="29e7e-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="29e7e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="29e7e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="29e7e-110">S_OK</span></span>|<span data-ttu-id="29e7e-111">`GetCLRControl` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="29e7e-111">`GetCLRControl` returned successfully.</span></span>|  
|<span data-ttu-id="29e7e-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="29e7e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="29e7e-113">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="29e7e-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="29e7e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="29e7e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="29e7e-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="29e7e-115">The call timed out.</span></span>|  
|<span data-ttu-id="29e7e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="29e7e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="29e7e-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="29e7e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="29e7e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="29e7e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="29e7e-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="29e7e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="29e7e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="29e7e-120">E_FAIL</span></span>|<span data-ttu-id="29e7e-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="29e7e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="29e7e-122">Wenn eine Methode E_FAIL zurückgegeben wird, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="29e7e-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="29e7e-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="29e7e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="29e7e-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="29e7e-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="29e7e-125">Die CLR wurde bereits gestartet.</span><span class="sxs-lookup"><span data-stu-id="29e7e-125">The CLR has already started.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29e7e-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="29e7e-126">Remarks</span></span>  
 <span data-ttu-id="29e7e-127">`ICLRControl` Stellt die [GetCLRManager-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) -Methode, die den Host um einen Schnittstellenzeiger auf einen der Managertypen erhalten kann.</span><span class="sxs-lookup"><span data-stu-id="29e7e-127">`ICLRControl` provides the [GetCLRManager Method](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method, which enables the host to get an interface pointer to one of the manager types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29e7e-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="29e7e-128">Requirements</span></span>  
 <span data-ttu-id="29e7e-129">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29e7e-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29e7e-130">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="29e7e-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="29e7e-131">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="29e7e-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="29e7e-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29e7e-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29e7e-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="29e7e-133">See also</span></span>
- [<span data-ttu-id="29e7e-134">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="29e7e-134">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="29e7e-135">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="29e7e-135">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
