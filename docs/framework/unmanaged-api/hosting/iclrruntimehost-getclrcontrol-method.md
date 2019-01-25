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
ms.openlocfilehash: 8f426bac735c780d63b75eeaf49151651fd2fa65
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54692898"
---
# <a name="iclrruntimehostgetclrcontrol-method"></a><span data-ttu-id="d093f-102">ICLRRuntimeHost::GetCLRControl-Methode</span><span class="sxs-lookup"><span data-stu-id="d093f-102">ICLRRuntimeHost::GetCLRControl Method</span></span>
<span data-ttu-id="d093f-103">Ruft einen Schnittstellenzeiger vom Typ [ICLRControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) Hosts verwenden können, um Aspekte der common Language Runtime (CLR) anpassen.</span><span class="sxs-lookup"><span data-stu-id="d093f-103">Gets an interface pointer of type [ICLRControl Interface](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d093f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d093f-104">Syntax</span></span>  
  
```  
HRESULT GetCLRControl(  
    [out] ICLRControl** pCLRControl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d093f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d093f-105">Parameters</span></span>  
 `pCLRControl`  
 <span data-ttu-id="d093f-106">[out] Einen Schnittstellenzeiger vom Typ [ICLRControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) , der Hosts so konfigurieren Sie zusätzliche Aspekte der CLR ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="d093f-106">[out] An interface pointer of type [ICLRControl Interface](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that enables hosts to configure additional aspects of the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d093f-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d093f-107">Return Value</span></span>  
  
|<span data-ttu-id="d093f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d093f-108">HRESULT</span></span>|<span data-ttu-id="d093f-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d093f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d093f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d093f-110">S_OK</span></span>|<span data-ttu-id="d093f-111">`GetCLRControl` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d093f-111">`GetCLRControl` returned successfully.</span></span>|  
|<span data-ttu-id="d093f-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d093f-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d093f-113">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="d093f-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d093f-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d093f-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d093f-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="d093f-115">The call timed out.</span></span>|  
|<span data-ttu-id="d093f-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d093f-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d093f-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="d093f-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d093f-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d093f-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d093f-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="d093f-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d093f-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d093f-120">E_FAIL</span></span>|<span data-ttu-id="d093f-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="d093f-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d093f-122">Wenn eine Methode E_FAIL zurückgegeben wird, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d093f-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d093f-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="d093f-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d093f-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="d093f-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="d093f-125">Die CLR wurde bereits gestartet.</span><span class="sxs-lookup"><span data-stu-id="d093f-125">The CLR has already started.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d093f-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d093f-126">Remarks</span></span>  
 <span data-ttu-id="d093f-127">`ICLRControl` Stellt die [GetCLRManager-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) -Methode, die den Host um einen Schnittstellenzeiger auf einen der Managertypen erhalten kann.</span><span class="sxs-lookup"><span data-stu-id="d093f-127">`ICLRControl` provides the [GetCLRManager Method](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method, which enables the host to get an interface pointer to one of the manager types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d093f-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d093f-128">Requirements</span></span>  
 <span data-ttu-id="d093f-129">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d093f-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d093f-130">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d093f-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d093f-131">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d093f-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d093f-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d093f-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d093f-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d093f-133">See also</span></span>
- [<span data-ttu-id="d093f-134">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d093f-134">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="d093f-135">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d093f-135">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
