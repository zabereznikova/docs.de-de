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
ms.openlocfilehash: b379bb2a9512cd1bd3344ed7f5130f96c0ccfa87
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855577"
---
# <a name="ihostsecuritymanagergetsecuritycontext-method"></a><span data-ttu-id="2603d-102">IHostSecurityManager::GetSecurityContext-Methode</span><span class="sxs-lookup"><span data-stu-id="2603d-102">IHostSecurityManager::GetSecurityContext Method</span></span>
<span data-ttu-id="2603d-103">Ruft den angeforderten [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) vom Host ab.</span><span class="sxs-lookup"><span data-stu-id="2603d-103">Gets the requested [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) from the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2603d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2603d-104">Syntax</span></span>  
  
```cpp
HRESULT GetSecurityContext (  
    [in]  EContextType eContextType,   
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2603d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2603d-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="2603d-106">in Einer der [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) -Werte, der angibt, welcher Typ von Sicherheitskontext zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="2603d-106">[in] One of the [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) values, indicating what type of security context to return.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="2603d-107">vorgenommen Die Adresse eines Schnittstellen Zeigers auf den `IHostSecurityContext` von `eContextType`.</span><span class="sxs-lookup"><span data-stu-id="2603d-107">[out] The address of an interface pointer to the `IHostSecurityContext` of `eContextType`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2603d-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2603d-108">Return Value</span></span>  
  
|<span data-ttu-id="2603d-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2603d-109">HRESULT</span></span>|<span data-ttu-id="2603d-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2603d-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2603d-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2603d-111">S_OK</span></span>|<span data-ttu-id="2603d-112">`GetSecurityContext`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2603d-112">`GetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="2603d-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2603d-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2603d-114">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="2603d-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2603d-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2603d-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2603d-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="2603d-116">The call timed out.</span></span>|  
|<span data-ttu-id="2603d-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2603d-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2603d-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="2603d-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2603d-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2603d-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2603d-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="2603d-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2603d-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2603d-121">E_FAIL</span></span>|<span data-ttu-id="2603d-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="2603d-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2603d-123">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2603d-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2603d-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="2603d-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2603d-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2603d-125">Remarks</span></span>  
 <span data-ttu-id="2603d-126">Ein Host kann den gesamten Code Zugriff auf Thread Token sowohl durch den CLR-als auch durch den Benutzercode steuern.</span><span class="sxs-lookup"><span data-stu-id="2603d-126">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="2603d-127">Außerdem kann sichergestellt werden, dass die umfassenden Sicherheitskontext Informationen über asynchrone Vorgänge oder Code Punkte mit eingeschränktem Code Zugriff übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="2603d-127">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="2603d-128">`IHostSecurityContext`kapselt diese Sicherheitskontext Informationen, die für die CLR nicht transparent sind.</span><span class="sxs-lookup"><span data-stu-id="2603d-128">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span> <span data-ttu-id="2603d-129">Die CLR erfasst diese Informationen und verschiebt Sie über die Verteilung von Arbeitsthreads im Thread Pool, die Finalizer-Ausführung sowie die Modul-und Klassen Konstruktion.</span><span class="sxs-lookup"><span data-stu-id="2603d-129">The CLR captures this information and moves it across thread pool worker item dispatch, finalizer execution, and module and class construction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2603d-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2603d-130">Requirements</span></span>  
 <span data-ttu-id="2603d-131">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2603d-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2603d-132">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2603d-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2603d-133">**Fern** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2603d-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2603d-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2603d-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2603d-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2603d-135">See also</span></span>

- [<span data-ttu-id="2603d-136">EContextType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="2603d-136">EContextType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)
- [<span data-ttu-id="2603d-137">IHostSecurityContext-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2603d-137">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="2603d-138">IHostSecurityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2603d-138">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
