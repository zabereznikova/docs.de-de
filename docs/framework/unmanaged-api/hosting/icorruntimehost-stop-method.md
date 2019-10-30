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
ms.openlocfilehash: 5fcf8bc861b2ef0b8ea9f5a5e46585564cc26615
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127700"
---
# <a name="icorruntimehoststop-method"></a><span data-ttu-id="3ffee-102">ICorRuntimeHost::Stop-Methode</span><span class="sxs-lookup"><span data-stu-id="3ffee-102">ICorRuntimeHost::Stop Method</span></span>
<span data-ttu-id="3ffee-103">Beendet die Ausführung von Code in der Laufzeit für den aktuellen Prozess.</span><span class="sxs-lookup"><span data-stu-id="3ffee-103">Stops the execution of code in the runtime for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ffee-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3ffee-104">Syntax</span></span>  
  
```cpp  
HRESULT Stop ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="3ffee-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3ffee-105">Return Value</span></span>  
  
|<span data-ttu-id="3ffee-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3ffee-106">HRESULT</span></span>|<span data-ttu-id="3ffee-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3ffee-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3ffee-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="3ffee-108">S_OK</span></span>|<span data-ttu-id="3ffee-109">Der Vorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="3ffee-109">The operation was successful.</span></span>|  
|<span data-ttu-id="3ffee-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="3ffee-110">S_FALSE</span></span>|<span data-ttu-id="3ffee-111">Der Vorgang konnte nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3ffee-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="3ffee-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3ffee-112">E_FAIL</span></span>|<span data-ttu-id="3ffee-113">Ein unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="3ffee-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="3ffee-114">Wenn eine Methode E_FAIL zurückgibt, kann die Common Language Runtime (CLR) im Prozess nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3ffee-114">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="3ffee-115">Nachfolgende Aufrufe von Hosting-APIs geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="3ffee-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3ffee-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3ffee-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3ffee-117">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="3ffee-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ffee-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3ffee-118">Remarks</span></span>  
 <span data-ttu-id="3ffee-119">Es ist in der Regel nicht erforderlich, die `Stop`-Methode aufzurufen, da der Code beim Beenden des Prozesses beendet wird.</span><span class="sxs-lookup"><span data-stu-id="3ffee-119">It is typically unnecessary to call the `Stop` method, because the code stops executing when the process exits.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3ffee-120">Nach einem `Stop`-Aufrufvorgang kann die CLR nicht in demselben Prozess erneut initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="3ffee-120">After a call to `Stop`, the CLR cannot be reinitialized into the same process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ffee-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3ffee-121">Requirements</span></span>  
 <span data-ttu-id="3ffee-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ffee-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ffee-123">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="3ffee-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3ffee-124">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3ffee-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3ffee-125">**.NET Framework Versionen:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="3ffee-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ffee-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ffee-126">See also</span></span>

- [<span data-ttu-id="3ffee-127">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3ffee-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
