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
ms.openlocfilehash: dfb96de02549e6d0f178c099793741f7fbd61d55
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724792"
---
# <a name="ihostsecuritymanagergetsecuritycontext-method"></a><span data-ttu-id="28d32-102">IHostSecurityManager::GetSecurityContext-Methode</span><span class="sxs-lookup"><span data-stu-id="28d32-102">IHostSecurityManager::GetSecurityContext Method</span></span>

<span data-ttu-id="28d32-103">Ruft den angeforderten [IHostSecurityContext](ihostsecuritycontext-interface.md) vom Host ab.</span><span class="sxs-lookup"><span data-stu-id="28d32-103">Gets the requested [IHostSecurityContext](ihostsecuritycontext-interface.md) from the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28d32-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="28d32-104">Syntax</span></span>  
  
```cpp
HRESULT GetSecurityContext (  
    [in]  EContextType eContextType,
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28d32-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="28d32-105">Parameters</span></span>  

 `eContextType`  
 <span data-ttu-id="28d32-106">in Einer der [EContextType](econtexttype-enumeration.md) -Werte, der angibt, welcher Typ von Sicherheitskontext zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="28d32-106">[in] One of the [EContextType](econtexttype-enumeration.md) values, indicating what type of security context to return.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="28d32-107">vorgenommen Die Adresse eines Schnittstellen Zeigers auf den `IHostSecurityContext` von `eContextType` .</span><span class="sxs-lookup"><span data-stu-id="28d32-107">[out] The address of an interface pointer to the `IHostSecurityContext` of `eContextType`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="28d32-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="28d32-108">Return Value</span></span>  
  
|<span data-ttu-id="28d32-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="28d32-109">HRESULT</span></span>|<span data-ttu-id="28d32-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="28d32-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="28d32-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="28d32-111">S_OK</span></span>|<span data-ttu-id="28d32-112">`GetSecurityContext` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="28d32-112">`GetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="28d32-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="28d32-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="28d32-114">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="28d32-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="28d32-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="28d32-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="28d32-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="28d32-116">The call timed out.</span></span>|  
|<span data-ttu-id="28d32-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="28d32-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="28d32-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="28d32-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="28d32-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="28d32-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="28d32-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="28d32-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="28d32-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="28d32-121">E_FAIL</span></span>|<span data-ttu-id="28d32-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="28d32-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="28d32-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="28d32-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="28d32-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="28d32-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28d32-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="28d32-125">Remarks</span></span>  

 <span data-ttu-id="28d32-126">Ein Host kann den gesamten Code Zugriff auf Thread Token sowohl durch den CLR-als auch durch den Benutzercode steuern.</span><span class="sxs-lookup"><span data-stu-id="28d32-126">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="28d32-127">Außerdem kann sichergestellt werden, dass die umfassenden Sicherheitskontext Informationen über asynchrone Vorgänge oder Code Punkte mit eingeschränktem Code Zugriff übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="28d32-127">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="28d32-128">`IHostSecurityContext` kapselt diese Sicherheitskontext Informationen, die für die CLR nicht transparent sind.</span><span class="sxs-lookup"><span data-stu-id="28d32-128">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span> <span data-ttu-id="28d32-129">Die CLR erfasst diese Informationen und verschiebt Sie über die Verteilung von Arbeitsthreads im Thread Pool, die Finalizer-Ausführung sowie die Modul-und Klassen Konstruktion.</span><span class="sxs-lookup"><span data-stu-id="28d32-129">The CLR captures this information and moves it across thread pool worker item dispatch, finalizer execution, and module and class construction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28d32-130">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="28d32-130">Requirements</span></span>  

 <span data-ttu-id="28d32-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28d32-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28d32-132">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="28d32-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="28d32-133">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="28d32-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="28d32-134">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28d32-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28d32-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="28d32-135">See also</span></span>

- [<span data-ttu-id="28d32-136">EContextType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="28d32-136">EContextType Enumeration</span></span>](econtexttype-enumeration.md)
- [<span data-ttu-id="28d32-137">IHostSecurityContext-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="28d32-137">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="28d32-138">IHostSecurityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="28d32-138">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
