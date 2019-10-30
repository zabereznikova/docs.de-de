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
ms.openlocfilehash: 478e07f18d40043de4e800c36647ac4a32499635
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120432"
---
# <a name="iclrruntimehostgetclrcontrol-method"></a><span data-ttu-id="48dac-102">ICLRRuntimeHost::GetCLRControl-Methode</span><span class="sxs-lookup"><span data-stu-id="48dac-102">ICLRRuntimeHost::GetCLRControl Method</span></span>
<span data-ttu-id="48dac-103">Ruft einen Schnittstellen Zeiger vom Typ [ICLRControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) ab, mit der Hosts Aspekte des Common Language Runtime (CLR) anpassen können.</span><span class="sxs-lookup"><span data-stu-id="48dac-103">Gets an interface pointer of type [ICLRControl Interface](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48dac-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="48dac-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCLRControl(  
    [out] ICLRControl** pCLRControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48dac-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="48dac-105">Parameters</span></span>  
 `pCLRControl`  
 <span data-ttu-id="48dac-106">vorgenommen Ein Schnittstellen Zeiger vom Typ [ICLRControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) , mit der Hosts weitere Aspekte der CLR konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="48dac-106">[out] An interface pointer of type [ICLRControl Interface](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that enables hosts to configure additional aspects of the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="48dac-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="48dac-107">Return Value</span></span>  
  
|<span data-ttu-id="48dac-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="48dac-108">HRESULT</span></span>|<span data-ttu-id="48dac-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="48dac-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="48dac-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="48dac-110">S_OK</span></span>|<span data-ttu-id="48dac-111">`GetCLRControl` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="48dac-111">`GetCLRControl` returned successfully.</span></span>|  
|<span data-ttu-id="48dac-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="48dac-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="48dac-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="48dac-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="48dac-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="48dac-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="48dac-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="48dac-115">The call timed out.</span></span>|  
|<span data-ttu-id="48dac-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="48dac-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="48dac-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="48dac-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="48dac-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="48dac-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="48dac-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="48dac-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="48dac-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="48dac-120">E_FAIL</span></span>|<span data-ttu-id="48dac-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="48dac-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="48dac-122">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="48dac-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="48dac-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="48dac-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="48dac-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="48dac-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="48dac-125">Die CLR wurde bereits gestartet.</span><span class="sxs-lookup"><span data-stu-id="48dac-125">The CLR has already started.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48dac-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="48dac-126">Remarks</span></span>  
 <span data-ttu-id="48dac-127">`ICLRControl` stellt die [Methode GetCLRManager-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) bereit, die es dem Host ermöglicht, einen Schnittstellen Zeiger auf einen der Manager-Typen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="48dac-127">`ICLRControl` provides the [GetCLRManager Method](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method, which enables the host to get an interface pointer to one of the manager types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48dac-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="48dac-128">Requirements</span></span>  
 <span data-ttu-id="48dac-129">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48dac-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48dac-130">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="48dac-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="48dac-131">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="48dac-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="48dac-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48dac-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48dac-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="48dac-133">See also</span></span>

- [<span data-ttu-id="48dac-134">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="48dac-134">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="48dac-135">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="48dac-135">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
