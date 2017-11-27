---
title: IHostIoCompletionManager::Bind-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostIoCompletionManager.Bind
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostIoCompletionManager::Bind
helpviewer_keywords:
- IHostIoCompletionManager::Bind method [.NET Framework hosting]
- Bind method [.NET Framework hosting]
ms.assetid: acd74cb5-7e22-4a07-83c3-82288e1abd9f
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d5eba258065c5ddbbf6fad474aed700065b155a4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ihostiocompletionmanagerbind-method"></a><span data-ttu-id="0b2cc-102">IHostIoCompletionManager::Bind-Methode</span><span class="sxs-lookup"><span data-stu-id="0b2cc-102">IHostIoCompletionManager::Bind Method</span></span>
<span data-ttu-id="0b2cc-103">Bindet das angegebene Handle eines e/a-Abschlussanschlusses, der durch einen früheren Aufruf erstellt wurde [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span><span class="sxs-lookup"><span data-stu-id="0b2cc-103">Binds the specified handle to an I/O completion port that has been created by an earlier call to [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b2cc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0b2cc-104">Syntax</span></span>  
  
```  
HRESULT Bind (  
    [in] HANDLE hPort,  
    [in] HANDLE hHandle  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0b2cc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0b2cc-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="0b2cc-106">[in] Der e/a-Abschlussport für die Bindung `hHandle`.</span><span class="sxs-lookup"><span data-stu-id="0b2cc-106">[in] The I/O completion port to which to bind `hHandle`.</span></span> <span data-ttu-id="0b2cc-107">Wenn der Wert der `hPort` ist null, `hHandle` an der Standard-e/a-Abschlussport gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="0b2cc-107">If the value of `hPort` is null, `hHandle` is bound to the default I/O completion port.</span></span>  
  
 `hHandle`  
 <span data-ttu-id="0b2cc-108">[in] Das Betriebssystemhandle zum Binden an `hPort`.</span><span class="sxs-lookup"><span data-stu-id="0b2cc-108">[in] The operating system handle to bind to `hPort`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0b2cc-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0b2cc-109">Return Value</span></span>  
  
|<span data-ttu-id="0b2cc-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0b2cc-110">HRESULT</span></span>|<span data-ttu-id="0b2cc-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0b2cc-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0b2cc-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="0b2cc-112">S_OK</span></span>|<span data-ttu-id="0b2cc-113">`Bind`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0b2cc-113">`Bind` returned successfully.</span></span>|  
|<span data-ttu-id="0b2cc-114">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="0b2cc-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0b2cc-115">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="0b2cc-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0b2cc-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0b2cc-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0b2cc-117">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0b2cc-117">The call timed out.</span></span>|  
|<span data-ttu-id="0b2cc-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0b2cc-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0b2cc-119">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="0b2cc-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0b2cc-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0b2cc-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0b2cc-121">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="0b2cc-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0b2cc-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0b2cc-122">E_FAIL</span></span>|<span data-ttu-id="0b2cc-123">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="0b2cc-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0b2cc-124">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="0b2cc-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0b2cc-125">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="0b2cc-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b2cc-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0b2cc-126">Remarks</span></span>  
 <span data-ttu-id="0b2cc-127">Ein e/a-Abschlussport wird erstellt, indem Sie über einen Aufruf an `CreateIoCompletionPort`.</span><span class="sxs-lookup"><span data-stu-id="0b2cc-127">An I/O completion port is created by using a call to `CreateIoCompletionPort`.</span></span> <span data-ttu-id="0b2cc-128">Die CLR ruft `Bind` ein Handle an diesen Port gebunden.</span><span class="sxs-lookup"><span data-stu-id="0b2cc-128">The CLR calls `Bind` to bind a handle to that port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0b2cc-129">Wenn eine e/a-Anforderung abgeschlossen ist, muss der Host Aufrufen der [ICLRIoCompletionManager:: OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="0b2cc-129">When an I/O request completes, the host must call the [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b2cc-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0b2cc-130">Requirements</span></span>  
 <span data-ttu-id="0b2cc-131">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b2cc-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b2cc-132">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0b2cc-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0b2cc-133">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0b2cc-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0b2cc-134">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b2cc-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b2cc-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0b2cc-135">See Also</span></span>  
 [<span data-ttu-id="0b2cc-136">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0b2cc-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
