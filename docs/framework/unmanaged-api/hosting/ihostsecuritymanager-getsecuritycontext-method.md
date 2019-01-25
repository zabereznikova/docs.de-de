---
title: IHostSecurityManager::GetSecurityContext-Methode
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.GetSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::GetSecurityContext
helpviewer_keywords:
- GetSecurityContext method [.NET Framework hosting]
- IHostSecurityManager::GetSecurityContext method [.NET Framework hosting]
ms.assetid: 958970d6-f6a2-4b84-b32a-f555cbaf8f61
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e11b447ebd03746730a86dbbcda31edd4196f13b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54644949"
---
# <a name="ihostsecuritymanagergetsecuritycontext-method"></a><span data-ttu-id="37b8d-102">IHostSecurityManager::GetSecurityContext-Methode</span><span class="sxs-lookup"><span data-stu-id="37b8d-102">IHostSecurityManager::GetSecurityContext Method</span></span>
<span data-ttu-id="37b8d-103">Ruft die angeforderte [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) vom Host.</span><span class="sxs-lookup"><span data-stu-id="37b8d-103">Gets the requested [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) from the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37b8d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="37b8d-104">Syntax</span></span>  
  
```  
HRESULT GetSecurityContext (  
    [in]  EContextType eContextType,   
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="37b8d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="37b8d-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="37b8d-106">[in] Eines der [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) Werte, der angibt, welche Art von Sicherheitskontext zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="37b8d-106">[in] One of the [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) values, indicating what type of security context to return.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="37b8d-107">[out] Die Adresse des einen Schnittstellenzeiger auf das `IHostSecurityContext` von `eContextType`.</span><span class="sxs-lookup"><span data-stu-id="37b8d-107">[out] The address of an interface pointer to the `IHostSecurityContext` of `eContextType`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="37b8d-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="37b8d-108">Return Value</span></span>  
  
|<span data-ttu-id="37b8d-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="37b8d-109">HRESULT</span></span>|<span data-ttu-id="37b8d-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="37b8d-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="37b8d-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="37b8d-111">S_OK</span></span>|<span data-ttu-id="37b8d-112">`GetSecurityContext` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="37b8d-112">`GetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="37b8d-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="37b8d-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="37b8d-114">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="37b8d-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="37b8d-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="37b8d-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="37b8d-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="37b8d-116">The call timed out.</span></span>|  
|<span data-ttu-id="37b8d-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="37b8d-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="37b8d-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="37b8d-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="37b8d-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="37b8d-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="37b8d-120">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="37b8d-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="37b8d-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="37b8d-121">E_FAIL</span></span>|<span data-ttu-id="37b8d-122">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="37b8d-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="37b8d-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="37b8d-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="37b8d-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="37b8d-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37b8d-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="37b8d-125">Remarks</span></span>  
 <span data-ttu-id="37b8d-126">Ein Host kann alle Codezugriff auf Threadtoken von der CLR und die Benutzer Code steuern.</span><span class="sxs-lookup"><span data-stu-id="37b8d-126">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="37b8d-127">Sie können auch sicherstellen, dass vollständige Informationen über asynchrone Vorgänge oder Codepunkte mit eingeschränktem Codezugriff übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="37b8d-127">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="37b8d-128">`IHostSecurityContext` kapselt dieses Sicherheitskontextinformationen, die für die CLR nicht transparent ist.</span><span class="sxs-lookup"><span data-stu-id="37b8d-128">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span> <span data-ttu-id="37b8d-129">Die CLR erfasst diese Informationen, und verschiebt sie über den Threadpool Worker Element Dispatch, Finalizerausführung und Modul und jeder Klasse erstellen.</span><span class="sxs-lookup"><span data-stu-id="37b8d-129">The CLR captures this information and moves it across thread pool worker item dispatch, finalizer execution, and module and class construction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37b8d-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="37b8d-130">Requirements</span></span>  
 <span data-ttu-id="37b8d-131">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37b8d-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37b8d-132">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="37b8d-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="37b8d-133">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="37b8d-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="37b8d-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37b8d-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37b8d-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="37b8d-135">See also</span></span>
- [<span data-ttu-id="37b8d-136">EContextType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="37b8d-136">EContextType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)
- [<span data-ttu-id="37b8d-137">IHostSecurityContext-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="37b8d-137">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="37b8d-138">IHostSecurityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="37b8d-138">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
