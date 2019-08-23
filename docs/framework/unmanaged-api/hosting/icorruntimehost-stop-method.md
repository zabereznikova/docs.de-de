---
title: ICorRuntimeHost::Stop-Methode
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.Stop
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::Stop
helpviewer_keywords:
- Stop method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::Stop method [.NET Framework hosting]
ms.assetid: 46a0d450-b516-4bef-8b71-8d3bf265cbed
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca51b87e7afc8e9e48d541a32b3bd60a19a5ff70
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965969"
---
# <a name="icorruntimehoststop-method"></a><span data-ttu-id="f3ea2-102">ICorRuntimeHost::Stop-Methode</span><span class="sxs-lookup"><span data-stu-id="f3ea2-102">ICorRuntimeHost::Stop Method</span></span>
<span data-ttu-id="f3ea2-103">Beendet die Ausführung von Code in der Laufzeit für den aktuellen Prozess.</span><span class="sxs-lookup"><span data-stu-id="f3ea2-103">Stops the execution of code in the runtime for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3ea2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f3ea2-104">Syntax</span></span>  
  
```cpp  
HRESULT Stop ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f3ea2-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f3ea2-105">Return Value</span></span>  
  
|<span data-ttu-id="f3ea2-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f3ea2-106">HRESULT</span></span>|<span data-ttu-id="f3ea2-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f3ea2-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f3ea2-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="f3ea2-108">S_OK</span></span>|<span data-ttu-id="f3ea2-109">Der Vorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="f3ea2-109">The operation was successful.</span></span>|  
|<span data-ttu-id="f3ea2-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="f3ea2-110">S_FALSE</span></span>|<span data-ttu-id="f3ea2-111">Der Vorgang konnte nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f3ea2-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="f3ea2-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f3ea2-112">E_FAIL</span></span>|<span data-ttu-id="f3ea2-113">Ein unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="f3ea2-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="f3ea2-114">Wenn eine Methode E_FAIL zurückgibt, kann die Common Language Runtime (CLR) im Prozess nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f3ea2-114">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="f3ea2-115">Nachfolgende Aufrufe von Hosting-APIs geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="f3ea2-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f3ea2-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f3ea2-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f3ea2-117">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="f3ea2-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3ea2-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f3ea2-118">Remarks</span></span>  
 <span data-ttu-id="f3ea2-119">Es ist normalerweise nicht erforderlich, `Stop` die-Methode aufzurufen, da der Code nicht mehr ausgeführt wird, wenn der Prozess beendet wird.</span><span class="sxs-lookup"><span data-stu-id="f3ea2-119">It is typically unnecessary to call the `Stop` method, because the code stops executing when the process exits.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f3ea2-120">Nach einem-Aufrufvorgang `Stop`kann die CLR nicht mehr in demselben Prozess initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="f3ea2-120">After a call to `Stop`, the CLR cannot be reinitialized into the same process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3ea2-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f3ea2-121">Requirements</span></span>  
 <span data-ttu-id="f3ea2-122">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3ea2-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3ea2-123">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f3ea2-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f3ea2-124">**Fern** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f3ea2-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f3ea2-125">**.NET Framework Versionen:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="f3ea2-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3ea2-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f3ea2-126">See also</span></span>

- [<span data-ttu-id="f3ea2-127">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f3ea2-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
