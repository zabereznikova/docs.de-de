---
title: ICorRuntimeHost::CloseEnum-Methode
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CloseEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CloseEnum
helpviewer_keywords:
- CloseEnum method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::CloseEnum method [.NET Framework hosting]
ms.assetid: f7ce7e8c-0a3e-4587-a180-063e2b85940e
topic_type:
- apiref
ms.openlocfilehash: e2eddfab68e5c9e2ebffe2c96c9348f3cd799c7f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127754"
---
# <a name="icorruntimehostcloseenum-method"></a><span data-ttu-id="e35eb-102">ICorRuntimeHost::CloseEnum-Methode</span><span class="sxs-lookup"><span data-stu-id="e35eb-102">ICorRuntimeHost::CloseEnum Method</span></span>
<span data-ttu-id="e35eb-103">Setzt einen Domänen Enumerator auf den Anfang der Domänen Liste zurück.</span><span class="sxs-lookup"><span data-stu-id="e35eb-103">Resets a domain enumerator back to the beginning of the domain list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e35eb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e35eb-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseEnum (  
    [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e35eb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e35eb-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="e35eb-106">in Der zurück zusetzenden Enumerator.</span><span class="sxs-lookup"><span data-stu-id="e35eb-106">[in] The enumerator to reset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e35eb-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e35eb-107">Return Value</span></span>  
  
|<span data-ttu-id="e35eb-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e35eb-108">HRESULT</span></span>|<span data-ttu-id="e35eb-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e35eb-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e35eb-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e35eb-110">S_OK</span></span>|<span data-ttu-id="e35eb-111">Der Vorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="e35eb-111">The operation was successful.</span></span>|  
|<span data-ttu-id="e35eb-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="e35eb-112">S_FALSE</span></span>|<span data-ttu-id="e35eb-113">Der Vorgang konnte nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e35eb-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="e35eb-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e35eb-114">E_FAIL</span></span>|<span data-ttu-id="e35eb-115">Ein unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="e35eb-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="e35eb-116">Wenn eine Methode E_FAIL zurückgibt, kann die Common Language Runtime (CLR) im Prozess nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e35eb-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="e35eb-117">Nachfolgende Aufrufe von Hosting-APIs geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="e35eb-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e35eb-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e35eb-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e35eb-119">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="e35eb-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e35eb-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e35eb-120">Requirements</span></span>  
 <span data-ttu-id="e35eb-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e35eb-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e35eb-122">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="e35eb-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e35eb-123">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e35eb-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e35eb-124">**.NET Framework Versionen:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="e35eb-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e35eb-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e35eb-125">See also</span></span>

- [<span data-ttu-id="e35eb-126">CorBindToRuntimeEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="e35eb-126">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="e35eb-127">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e35eb-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
