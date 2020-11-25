---
title: ICLRRuntimeHost::Stop-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.Stop
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::Stop
helpviewer_keywords:
- ICLRRuntimeHost::Stop method [.NET Framework hosting]
- Stop method, ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: b8fd7daf-8f8d-4ad7-92ae-019db244cec1
topic_type:
- apiref
ms.openlocfilehash: 50e777bde34eb0122ca537da4b73a5e507ce7a7b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728796"
---
# <a name="iclrruntimehoststop-method"></a><span data-ttu-id="430d9-102">ICLRRuntimeHost::Stop-Methode</span><span class="sxs-lookup"><span data-stu-id="430d9-102">ICLRRuntimeHost::Stop Method</span></span>

<span data-ttu-id="430d9-103">Beendet die Ausführung des Codes durch die Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="430d9-103">Stops the execution of code by the common language runtime (CLR).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="430d9-104">Diese Methode gibt keine Ressourcen für den Host frei, entladen Anwendungs Domänen oder zerstört Threads.</span><span class="sxs-lookup"><span data-stu-id="430d9-104">This method does not release resources to the host, unload application domains, or destroy threads.</span></span> <span data-ttu-id="430d9-105">Sie müssen den Prozess beenden, um diese Ressourcen freizugeben.</span><span class="sxs-lookup"><span data-stu-id="430d9-105">You must terminate the process to release these resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="430d9-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="430d9-106">Syntax</span></span>  
  
```cpp  
HRESULT Stop();  
```  
  
## <a name="return-value"></a><span data-ttu-id="430d9-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="430d9-107">Return Value</span></span>  
  
|<span data-ttu-id="430d9-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="430d9-108">HRESULT</span></span>|<span data-ttu-id="430d9-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="430d9-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="430d9-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="430d9-110">S_OK</span></span>|<span data-ttu-id="430d9-111">`Stop` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="430d9-111">`Stop` returned successfully.</span></span>|  
|<span data-ttu-id="430d9-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="430d9-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="430d9-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="430d9-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="430d9-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="430d9-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="430d9-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="430d9-115">The call timed out.</span></span>|  
|<span data-ttu-id="430d9-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="430d9-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="430d9-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="430d9-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="430d9-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="430d9-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="430d9-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="430d9-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="430d9-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="430d9-120">E_FAIL</span></span>|<span data-ttu-id="430d9-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="430d9-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="430d9-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="430d9-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="430d9-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="430d9-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="430d9-124">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="430d9-124">Requirements</span></span>  

 <span data-ttu-id="430d9-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="430d9-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="430d9-126">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="430d9-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="430d9-127">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="430d9-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="430d9-128">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="430d9-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="430d9-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="430d9-129">See also</span></span>

- [<span data-ttu-id="430d9-130">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="430d9-130">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
