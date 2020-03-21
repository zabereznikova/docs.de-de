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
ms.openlocfilehash: 7198698edce48546c4f9a82ace18d5a6e71891ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176252"
---
# <a name="ihostsecuritymanagergetsecuritycontext-method"></a><span data-ttu-id="ab316-102">IHostSecurityManager::GetSecurityContext-Methode</span><span class="sxs-lookup"><span data-stu-id="ab316-102">IHostSecurityManager::GetSecurityContext Method</span></span>
<span data-ttu-id="ab316-103">Ruft den angeforderten [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) vom Host ab.</span><span class="sxs-lookup"><span data-stu-id="ab316-103">Gets the requested [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) from the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab316-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ab316-104">Syntax</span></span>  
  
```cpp
HRESULT GetSecurityContext (  
    [in]  EContextType eContextType,
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab316-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ab316-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="ab316-106">[in] Einer der [EContextType-Werte,](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) der angibt, welcher Sicherheitskontext zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="ab316-106">[in] One of the [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) values, indicating what type of security context to return.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="ab316-107">[out] Die Adresse eines Schnittstellenzeigers `IHostSecurityContext` `eContextType`auf den von .</span><span class="sxs-lookup"><span data-stu-id="ab316-107">[out] The address of an interface pointer to the `IHostSecurityContext` of `eContextType`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ab316-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ab316-108">Return Value</span></span>  
  
|<span data-ttu-id="ab316-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ab316-109">HRESULT</span></span>|<span data-ttu-id="ab316-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ab316-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ab316-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ab316-111">S_OK</span></span>|<span data-ttu-id="ab316-112">`GetSecurityContext`erfolgreich zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ab316-112">`GetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="ab316-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ab316-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ab316-114">Die Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem sie keinen verwalteten Code ausführen oder den Aufruf erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="ab316-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ab316-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ab316-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ab316-116">Timeout für den Anruf.</span><span class="sxs-lookup"><span data-stu-id="ab316-116">The call timed out.</span></span>|  
|<span data-ttu-id="ab316-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ab316-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ab316-118">Der Aufrufer besitzt die Sperre nicht.</span><span class="sxs-lookup"><span data-stu-id="ab316-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ab316-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ab316-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ab316-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine blockierte Faser darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="ab316-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ab316-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ab316-121">E_FAIL</span></span>|<span data-ttu-id="ab316-122">Ein unbekannter katastrophaler Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="ab316-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ab316-123">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ab316-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ab316-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="ab316-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ab316-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ab316-125">Remarks</span></span>  
 <span data-ttu-id="ab316-126">Ein Host kann den gesamten Codezugriff auf Threadtoken sowohl über die CLR als auch durch den Benutzercode steuern.</span><span class="sxs-lookup"><span data-stu-id="ab316-126">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="ab316-127">Es kann auch sicherstellen, dass vollständige Sicherheitskontextinformationen über asynchrone Vorgänge oder Codepunkte mit eingeschränktem Codezugriff weitergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ab316-127">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="ab316-128">`IHostSecurityContext`Kapselt diese Sicherheitskontextinformationen, die für die CLR undurchsichtig sind.</span><span class="sxs-lookup"><span data-stu-id="ab316-128">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span> <span data-ttu-id="ab316-129">Die CLR erfasst diese Informationen und verschiebt sie über threadpool-Workerelementdispatch, Finalizerausführung und Modul- und Klassenkonstruktion.</span><span class="sxs-lookup"><span data-stu-id="ab316-129">The CLR captures this information and moves it across thread pool worker item dispatch, finalizer execution, and module and class construction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab316-130">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ab316-130">Requirements</span></span>  
 <span data-ttu-id="ab316-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab316-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab316-132">**Kopfzeile:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ab316-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ab316-133">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ab316-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ab316-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab316-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab316-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ab316-135">See also</span></span>

- [<span data-ttu-id="ab316-136">EContextType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="ab316-136">EContextType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)
- [<span data-ttu-id="ab316-137">IHostSecurityContext-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ab316-137">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="ab316-138">IHostSecurityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ab316-138">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
