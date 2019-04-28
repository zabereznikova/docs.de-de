---
title: IHostIoCompletionManager::InitializeHostOverlapped-Methode
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.InitializeHostOverlapped
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::InitializeHostOverlapped
helpviewer_keywords:
- IHostIoCompletionManager::InitializeHostOverlapped method [.NET Framework hosting]
- InitializeHostOverlapped method [.NET Framework hosting]
ms.assetid: c35199bf-bc47-4901-b467-4e8a37644bbb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1dea19a13cd2c741a24695b293ae1c8621ad5688
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796798"
---
# <a name="ihostiocompletionmanagerinitializehostoverlapped-method"></a><span data-ttu-id="d43ec-102">IHostIoCompletionManager::InitializeHostOverlapped-Methode</span><span class="sxs-lookup"><span data-stu-id="d43ec-102">IHostIoCompletionManager::InitializeHostOverlapped Method</span></span>
<span data-ttu-id="d43ec-103">Ermöglicht es dem Host mit der Möglichkeit, benutzerdefinierte Daten zum Anfügen an eine Win32 initialisieren `OVERLAPPED` -Struktur, die für asynchrone e/a-Anforderungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d43ec-103">Provides the host with an opportunity to initialize any custom data to append to a Win32 `OVERLAPPED` structure that is used for asynchronous I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d43ec-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d43ec-104">Syntax</span></span>  
  
```  
HRESULT InitializeHostOverlapped (  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d43ec-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d43ec-105">Parameters</span></span>  
 `pvOverlapped`  
 <span data-ttu-id="d43ec-106">[in] Ein Zeiger auf die Win32- `OVERLAPPED` Struktur mit der e/a-Anforderung eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d43ec-106">[in] A pointer to the Win32 `OVERLAPPED` structure to be included with the I/O request.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d43ec-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d43ec-107">Return Value</span></span>  
  
|<span data-ttu-id="d43ec-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d43ec-108">HRESULT</span></span>|<span data-ttu-id="d43ec-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d43ec-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d43ec-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d43ec-110">S_OK</span></span>|<span data-ttu-id="d43ec-111">`InitializeHostOverlapped` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d43ec-111">`InitializeHostOverlapped` returned successfully.</span></span>|  
|<span data-ttu-id="d43ec-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d43ec-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d43ec-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="d43ec-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d43ec-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d43ec-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d43ec-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="d43ec-115">The call timed out.</span></span>|  
|<span data-ttu-id="d43ec-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d43ec-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d43ec-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="d43ec-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d43ec-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d43ec-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d43ec-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="d43ec-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d43ec-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d43ec-120">E_FAIL</span></span>|<span data-ttu-id="d43ec-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="d43ec-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d43ec-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d43ec-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d43ec-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="d43ec-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d43ec-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="d43ec-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="d43ec-125">Es war nicht genügend Arbeitsspeicher verfügbar, um die angeforderte Ressource zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="d43ec-125">Not enough memory was available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d43ec-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d43ec-126">Remarks</span></span>  
 <span data-ttu-id="d43ec-127">Die Windows-Plattform-Funktionen verwenden die `OVERLAPPED` Struktur zum Speichern von Status für asynchrone e/a-Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="d43ec-127">The Windows Platform functions use the `OVERLAPPED` structure to store state for asynchronous I/O requests.</span></span> <span data-ttu-id="d43ec-128">Die CLR ruft die `InitializeHostOverlapped` Methode, um dem Host Geben Sie das Anfügen von benutzerdefinierten Daten zu einem `OVERLAPPED` Instanz.</span><span class="sxs-lookup"><span data-stu-id="d43ec-128">The CLR calls the `InitializeHostOverlapped` method to give the host the opportunity to append custom data to an `OVERLAPPED` instance.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d43ec-129">Rufen Sie am Anfang des benutzerdefinierten Datenblocks müssen Hosts den Offset der Größe der Festlegen der `OVERLAPPED` Struktur (`sizeof(OVERLAPPED)`).</span><span class="sxs-lookup"><span data-stu-id="d43ec-129">To get to the beginning of their custom data block, hosts must set the offset to the size of the `OVERLAPPED` structure (`sizeof(OVERLAPPED)`).</span></span>  
  
 <span data-ttu-id="d43ec-130">Ein Rückgabewert von E_OUTOFMEMORY gibt an, dass der Host zum Initialisieren der benutzerdefinierten Daten fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="d43ec-130">A return value of E_OUTOFMEMORY indicates that the host has failed to initialize its custom data.</span></span> <span data-ttu-id="d43ec-131">In diesem Fall wird die CLR meldet einen Fehler, und der Aufruf schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="d43ec-131">In this case, the CLR reports an error and fails the call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d43ec-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d43ec-132">Requirements</span></span>  
 <span data-ttu-id="d43ec-133">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d43ec-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d43ec-134">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d43ec-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d43ec-135">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d43ec-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d43ec-136">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d43ec-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d43ec-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d43ec-137">See also</span></span>

- [<span data-ttu-id="d43ec-138">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d43ec-138">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="d43ec-139">GetHostOverlappedSize-Methode</span><span class="sxs-lookup"><span data-stu-id="d43ec-139">GetHostOverlappedSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)
- [<span data-ttu-id="d43ec-140">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d43ec-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
