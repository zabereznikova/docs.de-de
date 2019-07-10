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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03c969cbda8fdaf8fa418c2246f3d0937e622250
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765741"
---
# <a name="iclrruntimehoststart-method"></a><span data-ttu-id="14bfa-102">ICLRRuntimeHost::Start-Methode</span><span class="sxs-lookup"><span data-stu-id="14bfa-102">ICLRRuntimeHost::Start Method</span></span>
<span data-ttu-id="14bfa-103">Initialisiert die common Language Runtime (CLR) in einen Prozess an.</span><span class="sxs-lookup"><span data-stu-id="14bfa-103">Initializes the common language runtime (CLR) into a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14bfa-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="14bfa-104">Syntax</span></span>  
  
```cpp  
HRESULT Start();  
```  
  
## <a name="return-value"></a><span data-ttu-id="14bfa-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="14bfa-105">Return Value</span></span>  
  
|<span data-ttu-id="14bfa-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="14bfa-106">HRESULT</span></span>|<span data-ttu-id="14bfa-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="14bfa-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="14bfa-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="14bfa-108">S_OK</span></span>|<span data-ttu-id="14bfa-109">`Start` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="14bfa-109">`Start` returned successfully.</span></span>|  
|<span data-ttu-id="14bfa-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="14bfa-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="14bfa-111">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="14bfa-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="14bfa-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="14bfa-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="14bfa-113">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="14bfa-113">The call timed out.</span></span>|  
|<span data-ttu-id="14bfa-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="14bfa-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="14bfa-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="14bfa-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="14bfa-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="14bfa-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="14bfa-117">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="14bfa-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="14bfa-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="14bfa-118">E_FAIL</span></span>|<span data-ttu-id="14bfa-119">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="14bfa-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="14bfa-120">Wenn eine Methode E_FAIL zurückgegeben wird, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="14bfa-120">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="14bfa-121">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="14bfa-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14bfa-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="14bfa-122">Remarks</span></span>  
 <span data-ttu-id="14bfa-123">In vielen Szenarien ist es nicht notwendig, `Start`, da die Common Language Runtime bei der ersten Anforderung zum Ausführen von verwalteten Codes automatisch initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="14bfa-123">In many scenarios it is not necessary to call `Start`, because the runtime will initialize itself automatically upon the first request to run managed code.</span></span> <span data-ttu-id="14bfa-124">Sie können allerdings verwenden `Start` an genau, wenn die Common Language Runtime initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="14bfa-124">You can, however, use `Start` to specify exactly when the runtime should be initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14bfa-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="14bfa-125">Requirements</span></span>  
 <span data-ttu-id="14bfa-126">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14bfa-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14bfa-127">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="14bfa-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="14bfa-128">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="14bfa-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="14bfa-129">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14bfa-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14bfa-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="14bfa-130">See also</span></span>

- <xref:System.AppDomain>
- [<span data-ttu-id="14bfa-131">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="14bfa-131">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
