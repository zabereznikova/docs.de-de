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
ms.openlocfilehash: 0b59532d18848f1896977aa37f0a9f54a939aa75
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120379"
---
# <a name="iclrruntimehoststop-method"></a><span data-ttu-id="f60c5-102">ICLRRuntimeHost::Stop-Methode</span><span class="sxs-lookup"><span data-stu-id="f60c5-102">ICLRRuntimeHost::Stop Method</span></span>
<span data-ttu-id="f60c5-103">Beendet die Ausführung des Codes durch die Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="f60c5-103">Stops the execution of code by the common language runtime (CLR).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="f60c5-104">Diese Methode gibt keine Ressourcen für den Host frei, entladen Anwendungs Domänen oder zerstört Threads.</span><span class="sxs-lookup"><span data-stu-id="f60c5-104">This method does not release resources to the host, unload application domains, or destroy threads.</span></span> <span data-ttu-id="f60c5-105">Sie müssen den Prozess beenden, um diese Ressourcen freizugeben.</span><span class="sxs-lookup"><span data-stu-id="f60c5-105">You must terminate the process to release these resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f60c5-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="f60c5-106">Syntax</span></span>  
  
```cpp  
HRESULT Stop();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f60c5-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f60c5-107">Return Value</span></span>  
  
|<span data-ttu-id="f60c5-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f60c5-108">HRESULT</span></span>|<span data-ttu-id="f60c5-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f60c5-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f60c5-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f60c5-110">S_OK</span></span>|<span data-ttu-id="f60c5-111">`Stop` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f60c5-111">`Stop` returned successfully.</span></span>|  
|<span data-ttu-id="f60c5-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f60c5-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f60c5-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="f60c5-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f60c5-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f60c5-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f60c5-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="f60c5-115">The call timed out.</span></span>|  
|<span data-ttu-id="f60c5-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f60c5-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f60c5-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="f60c5-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f60c5-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f60c5-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f60c5-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="f60c5-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f60c5-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f60c5-120">E_FAIL</span></span>|<span data-ttu-id="f60c5-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="f60c5-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f60c5-122">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f60c5-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f60c5-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="f60c5-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f60c5-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f60c5-124">Requirements</span></span>  
 <span data-ttu-id="f60c5-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f60c5-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f60c5-126">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="f60c5-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f60c5-127">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f60c5-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f60c5-128">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f60c5-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f60c5-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f60c5-129">See also</span></span>

- [<span data-ttu-id="f60c5-130">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f60c5-130">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
