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
ms.openlocfilehash: cf257ab86d27946c861c89dff5e6f09a42013e58
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804716"
---
# <a name="ihostiocompletionmanagerinitializehostoverlapped-method"></a><span data-ttu-id="20d87-102">IHostIoCompletionManager::InitializeHostOverlapped-Methode</span><span class="sxs-lookup"><span data-stu-id="20d87-102">IHostIoCompletionManager::InitializeHostOverlapped Method</span></span>
<span data-ttu-id="20d87-103">Bietet dem Host die Möglichkeit, benutzerdefinierte Daten zu initialisieren, um Sie an eine Win32-Struktur anzufügen `OVERLAPPED` , die für asynchrone e/a-Anforderungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="20d87-103">Provides the host with an opportunity to initialize any custom data to append to a Win32 `OVERLAPPED` structure that is used for asynchronous I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20d87-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="20d87-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeHostOverlapped (  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20d87-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="20d87-105">Parameters</span></span>  
 `pvOverlapped`  
 <span data-ttu-id="20d87-106">in Ein Zeiger auf die Win32- `OVERLAPPED` Struktur, die in der e/a-Anforderung enthalten sein soll.</span><span class="sxs-lookup"><span data-stu-id="20d87-106">[in] A pointer to the Win32 `OVERLAPPED` structure to be included with the I/O request.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="20d87-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="20d87-107">Return Value</span></span>  
  
|<span data-ttu-id="20d87-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="20d87-108">HRESULT</span></span>|<span data-ttu-id="20d87-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="20d87-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="20d87-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="20d87-110">S_OK</span></span>|<span data-ttu-id="20d87-111">`InitializeHostOverlapped`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="20d87-111">`InitializeHostOverlapped` returned successfully.</span></span>|  
|<span data-ttu-id="20d87-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="20d87-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="20d87-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="20d87-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="20d87-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="20d87-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="20d87-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="20d87-115">The call timed out.</span></span>|  
|<span data-ttu-id="20d87-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="20d87-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="20d87-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="20d87-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="20d87-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="20d87-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="20d87-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="20d87-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="20d87-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="20d87-120">E_FAIL</span></span>|<span data-ttu-id="20d87-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="20d87-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="20d87-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="20d87-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="20d87-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="20d87-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="20d87-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="20d87-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="20d87-125">Es war nicht genügend Arbeitsspeicher verfügbar, um die angeforderte Ressource zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="20d87-125">Not enough memory was available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20d87-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="20d87-126">Remarks</span></span>  
 <span data-ttu-id="20d87-127">Die Funktionen der Windows-Plattform verwenden die- `OVERLAPPED` Struktur, um den Zustand für asynchrone e/a-Anforderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="20d87-127">The Windows Platform functions use the `OVERLAPPED` structure to store state for asynchronous I/O requests.</span></span> <span data-ttu-id="20d87-128">Die CLR ruft die- `InitializeHostOverlapped` Methode auf, um dem Host die Möglichkeit zu geben, benutzerdefinierte Daten an eine Instanz anzufügen `OVERLAPPED` .</span><span class="sxs-lookup"><span data-stu-id="20d87-128">The CLR calls the `InitializeHostOverlapped` method to give the host the opportunity to append custom data to an `OVERLAPPED` instance.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="20d87-129">Um zum Anfang des benutzerdefinierten Datenblocks zu gelangen, müssen die Hosts den Offset auf die Größe der `OVERLAPPED` Struktur ( `sizeof(OVERLAPPED)` ) festlegen.</span><span class="sxs-lookup"><span data-stu-id="20d87-129">To get to the beginning of their custom data block, hosts must set the offset to the size of the `OVERLAPPED` structure (`sizeof(OVERLAPPED)`).</span></span>  
  
 <span data-ttu-id="20d87-130">Der Rückgabewert E_OUTOFMEMORY gibt an, dass der Host seine benutzerdefinierten Daten nicht initialisieren konnte.</span><span class="sxs-lookup"><span data-stu-id="20d87-130">A return value of E_OUTOFMEMORY indicates that the host has failed to initialize its custom data.</span></span> <span data-ttu-id="20d87-131">In diesem Fall meldet die CLR einen Fehler und schlägt den-Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="20d87-131">In this case, the CLR reports an error and fails the call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20d87-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="20d87-132">Requirements</span></span>  
 <span data-ttu-id="20d87-133">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20d87-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20d87-134">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="20d87-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="20d87-135">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="20d87-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="20d87-136">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20d87-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20d87-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="20d87-137">See also</span></span>

- [<span data-ttu-id="20d87-138">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="20d87-138">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="20d87-139">GetHostOverlappedSize-Methode</span><span class="sxs-lookup"><span data-stu-id="20d87-139">GetHostOverlappedSize Method</span></span>](ihostiocompletionmanager-gethostoverlappedsize-method.md)
- [<span data-ttu-id="20d87-140">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="20d87-140">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
