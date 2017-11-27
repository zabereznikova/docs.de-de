---
title: ICLRRuntimeHost::Start-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeHost.Start
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeHost::Start
helpviewer_keywords:
- ICLRRuntimeHost::Start method [.NET Framework hosting]
- Start method, ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: c0a6dce5-0a8d-42e8-808b-6ca14df9d289
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 26e1289aa22cda2ab744f1a2715259abbcafc59b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimehoststart-method"></a><span data-ttu-id="bb8b1-102">ICLRRuntimeHost::Start-Methode</span><span class="sxs-lookup"><span data-stu-id="bb8b1-102">ICLRRuntimeHost::Start Method</span></span>
<span data-ttu-id="bb8b1-103">Initialisiert die common Language Runtime (CLR) in einen Prozess an.</span><span class="sxs-lookup"><span data-stu-id="bb8b1-103">Initializes the common language runtime (CLR) into a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb8b1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bb8b1-104">Syntax</span></span>  
  
```  
HRESULT Start();  
```  
  
## <a name="return-value"></a><span data-ttu-id="bb8b1-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="bb8b1-105">Return Value</span></span>  
  
|<span data-ttu-id="bb8b1-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bb8b1-106">HRESULT</span></span>|<span data-ttu-id="bb8b1-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bb8b1-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bb8b1-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="bb8b1-108">S_OK</span></span>|<span data-ttu-id="bb8b1-109">`Start`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="bb8b1-109">`Start` returned successfully.</span></span>|  
|<span data-ttu-id="bb8b1-110">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="bb8b1-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bb8b1-111">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="bb8b1-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bb8b1-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bb8b1-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bb8b1-113">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="bb8b1-113">The call timed out.</span></span>|  
|<span data-ttu-id="bb8b1-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bb8b1-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bb8b1-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="bb8b1-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bb8b1-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bb8b1-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bb8b1-117">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="bb8b1-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bb8b1-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bb8b1-118">E_FAIL</span></span>|<span data-ttu-id="bb8b1-119">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="bb8b1-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bb8b1-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="bb8b1-120">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bb8b1-121">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="bb8b1-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb8b1-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bb8b1-122">Remarks</span></span>  
 <span data-ttu-id="bb8b1-123">In vielen Szenarien ist es nicht notwendig, `Start`, da die Common Language Runtime bei der ersten Anforderung zum Ausführen von verwalteten Codes automatisch initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="bb8b1-123">In many scenarios it is not necessary to call `Start`, because the runtime will initialize itself automatically upon the first request to run managed code.</span></span> <span data-ttu-id="bb8b1-124">Sie können allerdings verwenden `Start` an genau, wann die Common Language Runtime initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="bb8b1-124">You can, however, use `Start` to specify exactly when the runtime should be initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb8b1-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bb8b1-125">Requirements</span></span>  
 <span data-ttu-id="bb8b1-126">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb8b1-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb8b1-127">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bb8b1-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bb8b1-128">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="bb8b1-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bb8b1-129">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb8b1-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb8b1-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb8b1-130">See Also</span></span>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="bb8b1-131">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bb8b1-131">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
