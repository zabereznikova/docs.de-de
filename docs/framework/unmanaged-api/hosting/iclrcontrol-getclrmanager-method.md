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
ms.openlocfilehash: d18b3a5c06ac0d3a86f7823f3b140c76c6c9a746
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728354"
---
# <a name="iclrcontrolgetclrmanager-method"></a><span data-ttu-id="58d81-102">ICLRControl::GetCLRManager-Methode</span><span class="sxs-lookup"><span data-stu-id="58d81-102">ICLRControl::GetCLRManager Method</span></span>

<span data-ttu-id="58d81-103">Ruft einen Schnittstellen Zeiger auf eine Instanz eines der Manager-Typen ab, die der Host zum Konfigurieren des Common Language Runtime (CLR) verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="58d81-103">Gets an interface pointer to an instance of any of the manager types the host can use to configure the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58d81-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="58d81-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCLRManager (  
    [in]  REFIID  riid,  
    [out] void  **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58d81-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="58d81-105">Parameters</span></span>  

 `riid`  
 <span data-ttu-id="58d81-106">in Der `IID` des Vorgesetzten Typs, der zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="58d81-106">[in] The `IID` of the manager type to return.</span></span> <span data-ttu-id="58d81-107">Die folgenden `IID` Werte werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="58d81-107">The following `IID` values are supported.</span></span>  
  
- <span data-ttu-id="58d81-108">IID_ICLRDebugManager: gibt an, dass den `ppObject` Typ [ICLRDebugManager](iclrdebugmanager-interface.md)aufweisen soll.</span><span class="sxs-lookup"><span data-stu-id="58d81-108">IID_ICLRDebugManager: Specifies that `ppObject` will be of type [ICLRDebugManager](iclrdebugmanager-interface.md).</span></span>  
  
- <span data-ttu-id="58d81-109">IID_ICLRErrorReportingManager: gibt an, dass den `ppObject` Typ [ICLRErrorReportingManager](iclrerrorreportingmanager-interface.md)aufweisen soll.</span><span class="sxs-lookup"><span data-stu-id="58d81-109">IID_ICLRErrorReportingManager: Specifies that `ppObject` will be of type [ICLRErrorReportingManager](iclrerrorreportingmanager-interface.md).</span></span>  
  
- <span data-ttu-id="58d81-110">IID_ICLRGCManager: gibt an, dass den `ppObject` Typ [ICLRGCManager](iclrgcmanager-interface.md)aufweisen soll.</span><span class="sxs-lookup"><span data-stu-id="58d81-110">IID_ICLRGCManager: Specifies that `ppObject` will be of type [ICLRGCManager](iclrgcmanager-interface.md).</span></span>  
  
- <span data-ttu-id="58d81-111">IID_ICLRHostProtectionManager: gibt an, dass den `ppObject` Typ [iclrhostschutzmanager](iclrhostprotectionmanager-interface.md)aufweisen soll.</span><span class="sxs-lookup"><span data-stu-id="58d81-111">IID_ICLRHostProtectionManager: Specifies that `ppObject` will be of type [ICLRHostProtectionManager](iclrhostprotectionmanager-interface.md).</span></span>  
  
- <span data-ttu-id="58d81-112">IID_ICLROnEventManager: gibt an, dass den `ppObject` Typ [ICLROnEventManager](iclroneventmanager-interface.md)aufweisen soll.</span><span class="sxs-lookup"><span data-stu-id="58d81-112">IID_ICLROnEventManager: Specifies that `ppObject` will be of type [ICLROnEventManager](iclroneventmanager-interface.md).</span></span>  
  
- <span data-ttu-id="58d81-113">IID_ICLRPolicyManager: gibt an, dass den `ppObject` Typ [ICLRPolicyManager](iclrpolicymanager-interface.md)aufweisen soll.</span><span class="sxs-lookup"><span data-stu-id="58d81-113">IID_ICLRPolicyManager: Specifies that `ppObject` will be of type [ICLRPolicyManager](iclrpolicymanager-interface.md).</span></span>  
  
- <span data-ttu-id="58d81-114">IID_ICLRTaskManager: gibt an, dass den `ppObject` Typ [ICLRTaskManager](iclrtaskmanager-interface.md)aufweisen soll.</span><span class="sxs-lookup"><span data-stu-id="58d81-114">IID_ICLRTaskManager: Specifies that `ppObject` will be of type [ICLRTaskManager](iclrtaskmanager-interface.md).</span></span>  
  
 `ppObject`  
 <span data-ttu-id="58d81-115">vorgenommen Ein Schnittstellen Zeiger auf den angeforderten Manager oder NULL, wenn ein ungültiger Manager-Typ angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="58d81-115">[out] An interface pointer to the requested manager, or null, if an invalid manager type was requested.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="58d81-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="58d81-116">Return Value</span></span>  
  
|<span data-ttu-id="58d81-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="58d81-117">HRESULT</span></span>|<span data-ttu-id="58d81-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="58d81-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="58d81-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="58d81-119">S_OK</span></span>|<span data-ttu-id="58d81-120">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="58d81-120">The method returned successfully.</span></span>|  
|<span data-ttu-id="58d81-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="58d81-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="58d81-122">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="58d81-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="58d81-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="58d81-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="58d81-124">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="58d81-124">The call timed out.</span></span>|  
|<span data-ttu-id="58d81-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="58d81-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="58d81-126">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="58d81-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="58d81-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="58d81-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="58d81-128">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="58d81-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="58d81-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="58d81-129">E_FAIL</span></span>|<span data-ttu-id="58d81-130">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="58d81-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="58d81-131">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="58d81-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="58d81-132">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="58d81-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="58d81-133">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="58d81-133">E_NOINTERFACE</span></span>|<span data-ttu-id="58d81-134">Der Schnittstellentyp wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="58d81-134">The interface type is not supported.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="58d81-135">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="58d81-135">Requirements</span></span>  

 <span data-ttu-id="58d81-136">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58d81-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58d81-137">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="58d81-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="58d81-138">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="58d81-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="58d81-139">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58d81-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58d81-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="58d81-140">See also</span></span>

- [<span data-ttu-id="58d81-141">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="58d81-141">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="58d81-142">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="58d81-142">IHostControl Interface</span></span>](ihostcontrol-interface.md)
