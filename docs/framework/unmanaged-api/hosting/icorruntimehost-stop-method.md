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
ms.openlocfilehash: b1af01559e65bd80fc62cb2eba44bf21d4fa3113
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770912"
---
# <a name="icorruntimehoststop-method"></a><span data-ttu-id="7ba4a-102">ICorRuntimeHost::Stop-Methode</span><span class="sxs-lookup"><span data-stu-id="7ba4a-102">ICorRuntimeHost::Stop Method</span></span>
<span data-ttu-id="7ba4a-103">Beendet die Ausführung von Code in der Runtime für den aktuellen Prozess an.</span><span class="sxs-lookup"><span data-stu-id="7ba4a-103">Stops the execution of code in the runtime for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ba4a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7ba4a-104">Syntax</span></span>  
  
```cpp  
HRESULT Stop ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="7ba4a-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7ba4a-105">Return Value</span></span>  
  
|<span data-ttu-id="7ba4a-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7ba4a-106">HRESULT</span></span>|<span data-ttu-id="7ba4a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7ba4a-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7ba4a-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="7ba4a-108">S_OK</span></span>|<span data-ttu-id="7ba4a-109">Der Vorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="7ba4a-109">The operation was successful.</span></span>|  
|<span data-ttu-id="7ba4a-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="7ba4a-110">S_FALSE</span></span>|<span data-ttu-id="7ba4a-111">Der Vorgang konnte nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="7ba4a-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="7ba4a-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7ba4a-112">E_FAIL</span></span>|<span data-ttu-id="7ba4a-113">Ein Unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="7ba4a-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="7ba4a-114">Wenn eine Methode E_FAIL zurückgegeben wird, ist die common Language Runtime (CLR) nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7ba4a-114">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="7ba4a-115">Nachfolgende Aufrufe von hosting-APIs HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="7ba4a-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7ba4a-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7ba4a-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7ba4a-117">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="7ba4a-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ba4a-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7ba4a-118">Remarks</span></span>  
 <span data-ttu-id="7ba4a-119">Ist in der Regel nicht erforderlich, zum Aufrufen der `Stop` -Methode, da der Code unterbrochen ausgeführt wird, wenn der Prozess beendet wird.</span><span class="sxs-lookup"><span data-stu-id="7ba4a-119">It is typically unnecessary to call the `Stop` method, because the code stops executing when the process exits.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7ba4a-120">Nach einem Aufruf von `Stop`, die CLR kann nicht erneut initialisiert werden, in den gleichen Prozess.</span><span class="sxs-lookup"><span data-stu-id="7ba4a-120">After a call to `Stop`, the CLR cannot be reinitialized into the same process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ba4a-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7ba4a-121">Requirements</span></span>  
 <span data-ttu-id="7ba4a-122">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ba4a-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ba4a-123">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7ba4a-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7ba4a-124">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7ba4a-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7ba4a-125">**.NET Framework-Versionen:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="7ba4a-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ba4a-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7ba4a-126">See also</span></span>

- [<span data-ttu-id="7ba4a-127">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7ba4a-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
