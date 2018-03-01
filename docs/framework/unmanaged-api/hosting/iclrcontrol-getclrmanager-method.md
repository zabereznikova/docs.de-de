---
title: ICLRControl::GetCLRManager-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRControl.GetCLRManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl::GetCLRManager
helpviewer_keywords:
- GetCLRManager method [.NET Framework hosting]
- ICLRControl::GetCLRManager method [.NET Framework hosting]
ms.assetid: 8a11bfa4-cbb0-4082-82b5-f9fba66c93f5
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 197a3818de8d0b17331a9f9ac422ecaabb230a50
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrcontrolgetclrmanager-method"></a><span data-ttu-id="42840-102">ICLRControl::GetCLRManager-Methode</span><span class="sxs-lookup"><span data-stu-id="42840-102">ICLRControl::GetCLRManager Method</span></span>
<span data-ttu-id="42840-103">Ruft einen Schnittstellenzeiger zu einer Instanz von den Manager-Typen, die der Host so konfigurieren Sie die common Language Runtime (CLR) verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="42840-103">Gets an interface pointer to an instance of any of the manager types the host can use to configure the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42840-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="42840-104">Syntax</span></span>  
  
```  
HRESULT GetCLRManager (  
    [in]  REFIID  riid,  
    [out] void  **ppObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="42840-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="42840-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="42840-106">[in] Die `IID` von den Manager-Typ zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="42840-106">[in] The `IID` of the manager type to return.</span></span> <span data-ttu-id="42840-107">Die folgenden `IID` Werte werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="42840-107">The following `IID` values are supported.</span></span>  
  
-   <span data-ttu-id="42840-108">IID_ICLRDebugManager: Gibt an, dass `ppObject` vom Typ [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="42840-108">IID_ICLRDebugManager: Specifies that `ppObject` will be of type [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md).</span></span>  
  
-   <span data-ttu-id="42840-109">IID_ICLRErrorReportingManager: Gibt an, dass `ppObject` vom Typ [ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="42840-109">IID_ICLRErrorReportingManager: Specifies that `ppObject` will be of type [ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md).</span></span>  
  
-   <span data-ttu-id="42840-110">IID_ICLRGCManager: Gibt an, dass `ppObject` vom Typ [ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="42840-110">IID_ICLRGCManager: Specifies that `ppObject` will be of type [ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span></span>  
  
-   <span data-ttu-id="42840-111">IID_ICLRHostProtectionManager: Gibt an, dass `ppObject` vom Typ [ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="42840-111">IID_ICLRHostProtectionManager: Specifies that `ppObject` will be of type [ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md).</span></span>  
  
-   <span data-ttu-id="42840-112">IID_ICLROnEventManager: Gibt an, dass `ppObject` vom Typ [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="42840-112">IID_ICLROnEventManager: Specifies that `ppObject` will be of type [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md).</span></span>  
  
-   <span data-ttu-id="42840-113">IID_ICLRPolicyManager: Gibt an, dass `ppObject` vom Typ [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="42840-113">IID_ICLRPolicyManager: Specifies that `ppObject` will be of type [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).</span></span>  
  
-   <span data-ttu-id="42840-114">IID_ICLRTaskManager: Gibt an, die `ppObject` vom Typ [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="42840-114">IID_ICLRTaskManager: speciries that `ppObject` will be of type [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md).</span></span>  
  
 `ppObject`  
 <span data-ttu-id="42840-115">[out] Ein Schnittstellenzeiger auf den angeforderten Manager bzw. Null, wenn ein ungültiger Managertyp angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="42840-115">[out] An interface pointer to the requested manager, or null, if an invalid manager type was requested.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="42840-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="42840-116">Return Value</span></span>  
  
|<span data-ttu-id="42840-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="42840-117">HRESULT</span></span>|<span data-ttu-id="42840-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="42840-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="42840-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="42840-119">S_OK</span></span>|<span data-ttu-id="42840-120">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="42840-120">The method returned successfully.</span></span>|  
|<span data-ttu-id="42840-121">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="42840-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="42840-122">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="42840-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="42840-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="42840-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="42840-124">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="42840-124">The call timed out.</span></span>|  
|<span data-ttu-id="42840-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="42840-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="42840-126">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="42840-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="42840-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="42840-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="42840-128">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="42840-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="42840-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="42840-129">E_FAIL</span></span>|<span data-ttu-id="42840-130">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="42840-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="42840-131">Nachdem eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="42840-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="42840-132">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="42840-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="42840-133">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="42840-133">E_NOINTERFACE</span></span>|<span data-ttu-id="42840-134">Der Schnittstellentyp wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="42840-134">The interface type is not supported.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="42840-135">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="42840-135">Requirements</span></span>  
 <span data-ttu-id="42840-136">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42840-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42840-137">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="42840-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="42840-138">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="42840-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="42840-139">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42840-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42840-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="42840-140">See Also</span></span>  
 [<span data-ttu-id="42840-141">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="42840-141">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="42840-142">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="42840-142">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
