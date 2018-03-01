---
title: IHostIoCompletionManager::GetHostOverlappedSize-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostIoCompletionManager.GetHostOverlappedSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetHostOverlappedSize
helpviewer_keywords:
- IHostIoCompletionManager::GetHostOverlappedSize method [.NET Framework hosting]
- GetHostOverlappedSize method [.NET Framework hosting]
ms.assetid: 2902578b-d5e2-4f8d-a103-0c7b6dceda9e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 41fc1a4a0debe0c302115c79962c0da50cc4ee37
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihostiocompletionmanagergethostoverlappedsize-method"></a><span data-ttu-id="d08f2-102">IHostIoCompletionManager::GetHostOverlappedSize-Methode</span><span class="sxs-lookup"><span data-stu-id="d08f2-102">IHostIoCompletionManager::GetHostOverlappedSize Method</span></span>
<span data-ttu-id="d08f2-103">Ruft die Größe der benutzerdefinierten Daten, die der Host beabsichtigt, um e/a-Anforderungen angefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d08f2-103">Gets the size of any custom data the host intends to append to I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d08f2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d08f2-104">Syntax</span></span>  
  
```  
HRESULT GetHostOverlappedSize (  
    [out] DWORD *pcbSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d08f2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d08f2-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="d08f2-106">[out] Ein Zeiger auf die Anzahl der Bytes, die die common Language Runtime (CLR) zusätzlich zur Größe des Win32-zuordnen soll `OVERLAPPED` Objekt.</span><span class="sxs-lookup"><span data-stu-id="d08f2-106">[out] A pointer to the number of bytes that the common language runtime (CLR) should allocate in addition to the size of the Win32 `OVERLAPPED` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d08f2-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d08f2-107">Return Value</span></span>  
  
|<span data-ttu-id="d08f2-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d08f2-108">HRESULT</span></span>|<span data-ttu-id="d08f2-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d08f2-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d08f2-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d08f2-110">S_OK</span></span>|<span data-ttu-id="d08f2-111">`GetHostOverlappedSize`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d08f2-111">`GetHostOverlappedSize` returned successfully.</span></span>|  
|<span data-ttu-id="d08f2-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="d08f2-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d08f2-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="d08f2-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d08f2-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d08f2-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d08f2-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="d08f2-115">The call timed out.</span></span>|  
|<span data-ttu-id="d08f2-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d08f2-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d08f2-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="d08f2-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d08f2-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d08f2-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d08f2-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="d08f2-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d08f2-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d08f2-120">E_FAIL</span></span>|<span data-ttu-id="d08f2-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="d08f2-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d08f2-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="d08f2-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d08f2-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="d08f2-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d08f2-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d08f2-124">Remarks</span></span>  
 <span data-ttu-id="d08f2-125">Alle asynchronen e/a-Aufrufe von Windows-Plattform-APIs verwenden ein Win32- `OVERLAPPED` -Objekt, das Informationen, z. B. die Position des Dateizeigers bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="d08f2-125">All asynchronous I/O calls to Windows Platform APIs take a Win32 `OVERLAPPED` object, which provides information such as the file pointer position.</span></span> <span data-ttu-id="d08f2-126">Um den Status beizubehalten, Anwendungen, die asynchrone e/a-Aufrufe in der Regel stellen benutzerdefinierte Daten der Struktur hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d08f2-126">To maintain state, applications that make asynchronous I/O calls typically add custom data to the structure.</span></span> <span data-ttu-id="d08f2-127">`GetHostOverlappedSize`und [IHostIoCompletionManager:: InitializeHostOverlapped](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md) bieten eine Möglichkeit für den Host, diese benutzerdefinierten Daten aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="d08f2-127">`GetHostOverlappedSize` and [IHostIoCompletionManager::InitializeHostOverlapped](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md) provide an opportunity for the host to include such custom data.</span></span>  
  
 <span data-ttu-id="d08f2-128">Die CLR ruft die `GetHostOverlappedSize` Methode, um die Größe der benutzerdefinierten Daten zu bestimmen, die der Host zum Anfügen an die `OVERLAPPED` Objekt.</span><span class="sxs-lookup"><span data-stu-id="d08f2-128">The CLR calls the `GetHostOverlappedSize` method to determine the size of the custom data that the host intends to append to the `OVERLAPPED` object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d08f2-129">`GetHostOverlappedSize`wird nur einmal aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="d08f2-129">`GetHostOverlappedSize` is called only once.</span></span> <span data-ttu-id="d08f2-130">Benutzerdefinierte Daten für den Host muss die gleiche Größe für alle e/a-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="d08f2-130">The host's custom data must be the same size for every I/O request.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d08f2-131">Die Größe der `OVERLAPPED` Objekt selbst ist nicht im Wert des enthalten `pcbSize`.</span><span class="sxs-lookup"><span data-stu-id="d08f2-131">The size of the `OVERLAPPED` object itself is not included in the value of `pcbSize`.</span></span>  
  
 <span data-ttu-id="d08f2-132">Weitere Informationen zu den `OVERLAPPED` -Struktur, finden Sie in der Dokumentation zur Windows-Plattform.</span><span class="sxs-lookup"><span data-stu-id="d08f2-132">For more information about the `OVERLAPPED` structure, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d08f2-133">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d08f2-133">Requirements</span></span>  
 <span data-ttu-id="d08f2-134">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d08f2-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d08f2-135">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d08f2-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d08f2-136">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d08f2-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d08f2-137">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d08f2-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d08f2-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d08f2-138">See Also</span></span>  
 <xref:System.Threading.NativeOverlapped>  
 [<span data-ttu-id="d08f2-139">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d08f2-139">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="d08f2-140">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d08f2-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
