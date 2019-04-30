---
title: ICLRControl::GetCLRManager-Methode
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 09079c8847b7cb995d97a4577d03982602bbadfa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61969896"
---
# <a name="iclrcontrolgetclrmanager-method"></a><span data-ttu-id="670d8-102">ICLRControl::GetCLRManager-Methode</span><span class="sxs-lookup"><span data-stu-id="670d8-102">ICLRControl::GetCLRManager Method</span></span>
<span data-ttu-id="670d8-103">Ruft einen Schnittstellenzeiger auf eine Instanz eines der Managertypen, mit denen des Hosts so konfigurieren Sie die common Language Runtime (CLR) ab.</span><span class="sxs-lookup"><span data-stu-id="670d8-103">Gets an interface pointer to an instance of any of the manager types the host can use to configure the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="670d8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="670d8-104">Syntax</span></span>  
  
```  
HRESULT GetCLRManager (  
    [in]  REFIID  riid,  
    [out] void  **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="670d8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="670d8-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="670d8-106">[in] Die `IID` die Manager-Typs zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="670d8-106">[in] The `IID` of the manager type to return.</span></span> <span data-ttu-id="670d8-107">Die folgenden `IID` Werte werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="670d8-107">The following `IID` values are supported.</span></span>  
  
- <span data-ttu-id="670d8-108">IID_ICLRDebugManager: Gibt an, dass `ppObject` Typ [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="670d8-108">IID_ICLRDebugManager: Specifies that `ppObject` will be of type [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md).</span></span>  
  
- <span data-ttu-id="670d8-109">IID_ICLRErrorReportingManager: Gibt an, dass `ppObject` Typ [ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="670d8-109">IID_ICLRErrorReportingManager: Specifies that `ppObject` will be of type [ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md).</span></span>  
  
- <span data-ttu-id="670d8-110">IID_ICLRGCManager: Gibt an, dass `ppObject` Typ [ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="670d8-110">IID_ICLRGCManager: Specifies that `ppObject` will be of type [ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span></span>  
  
- <span data-ttu-id="670d8-111">IID_ICLRHostProtectionManager: Gibt an, dass `ppObject` Typ [ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="670d8-111">IID_ICLRHostProtectionManager: Specifies that `ppObject` will be of type [ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md).</span></span>  
  
- <span data-ttu-id="670d8-112">IID_ICLROnEventManager: Gibt an, dass `ppObject` Typ [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="670d8-112">IID_ICLROnEventManager: Specifies that `ppObject` will be of type [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md).</span></span>  
  
- <span data-ttu-id="670d8-113">IID_ICLRPolicyManager: Gibt an, dass `ppObject` Typ [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="670d8-113">IID_ICLRPolicyManager: Specifies that `ppObject` will be of type [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).</span></span>  
  
- <span data-ttu-id="670d8-114">IID_ICLRTaskManager: Gibt an, dass `ppObject` Typ [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="670d8-114">IID_ICLRTaskManager: Specifies that `ppObject` will be of type [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md).</span></span>  
  
 `ppObject`  
 <span data-ttu-id="670d8-115">[out] Einen Schnittstellenzeiger auf das angeforderte Manager bzw. Null, wenn ein ungültiger Managertyp angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="670d8-115">[out] An interface pointer to the requested manager, or null, if an invalid manager type was requested.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="670d8-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="670d8-116">Return Value</span></span>  
  
|<span data-ttu-id="670d8-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="670d8-117">HRESULT</span></span>|<span data-ttu-id="670d8-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="670d8-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="670d8-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="670d8-119">S_OK</span></span>|<span data-ttu-id="670d8-120">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="670d8-120">The method returned successfully.</span></span>|  
|<span data-ttu-id="670d8-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="670d8-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="670d8-122">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="670d8-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="670d8-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="670d8-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="670d8-124">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="670d8-124">The call timed out.</span></span>|  
|<span data-ttu-id="670d8-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="670d8-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="670d8-126">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="670d8-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="670d8-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="670d8-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="670d8-128">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="670d8-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="670d8-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="670d8-129">E_FAIL</span></span>|<span data-ttu-id="670d8-130">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="670d8-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="670d8-131">Wenn eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="670d8-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="670d8-132">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="670d8-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="670d8-133">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="670d8-133">E_NOINTERFACE</span></span>|<span data-ttu-id="670d8-134">Der Schnittstellentyp wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="670d8-134">The interface type is not supported.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="670d8-135">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="670d8-135">Requirements</span></span>  
 <span data-ttu-id="670d8-136">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="670d8-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="670d8-137">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="670d8-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="670d8-138">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="670d8-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="670d8-139">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="670d8-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="670d8-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="670d8-140">See also</span></span>

- [<span data-ttu-id="670d8-141">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="670d8-141">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="670d8-142">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="670d8-142">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
