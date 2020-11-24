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
ms.openlocfilehash: 9342233317535ebecbcddea48b9029b81868eb0c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690147"
---
# <a name="icorruntimehoststop-method"></a><span data-ttu-id="e0aa0-102">ICorRuntimeHost::Stop-Methode</span><span class="sxs-lookup"><span data-stu-id="e0aa0-102">ICorRuntimeHost::Stop Method</span></span>

<span data-ttu-id="e0aa0-103">Beendet die Ausführung von Code in der Laufzeit für den aktuellen Prozess.</span><span class="sxs-lookup"><span data-stu-id="e0aa0-103">Stops the execution of code in the runtime for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0aa0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e0aa0-104">Syntax</span></span>  
  
```cpp  
HRESULT Stop ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e0aa0-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e0aa0-105">Return Value</span></span>  
  
|<span data-ttu-id="e0aa0-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e0aa0-106">HRESULT</span></span>|<span data-ttu-id="e0aa0-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e0aa0-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e0aa0-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="e0aa0-108">S_OK</span></span>|<span data-ttu-id="e0aa0-109">Der Vorgang wurde durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="e0aa0-109">The operation was successful.</span></span>|  
|<span data-ttu-id="e0aa0-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="e0aa0-110">S_FALSE</span></span>|<span data-ttu-id="e0aa0-111">Der Vorgang konnte nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e0aa0-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="e0aa0-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e0aa0-112">E_FAIL</span></span>|<span data-ttu-id="e0aa0-113">Ein unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="e0aa0-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="e0aa0-114">Wenn eine Methode E_FAIL zurückgibt, ist die Common Language Runtime (CLR) im Prozess nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="e0aa0-114">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="e0aa0-115">Nachfolgende Aufrufe von Hosting-APIs geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="e0aa0-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e0aa0-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e0aa0-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e0aa0-117">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="e0aa0-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0aa0-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e0aa0-118">Remarks</span></span>  

 <span data-ttu-id="e0aa0-119">Es ist normalerweise nicht erforderlich, die-Methode aufzurufen `Stop` , da der Code nicht mehr ausgeführt wird, wenn der Prozess beendet wird.</span><span class="sxs-lookup"><span data-stu-id="e0aa0-119">It is typically unnecessary to call the `Stop` method, because the code stops executing when the process exits.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e0aa0-120">Nach einem- `Stop` Aufrufvorgang kann die CLR nicht mehr in demselben Prozess initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="e0aa0-120">After a call to `Stop`, the CLR cannot be reinitialized into the same process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0aa0-121">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e0aa0-121">Requirements</span></span>  

 <span data-ttu-id="e0aa0-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0aa0-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0aa0-123">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="e0aa0-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e0aa0-124">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e0aa0-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e0aa0-125">**.NET Framework Versionen:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="e0aa0-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0aa0-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e0aa0-126">See also</span></span>

- [<span data-ttu-id="e0aa0-127">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e0aa0-127">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
