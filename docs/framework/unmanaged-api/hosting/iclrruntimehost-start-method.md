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
ms.openlocfilehash: 608612f6a0f4395092e33ce75fdbd249f19ae4f4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59172613"
---
# <a name="iclrruntimehoststart-method"></a><span data-ttu-id="faf12-102">ICLRRuntimeHost::Start-Methode</span><span class="sxs-lookup"><span data-stu-id="faf12-102">ICLRRuntimeHost::Start Method</span></span>
<span data-ttu-id="faf12-103">Initialisiert die common Language Runtime (CLR) in einen Prozess an.</span><span class="sxs-lookup"><span data-stu-id="faf12-103">Initializes the common language runtime (CLR) into a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="faf12-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="faf12-104">Syntax</span></span>  
  
```  
HRESULT Start();  
```  
  
## <a name="return-value"></a><span data-ttu-id="faf12-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="faf12-105">Return Value</span></span>  
  
|<span data-ttu-id="faf12-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="faf12-106">HRESULT</span></span>|<span data-ttu-id="faf12-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="faf12-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="faf12-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="faf12-108">S_OK</span></span>|`Start` <span data-ttu-id="faf12-109">wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="faf12-109">returned successfully.</span></span>|  
|<span data-ttu-id="faf12-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="faf12-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="faf12-111">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="faf12-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="faf12-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="faf12-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="faf12-113">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="faf12-113">The call timed out.</span></span>|  
|<span data-ttu-id="faf12-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="faf12-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="faf12-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="faf12-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="faf12-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="faf12-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="faf12-117">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="faf12-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="faf12-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="faf12-118">E_FAIL</span></span>|<span data-ttu-id="faf12-119">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="faf12-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="faf12-120">Wenn eine Methode E_FAIL zurückgegeben wird, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="faf12-120">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="faf12-121">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="faf12-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="faf12-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="faf12-122">Remarks</span></span>  
 <span data-ttu-id="faf12-123">In vielen Szenarien ist es nicht notwendig, `Start`, da die Common Language Runtime bei der ersten Anforderung zum Ausführen von verwalteten Codes automatisch initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="faf12-123">In many scenarios it is not necessary to call `Start`, because the runtime will initialize itself automatically upon the first request to run managed code.</span></span> <span data-ttu-id="faf12-124">Sie können allerdings verwenden `Start` an genau, wenn die Common Language Runtime initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="faf12-124">You can, however, use `Start` to specify exactly when the runtime should be initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="faf12-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="faf12-125">Requirements</span></span>  
 <span data-ttu-id="faf12-126">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="faf12-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="faf12-127">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="faf12-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="faf12-128">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="faf12-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="faf12-129">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="faf12-129">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="faf12-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="faf12-130">See also</span></span>

- <xref:System.AppDomain>
- [<span data-ttu-id="faf12-131">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="faf12-131">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
