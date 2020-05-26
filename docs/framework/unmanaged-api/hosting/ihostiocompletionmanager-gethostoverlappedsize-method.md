---
title: IHostIoCompletionManager::GetHostOverlappedSize-Methode
ms.date: 03/30/2017
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
ms.openlocfilehash: a97009a4ebc834d867dddcc350033c550364ea42
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804751"
---
# <a name="ihostiocompletionmanagergethostoverlappedsize-method"></a><span data-ttu-id="5ab25-102">IHostIoCompletionManager::GetHostOverlappedSize-Methode</span><span class="sxs-lookup"><span data-stu-id="5ab25-102">IHostIoCompletionManager::GetHostOverlappedSize Method</span></span>
<span data-ttu-id="5ab25-103">Ruft die Größe aller benutzerdefinierten Daten ab, die der Host an e/a-Anforderungen anfügen soll.</span><span class="sxs-lookup"><span data-stu-id="5ab25-103">Gets the size of any custom data the host intends to append to I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ab25-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5ab25-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHostOverlappedSize (  
    [out] DWORD *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ab25-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5ab25-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="5ab25-106">vorgenommen Ein Zeiger auf die Anzahl der Bytes, die der Common Language Runtime (CLR) zusätzlich zur Größe des Win32-Objekts zuordnen soll `OVERLAPPED` .</span><span class="sxs-lookup"><span data-stu-id="5ab25-106">[out] A pointer to the number of bytes that the common language runtime (CLR) should allocate in addition to the size of the Win32 `OVERLAPPED` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5ab25-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5ab25-107">Return Value</span></span>  
  
|<span data-ttu-id="5ab25-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5ab25-108">HRESULT</span></span>|<span data-ttu-id="5ab25-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5ab25-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5ab25-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="5ab25-110">S_OK</span></span>|<span data-ttu-id="5ab25-111">`GetHostOverlappedSize`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5ab25-111">`GetHostOverlappedSize` returned successfully.</span></span>|  
|<span data-ttu-id="5ab25-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5ab25-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5ab25-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="5ab25-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5ab25-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5ab25-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5ab25-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="5ab25-115">The call timed out.</span></span>|  
|<span data-ttu-id="5ab25-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5ab25-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5ab25-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="5ab25-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5ab25-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5ab25-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5ab25-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="5ab25-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5ab25-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5ab25-120">E_FAIL</span></span>|<span data-ttu-id="5ab25-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="5ab25-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5ab25-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="5ab25-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5ab25-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="5ab25-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ab25-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5ab25-124">Remarks</span></span>  
 <span data-ttu-id="5ab25-125">Alle asynchronen e/a-Aufrufe an Windows-Plattform-APIs nehmen ein Win32- `OVERLAPPED` Objekt an, das Informationen wie die Dateizeiger Position bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="5ab25-125">All asynchronous I/O calls to Windows Platform APIs take a Win32 `OVERLAPPED` object, which provides information such as the file pointer position.</span></span> <span data-ttu-id="5ab25-126">Zur Aufrechterhaltung des Zustands fügen Anwendungen, die asynchrone e/a-Aufrufe durchführen, in der Regel benutzerdefinierte Daten zur Struktur hinzu.</span><span class="sxs-lookup"><span data-stu-id="5ab25-126">To maintain state, applications that make asynchronous I/O calls typically add custom data to the structure.</span></span> <span data-ttu-id="5ab25-127">`GetHostOverlappedSize`und [IHostIoCompletionManager:: initializehostoverllapp](ihostiocompletionmanager-initializehostoverlapped-method.md) bieten dem Host die Möglichkeit, solche benutzerdefinierten Daten einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="5ab25-127">`GetHostOverlappedSize` and [IHostIoCompletionManager::InitializeHostOverlapped](ihostiocompletionmanager-initializehostoverlapped-method.md) provide an opportunity for the host to include such custom data.</span></span>  
  
 <span data-ttu-id="5ab25-128">Die CLR ruft die- `GetHostOverlappedSize` Methode auf, um die Größe der benutzerdefinierten Daten zu bestimmen, die der Host an das-Objekt anfügen soll `OVERLAPPED` .</span><span class="sxs-lookup"><span data-stu-id="5ab25-128">The CLR calls the `GetHostOverlappedSize` method to determine the size of the custom data that the host intends to append to the `OVERLAPPED` object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5ab25-129">`GetHostOverlappedSize`wird nur einmal aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="5ab25-129">`GetHostOverlappedSize` is called only once.</span></span> <span data-ttu-id="5ab25-130">Die benutzerdefinierten Daten des Hosts müssen für jede e/a-Anforderung dieselbe Größe aufweisen.</span><span class="sxs-lookup"><span data-stu-id="5ab25-130">The host's custom data must be the same size for every I/O request.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="5ab25-131">Die Größe des `OVERLAPPED` Objekts selbst ist nicht im Wert von enthalten `pcbSize` .</span><span class="sxs-lookup"><span data-stu-id="5ab25-131">The size of the `OVERLAPPED` object itself is not included in the value of `pcbSize`.</span></span>  
  
 <span data-ttu-id="5ab25-132">Weitere Informationen zur `OVERLAPPED` Struktur finden Sie in der Dokumentation zur Windows-Plattform.</span><span class="sxs-lookup"><span data-stu-id="5ab25-132">For more information about the `OVERLAPPED` structure, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ab25-133">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5ab25-133">Requirements</span></span>  
 <span data-ttu-id="5ab25-134">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ab25-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ab25-135">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="5ab25-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5ab25-136">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5ab25-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5ab25-137">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ab25-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ab25-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5ab25-138">See also</span></span>

- <xref:System.Threading.NativeOverlapped>
- [<span data-ttu-id="5ab25-139">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5ab25-139">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="5ab25-140">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5ab25-140">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
