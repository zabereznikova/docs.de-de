---
title: ICorRuntimeHost::Start-Methode
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::Start
helpviewer_keywords:
- Start method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::Start method [.NET Framework hosting]
ms.assetid: c66f3ac5-6489-484a-9bed-c31b711cee01
topic_type:
- apiref
ms.openlocfilehash: c450d83669a3bc548c15ed5800dc73438b9a84a6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127695"
---
# <a name="icorruntimehoststart-method"></a><span data-ttu-id="057dc-102">ICorRuntimeHost::Start-Methode</span><span class="sxs-lookup"><span data-stu-id="057dc-102">ICorRuntimeHost::Start Method</span></span>
<span data-ttu-id="057dc-103">Startet die Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="057dc-103">Starts the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="057dc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="057dc-104">Syntax</span></span>  
  
```cpp  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="057dc-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="057dc-105">Return Value</span></span>  
  
|<span data-ttu-id="057dc-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="057dc-106">HRESULT</span></span>|<span data-ttu-id="057dc-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="057dc-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="057dc-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="057dc-108">S_OK</span></span>|<span data-ttu-id="057dc-109">Der Vorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="057dc-109">The operation was successful.</span></span>|  
|<span data-ttu-id="057dc-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="057dc-110">S_FALSE</span></span>|<span data-ttu-id="057dc-111">Der Vorgang konnte nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="057dc-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="057dc-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="057dc-112">E_FAIL</span></span>|<span data-ttu-id="057dc-113">Ein unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="057dc-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="057dc-114">Wenn eine Methode E_FAIL zurückgibt, kann die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="057dc-114">If a method returns E_FAIL, the CLR is no longer usable in the process.</span></span> <span data-ttu-id="057dc-115">Nachfolgende Aufrufe von Hosting-APIs geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="057dc-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="057dc-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="057dc-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="057dc-117">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="057dc-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="057dc-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="057dc-118">Remarks</span></span>  
 <span data-ttu-id="057dc-119">Es ist in der Regel nicht notwendig, die `Start`-Methode aufzurufen, da die CLR bei der ersten Anforderung zum Ausführen von verwaltetem Code automatisch startet.</span><span class="sxs-lookup"><span data-stu-id="057dc-119">It is typically not necessary to call the `Start` method, because the CLR starts automatically upon the first request to run managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="057dc-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="057dc-120">Requirements</span></span>  
 <span data-ttu-id="057dc-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="057dc-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="057dc-122">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="057dc-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="057dc-123">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="057dc-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="057dc-124">**.NET Framework Versionen:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="057dc-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="057dc-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="057dc-125">See also</span></span>

- [<span data-ttu-id="057dc-126">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="057dc-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
