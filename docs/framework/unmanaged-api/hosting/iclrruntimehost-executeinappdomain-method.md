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
ms.openlocfilehash: c847f177f48d72f28192d1efabe93c65a7b3f4b8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120494"
---
# <a name="iclrruntimehostexecuteinappdomain-method"></a><span data-ttu-id="9b56f-102">ICLRRuntimeHost::ExecuteInAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="9b56f-102">ICLRRuntimeHost::ExecuteInAppDomain Method</span></span>
<span data-ttu-id="9b56f-103">Gibt den <xref:System.AppDomain> an, in dem der angegebene verwaltete Code ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9b56f-103">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b56f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b56f-104">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteInAppDomain(  
    [in] DWORD AppDomainId,   
    [in] FExecuteInDomainCallback pCallback,   
    [in] void* cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b56f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9b56f-105">Parameters</span></span>  
 `AppDomainId`  
 <span data-ttu-id="9b56f-106">in Die numerische ID des <xref:System.AppDomain>, in dem die angegebene Methode ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9b56f-106">[in] The numeric ID of the <xref:System.AppDomain> in which to execute the specified method.</span></span>  
  
 `pCallback`  
 <span data-ttu-id="9b56f-107">in Ein Zeiger auf die Funktion, die innerhalb des angegebenen <xref:System.AppDomain>ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9b56f-107">[in] A pointer to the function to execute within the specified <xref:System.AppDomain>.</span></span>  
  
 `cookie`  
 <span data-ttu-id="9b56f-108">in Ein Zeiger auf den nicht transparenten vom Aufrufer zugewiesenen Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="9b56f-108">[in] A pointer to opaque caller-allocated memory.</span></span> <span data-ttu-id="9b56f-109">Dieser Parameter wird vom Common Language Runtime (CLR) an den Domänen Rückruf übergeben.</span><span class="sxs-lookup"><span data-stu-id="9b56f-109">This parameter is passed by the common language runtime (CLR) to the domain callback.</span></span> <span data-ttu-id="9b56f-110">Es handelt sich nicht um einen von der Laufzeit verwalteten Heap Speicher. die Zuordnung und die Lebensdauer dieses Speichers werden vom Aufrufer gesteuert.</span><span class="sxs-lookup"><span data-stu-id="9b56f-110">It is not runtime-managed heap memory; both the allocation and lifetime of this memory are controlled by the caller.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9b56f-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9b56f-111">Return Value</span></span>  
  
|<span data-ttu-id="9b56f-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9b56f-112">HRESULT</span></span>|<span data-ttu-id="9b56f-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9b56f-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9b56f-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="9b56f-114">S_OK</span></span>|<span data-ttu-id="9b56f-115">`ExecuteInAppDomain` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9b56f-115">`ExecuteInAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="9b56f-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9b56f-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9b56f-117">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="9b56f-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9b56f-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9b56f-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9b56f-119">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="9b56f-119">The call timed out.</span></span>|  
|<span data-ttu-id="9b56f-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9b56f-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9b56f-121">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="9b56f-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9b56f-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9b56f-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9b56f-123">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="9b56f-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9b56f-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9b56f-124">E_FAIL</span></span>|<span data-ttu-id="9b56f-125">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="9b56f-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9b56f-126">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9b56f-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9b56f-127">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="9b56f-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b56f-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9b56f-128">Remarks</span></span>  
 <span data-ttu-id="9b56f-129">mit `ExecuteInAppDomain` kann der Host steuern, welche verwaltete <xref:System.AppDomain> die angegebene verwaltete Methode in ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9b56f-129">`ExecuteInAppDomain` allows the host to exercise control over which managed <xref:System.AppDomain> the specified managed method should be executed in.</span></span> <span data-ttu-id="9b56f-130">Sie können den Wert des Bezeichners einer Anwendungsdomäne abrufen, der dem Wert der <xref:System.AppDomain.Id%2A>-Eigenschaft entspricht, indem Sie die [GetCurrentAppDomainId-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)aufrufen.</span><span class="sxs-lookup"><span data-stu-id="9b56f-130">You can get the value of an application domain's identifier, which corresponds to the value of the <xref:System.AppDomain.Id%2A> property, by calling [GetCurrentAppDomainId Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b56f-131">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9b56f-131">Requirements</span></span>  
 <span data-ttu-id="9b56f-132">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b56f-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b56f-133">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="9b56f-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9b56f-134">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9b56f-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9b56f-135">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b56f-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b56f-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b56f-136">See also</span></span>

- [<span data-ttu-id="9b56f-137">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9b56f-137">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
