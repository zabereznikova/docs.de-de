---
title: ICLRRuntimeHost::Start-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::Start
helpviewer_keywords:
- ICLRRuntimeHost::Start method [.NET Framework hosting]
- Start method, ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: c0a6dce5-0a8d-42e8-808b-6ca14df9d289
topic_type:
- apiref
ms.openlocfilehash: a599e754202309a2b61d1761150f3f570fd0dc76
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120410"
---
# <a name="iclrruntimehoststart-method"></a><span data-ttu-id="e8460-102">ICLRRuntimeHost::Start-Methode</span><span class="sxs-lookup"><span data-stu-id="e8460-102">ICLRRuntimeHost::Start Method</span></span>
<span data-ttu-id="e8460-103">Initialisiert die Common Language Runtime (CLR) in einen Prozess.</span><span class="sxs-lookup"><span data-stu-id="e8460-103">Initializes the common language runtime (CLR) into a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8460-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e8460-104">Syntax</span></span>  
  
```cpp  
HRESULT Start();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e8460-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e8460-105">Return Value</span></span>  
  
|<span data-ttu-id="e8460-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e8460-106">HRESULT</span></span>|<span data-ttu-id="e8460-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e8460-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e8460-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="e8460-108">S_OK</span></span>|<span data-ttu-id="e8460-109">`Start` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e8460-109">`Start` returned successfully.</span></span>|  
|<span data-ttu-id="e8460-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e8460-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e8460-111">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="e8460-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e8460-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e8460-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e8460-113">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="e8460-113">The call timed out.</span></span>|  
|<span data-ttu-id="e8460-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e8460-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e8460-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="e8460-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e8460-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e8460-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e8460-117">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="e8460-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e8460-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e8460-118">E_FAIL</span></span>|<span data-ttu-id="e8460-119">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="e8460-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e8460-120">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e8460-120">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e8460-121">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="e8460-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e8460-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e8460-122">Remarks</span></span>  
 <span data-ttu-id="e8460-123">In vielen Szenarien ist es nicht notwendig, `Start`aufzurufen, da die Laufzeit bei der ersten Anforderung zum Ausführen von verwaltetem Code automatisch initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="e8460-123">In many scenarios it is not necessary to call `Start`, because the runtime will initialize itself automatically upon the first request to run managed code.</span></span> <span data-ttu-id="e8460-124">Sie können jedoch `Start` verwenden, um genau anzugeben, wann die Laufzeit initialisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="e8460-124">You can, however, use `Start` to specify exactly when the runtime should be initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8460-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e8460-125">Requirements</span></span>  
 <span data-ttu-id="e8460-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8460-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8460-127">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="e8460-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e8460-128">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e8460-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e8460-129">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8460-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8460-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8460-130">See also</span></span>

- <xref:System.AppDomain>
- [<span data-ttu-id="e8460-131">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e8460-131">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
