---
title: ICLRPolicyManager::SetUnhandledExceptionPolicy-Methode
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetUnhandledExceptionPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetUnhandledExceptionPolicy
helpviewer_keywords:
- ICLRPolicyManager::SetUnhandledExceptionPolicy method [.NET Framework hosting]
- SetUnhandledExceptionPolicy method [.NET Framework hosting]
ms.assetid: 5268480e-280a-4931-b7a3-dc3ffdf7f78f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f988084310b920907bb7f212e7d40ca0d1c91db
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59197515"
---
# <a name="iclrpolicymanagersetunhandledexceptionpolicy-method"></a><span data-ttu-id="95225-102">ICLRPolicyManager::SetUnhandledExceptionPolicy-Methode</span><span class="sxs-lookup"><span data-stu-id="95225-102">ICLRPolicyManager::SetUnhandledExceptionPolicy Method</span></span>
<span data-ttu-id="95225-103">Gibt das Verhalten der common Language Runtime (CLR) an, wenn eine nicht behandelte Ausnahme auftritt.</span><span class="sxs-lookup"><span data-stu-id="95225-103">Specifies the behavior of the common language runtime (CLR) when an unhandled exception occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95225-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="95225-104">Syntax</span></span>  
  
```  
HRESULT SetUnhandledExceptionPolicy (  
    [in] EClrUnhandledExceptionPolicy policy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95225-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="95225-105">Parameters</span></span>  
 `policy`  
 <span data-ttu-id="95225-106">[in] Eines der [EClrUnhandledException](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md) Werte, der angibt, ob das Verhalten von der CLR oder den Host festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="95225-106">[in] One of the [EClrUnhandledException](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md) values, indicating whether the behavior is set by the CLR or the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="95225-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="95225-107">Return Value</span></span>  
  
|<span data-ttu-id="95225-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="95225-108">HRESULT</span></span>|<span data-ttu-id="95225-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="95225-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="95225-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="95225-110">S_OK</span></span>|<span data-ttu-id="95225-111">`SetUnhandledExceptionPolicy` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="95225-111">`SetUnhandledExceptionPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="95225-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="95225-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="95225-113">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="95225-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="95225-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="95225-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="95225-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="95225-115">The call timed out.</span></span>|  
|<span data-ttu-id="95225-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="95225-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="95225-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="95225-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="95225-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="95225-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="95225-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="95225-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="95225-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="95225-120">E_FAIL</span></span>|<span data-ttu-id="95225-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="95225-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="95225-122">Wenn eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="95225-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="95225-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="95225-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95225-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="95225-124">Remarks</span></span>  
 <span data-ttu-id="95225-125">In der Standardeinstellung die CLR ist der letzte Handler für alle nicht behandelten Ausnahmen, und das Standardverhalten ist, um den Prozess abbrechen.</span><span class="sxs-lookup"><span data-stu-id="95225-125">By default, the CLR is the final handler for all unhandled exceptions, and its default behavior is to tear down the process.</span></span> <span data-ttu-id="95225-126">Der Host kann dieses Verhalten ändern, durch Festlegen der `policy` eHostDeterminedPolicy Wert.</span><span class="sxs-lookup"><span data-stu-id="95225-126">The host can change this behavior by setting the `policy` value to eHostDeterminedPolicy.</span></span> <span data-ttu-id="95225-127">Dieser Wert kann den Host einen eigenen Standardverhalten implementieren wie in früheren Versionen der CLR.</span><span class="sxs-lookup"><span data-stu-id="95225-127">This value allows the host to implement its own default behavior, as with earlier versions of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95225-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="95225-128">Requirements</span></span>  
 <span data-ttu-id="95225-129">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95225-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95225-130">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="95225-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="95225-131">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="95225-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="95225-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95225-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95225-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="95225-133">See also</span></span>

- [<span data-ttu-id="95225-134">EClrUnhandledException-Enumeration</span><span class="sxs-lookup"><span data-stu-id="95225-134">EClrUnhandledException Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md)
- [<span data-ttu-id="95225-135">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="95225-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="95225-136">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="95225-136">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="95225-137">IHostPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="95225-137">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
