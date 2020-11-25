---
title: ICLRRuntimeHost::SetHostControl-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.SetHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::SetHostControl
helpviewer_keywords:
- SetHostControl method [.NET Framework hosting]
- ICLRRuntimeHost::SetHostControl method [.NET Framework hosting]
ms.assetid: 6136be87-e631-4756-81ed-74b66581bad4
topic_type:
- apiref
ms.openlocfilehash: 32483be43d4d4fe9d185c091e15a13c6feb95600
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728822"
---
# <a name="iclrruntimehostsethostcontrol-method"></a><span data-ttu-id="54741-102">ICLRRuntimeHost::SetHostControl-Methode</span><span class="sxs-lookup"><span data-stu-id="54741-102">ICLRRuntimeHost::SetHostControl Method</span></span>

<span data-ttu-id="54741-103">Legt den Schnittstellen Zeiger fest, den der Common Language Runtime (CLR) verwenden kann, um die Implementierung der [IHostControl-Schnittstelle](ihostcontrol-interface.md)des Hosts zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="54741-103">Sets the interface pointer that the common language runtime (CLR) can use to get the host's implementation of [IHostControl Interface](ihostcontrol-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54741-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="54741-104">Syntax</span></span>  
  
```cpp  
HRESULT SetHostControl(  
    [in] IHostControl* pHostControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="54741-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="54741-105">Parameters</span></span>  

 `pHostControl`  
 <span data-ttu-id="54741-106">in Ein Schnittstellen Zeiger auf die Implementierung der [IHostControl-Schnittstelle](ihostcontrol-interface.md)des Hosts.</span><span class="sxs-lookup"><span data-stu-id="54741-106">[in] An interface pointer to the host's implementation of [IHostControl Interface](ihostcontrol-interface.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="54741-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="54741-107">Return Value</span></span>  
  
|<span data-ttu-id="54741-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="54741-108">HRESULT</span></span>|<span data-ttu-id="54741-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="54741-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="54741-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="54741-110">S_OK</span></span>|<span data-ttu-id="54741-111">`SetHostControl` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="54741-111">`SetHostControl` returned successfully.</span></span>|  
|<span data-ttu-id="54741-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="54741-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="54741-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="54741-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="54741-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="54741-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="54741-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="54741-115">The call timed out.</span></span>|  
|<span data-ttu-id="54741-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="54741-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="54741-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="54741-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="54741-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="54741-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="54741-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="54741-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="54741-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="54741-120">E_FAIL</span></span>|<span data-ttu-id="54741-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="54741-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="54741-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="54741-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="54741-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="54741-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="54741-124">E_CLR_ALREADY_STARTED</span><span class="sxs-lookup"><span data-stu-id="54741-124">E_CLR_ALREADY_STARTED</span></span>|<span data-ttu-id="54741-125">Die CLR wurde bereits initialisiert.</span><span class="sxs-lookup"><span data-stu-id="54741-125">The CLR has already been initialized.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="54741-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="54741-126">Remarks</span></span>  

 <span data-ttu-id="54741-127">Sie müssen `SetHostControl` vor dem Initialisieren der CLR aufzurufen, d. h. bevor Sie die [Start-Methode](iclrruntimehost-start-method.md) aufruft oder eine der [Metadatenschnittstellen](../metadata/metadata-interfaces.md)verwenden.</span><span class="sxs-lookup"><span data-stu-id="54741-127">You must call `SetHostControl` before the CLR is initialized, that is, before you call [Start Method](iclrruntimehost-start-method.md) or use any of the [Metadata Interfaces](../metadata/metadata-interfaces.md).</span></span> <span data-ttu-id="54741-128">Es wird empfohlen, dass Sie `SetHostControl` sofort nach dem Aufrufen der [CorBindToCurrentRuntime-Funktion](corbindtocurrentruntime-function.md) oder der [CorBindToRuntimeEx-Funktion](corbindtoruntimeex-function.md)aufrufen.</span><span class="sxs-lookup"><span data-stu-id="54741-128">It is recommended that you call `SetHostControl` immediately after calling [CorBindToCurrentRuntime Function](corbindtocurrentruntime-function.md) or [CorBindToRuntimeEx Function](corbindtoruntimeex-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54741-129">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="54741-129">Requirements</span></span>  

 <span data-ttu-id="54741-130">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54741-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54741-131">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="54741-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="54741-132">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="54741-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="54741-133">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54741-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54741-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="54741-134">See also</span></span>

- [<span data-ttu-id="54741-135">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="54741-135">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
- [<span data-ttu-id="54741-136">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="54741-136">IHostControl Interface</span></span>](ihostcontrol-interface.md)
