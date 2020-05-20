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
ms.openlocfilehash: e5ed1cbb640e760d75e1722871453a0bec283bde
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703914"
---
# <a name="iclrruntimehoststart-method"></a><span data-ttu-id="b1347-102">ICLRRuntimeHost::Start-Methode</span><span class="sxs-lookup"><span data-stu-id="b1347-102">ICLRRuntimeHost::Start Method</span></span>
<span data-ttu-id="b1347-103">Initialisiert die Common Language Runtime (CLR) in einen Prozess.</span><span class="sxs-lookup"><span data-stu-id="b1347-103">Initializes the common language runtime (CLR) into a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1347-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b1347-104">Syntax</span></span>  
  
```cpp  
HRESULT Start();  
```  
  
## <a name="return-value"></a><span data-ttu-id="b1347-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b1347-105">Return Value</span></span>  
  
|<span data-ttu-id="b1347-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b1347-106">HRESULT</span></span>|<span data-ttu-id="b1347-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b1347-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b1347-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="b1347-108">S_OK</span></span>|<span data-ttu-id="b1347-109">`Start`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b1347-109">`Start` returned successfully.</span></span>|  
|<span data-ttu-id="b1347-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b1347-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b1347-111">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="b1347-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b1347-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b1347-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b1347-113">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="b1347-113">The call timed out.</span></span>|  
|<span data-ttu-id="b1347-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b1347-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b1347-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="b1347-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b1347-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b1347-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b1347-117">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="b1347-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b1347-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b1347-118">E_FAIL</span></span>|<span data-ttu-id="b1347-119">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="b1347-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b1347-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="b1347-120">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b1347-121">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="b1347-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b1347-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b1347-122">Remarks</span></span>  
 <span data-ttu-id="b1347-123">In vielen Szenarien ist es nicht notwendig, aufzurufen `Start` , da die Laufzeit bei der ersten Anforderung zum Ausführen von verwaltetem Code automatisch initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="b1347-123">In many scenarios it is not necessary to call `Start`, because the runtime will initialize itself automatically upon the first request to run managed code.</span></span> <span data-ttu-id="b1347-124">Sie können jedoch verwenden, `Start` um genau anzugeben, wann die Laufzeit initialisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="b1347-124">You can, however, use `Start` to specify exactly when the runtime should be initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1347-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b1347-125">Requirements</span></span>  
 <span data-ttu-id="b1347-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1347-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1347-127">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="b1347-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b1347-128">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b1347-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b1347-129">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1347-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1347-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1347-130">See also</span></span>

- <xref:System.AppDomain>
- [<span data-ttu-id="b1347-131">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b1347-131">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
