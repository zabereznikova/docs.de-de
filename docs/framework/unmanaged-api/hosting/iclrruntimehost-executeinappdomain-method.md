---
title: ICLRRuntimeHost::ExecuteInAppDomain-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteInAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteInAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInAppDomain method [.NET Framework hosting]
- ExecuteInAppDomain method [.NET Framework hosting]
ms.assetid: e2b0e2db-3fae-4b56-844e-d30a125a660c
topic_type:
- apiref
ms.openlocfilehash: c012e4e2b5e41737f7bbe6a0fb887693b0ba22c8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176421"
---
# <a name="iclrruntimehostexecuteinappdomain-method"></a><span data-ttu-id="e0da9-102">ICLRRuntimeHost::ExecuteInAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="e0da9-102">ICLRRuntimeHost::ExecuteInAppDomain Method</span></span>
<span data-ttu-id="e0da9-103">Gibt an, <xref:System.AppDomain> in welcher Datei der angegebene verwaltete Code ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e0da9-103">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0da9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e0da9-104">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteInAppDomain(  
    [in] DWORD AppDomainId,
    [in] FExecuteInDomainCallback pCallback,
    [in] void* cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0da9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e0da9-105">Parameters</span></span>  
 `AppDomainId`  
 <span data-ttu-id="e0da9-106">[in] Die numerische ID <xref:System.AppDomain> der, in der die angegebene Methode ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e0da9-106">[in] The numeric ID of the <xref:System.AppDomain> in which to execute the specified method.</span></span>  
  
 `pCallback`  
 <span data-ttu-id="e0da9-107">[in] Ein Zeiger auf die Funktion, <xref:System.AppDomain>die innerhalb der angegebenen ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e0da9-107">[in] A pointer to the function to execute within the specified <xref:System.AppDomain>.</span></span>  
  
 `cookie`  
 <span data-ttu-id="e0da9-108">[in] Ein Zeiger auf undurchsichtigen Speicher, der vom Aufrufer zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="e0da9-108">[in] A pointer to opaque caller-allocated memory.</span></span> <span data-ttu-id="e0da9-109">Dieser Parameter wird von der Common Language Runtime (CLR) an den Domänenrückruf übergeben.</span><span class="sxs-lookup"><span data-stu-id="e0da9-109">This parameter is passed by the common language runtime (CLR) to the domain callback.</span></span> <span data-ttu-id="e0da9-110">Es handelt sich nicht um einen mit einer Laufzeit verwalteten Heapspeicher. Sowohl die Zuweisung als auch die Lebensdauer dieses Speichers werden vom Aufrufer gesteuert.</span><span class="sxs-lookup"><span data-stu-id="e0da9-110">It is not runtime-managed heap memory; both the allocation and lifetime of this memory are controlled by the caller.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e0da9-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e0da9-111">Return Value</span></span>  
  
|<span data-ttu-id="e0da9-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e0da9-112">HRESULT</span></span>|<span data-ttu-id="e0da9-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e0da9-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e0da9-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="e0da9-114">S_OK</span></span>|<span data-ttu-id="e0da9-115">`ExecuteInAppDomain`erfolgreich zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e0da9-115">`ExecuteInAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="e0da9-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e0da9-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e0da9-117">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem sie keinen verwalteten Code ausführen oder den Aufruf erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="e0da9-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e0da9-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e0da9-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e0da9-119">Timeout für den Anruf.</span><span class="sxs-lookup"><span data-stu-id="e0da9-119">The call timed out.</span></span>|  
|<span data-ttu-id="e0da9-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e0da9-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e0da9-121">Der Aufrufer besitzt die Sperre nicht.</span><span class="sxs-lookup"><span data-stu-id="e0da9-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e0da9-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e0da9-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e0da9-123">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine blockierte Faser darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="e0da9-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e0da9-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e0da9-124">E_FAIL</span></span>|<span data-ttu-id="e0da9-125">Ein unbekannter katastrophaler Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="e0da9-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e0da9-126">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e0da9-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e0da9-127">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="e0da9-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0da9-128">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e0da9-128">Remarks</span></span>  
 <span data-ttu-id="e0da9-129">`ExecuteInAppDomain`ermöglicht es dem Host, <xref:System.AppDomain> die Kontrolle darüber auszuüben, in welcher Verwalteten die angegebene verwaltete Methode ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e0da9-129">`ExecuteInAppDomain` allows the host to exercise control over which managed <xref:System.AppDomain> the specified managed method should be executed in.</span></span> <span data-ttu-id="e0da9-130">Sie können den Wert des Bezeichners einer Anwendungsdomäne <xref:System.AppDomain.Id%2A> abrufen, der dem Wert der Eigenschaft entspricht, indem Sie die [GetCurrentAppDomainId-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)aufrufen.</span><span class="sxs-lookup"><span data-stu-id="e0da9-130">You can get the value of an application domain's identifier, which corresponds to the value of the <xref:System.AppDomain.Id%2A> property, by calling [GetCurrentAppDomainId Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0da9-131">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e0da9-131">Requirements</span></span>  
 <span data-ttu-id="e0da9-132">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0da9-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0da9-133">**Kopfzeile:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e0da9-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e0da9-134">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e0da9-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e0da9-135">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0da9-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0da9-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e0da9-136">See also</span></span>

- [<span data-ttu-id="e0da9-137">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e0da9-137">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
