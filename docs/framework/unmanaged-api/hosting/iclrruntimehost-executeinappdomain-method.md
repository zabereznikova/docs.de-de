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
ms.openlocfilehash: 4c28c4a5cc64b20c9ac9c57e1aef5e7b90a20e01
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728887"
---
# <a name="iclrruntimehostexecuteinappdomain-method"></a><span data-ttu-id="42c7b-102">ICLRRuntimeHost::ExecuteInAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="42c7b-102">ICLRRuntimeHost::ExecuteInAppDomain Method</span></span>

<span data-ttu-id="42c7b-103">Gibt den an, <xref:System.AppDomain> in dem der angegebene verwaltete Code ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="42c7b-103">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42c7b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="42c7b-104">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteInAppDomain(  
    [in] DWORD AppDomainId,
    [in] FExecuteInDomainCallback pCallback,
    [in] void* cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42c7b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="42c7b-105">Parameters</span></span>  

 `AppDomainId`  
 <span data-ttu-id="42c7b-106">in Die numerische ID des <xref:System.AppDomain> , in dem die angegebene Methode ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="42c7b-106">[in] The numeric ID of the <xref:System.AppDomain> in which to execute the specified method.</span></span>  
  
 `pCallback`  
 <span data-ttu-id="42c7b-107">in Ein Zeiger auf die Funktion, die innerhalb des angegebenen ausgeführt werden soll <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="42c7b-107">[in] A pointer to the function to execute within the specified <xref:System.AppDomain>.</span></span>  
  
 `cookie`  
 <span data-ttu-id="42c7b-108">in Ein Zeiger auf den nicht transparenten vom Aufrufer zugewiesenen Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="42c7b-108">[in] A pointer to opaque caller-allocated memory.</span></span> <span data-ttu-id="42c7b-109">Dieser Parameter wird vom Common Language Runtime (CLR) an den Domänen Rückruf übergeben.</span><span class="sxs-lookup"><span data-stu-id="42c7b-109">This parameter is passed by the common language runtime (CLR) to the domain callback.</span></span> <span data-ttu-id="42c7b-110">Es handelt sich nicht um einen von der Laufzeit verwalteten Heap Speicher. die Zuordnung und die Lebensdauer dieses Speichers werden vom Aufrufer gesteuert.</span><span class="sxs-lookup"><span data-stu-id="42c7b-110">It is not runtime-managed heap memory; both the allocation and lifetime of this memory are controlled by the caller.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="42c7b-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="42c7b-111">Return Value</span></span>  
  
|<span data-ttu-id="42c7b-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="42c7b-112">HRESULT</span></span>|<span data-ttu-id="42c7b-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="42c7b-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="42c7b-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="42c7b-114">S_OK</span></span>|<span data-ttu-id="42c7b-115">`ExecuteInAppDomain` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="42c7b-115">`ExecuteInAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="42c7b-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="42c7b-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="42c7b-117">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="42c7b-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="42c7b-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="42c7b-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="42c7b-119">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="42c7b-119">The call timed out.</span></span>|  
|<span data-ttu-id="42c7b-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="42c7b-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="42c7b-121">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="42c7b-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="42c7b-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="42c7b-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="42c7b-123">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="42c7b-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="42c7b-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="42c7b-124">E_FAIL</span></span>|<span data-ttu-id="42c7b-125">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="42c7b-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="42c7b-126">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="42c7b-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="42c7b-127">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="42c7b-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42c7b-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="42c7b-128">Remarks</span></span>  

 <span data-ttu-id="42c7b-129">`ExecuteInAppDomain` ermöglicht es dem Host, die Steuerung zu steuern, über welche verwaltete <xref:System.AppDomain> die angegebene verwaltete Methode in ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="42c7b-129">`ExecuteInAppDomain` allows the host to exercise control over which managed <xref:System.AppDomain> the specified managed method should be executed in.</span></span> <span data-ttu-id="42c7b-130">Sie können den Wert des Bezeichners einer Anwendungsdomäne abrufen, der dem Wert der-Eigenschaft entspricht <xref:System.AppDomain.Id%2A> , indem Sie die [GetCurrentAppDomainId-Methode](iclrruntimehost-getcurrentappdomainid-method.md)aufrufen.</span><span class="sxs-lookup"><span data-stu-id="42c7b-130">You can get the value of an application domain's identifier, which corresponds to the value of the <xref:System.AppDomain.Id%2A> property, by calling [GetCurrentAppDomainId Method](iclrruntimehost-getcurrentappdomainid-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42c7b-131">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="42c7b-131">Requirements</span></span>  

 <span data-ttu-id="42c7b-132">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42c7b-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42c7b-133">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="42c7b-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="42c7b-134">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="42c7b-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="42c7b-135">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42c7b-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42c7b-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="42c7b-136">See also</span></span>

- [<span data-ttu-id="42c7b-137">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="42c7b-137">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
