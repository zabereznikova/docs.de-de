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
ms.openlocfilehash: d3748621474373fee8248496d48414ff67c699d6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715694"
---
# <a name="icorruntimehostcloseenum-method"></a><span data-ttu-id="7eefc-102">ICorRuntimeHost::CloseEnum-Methode</span><span class="sxs-lookup"><span data-stu-id="7eefc-102">ICorRuntimeHost::CloseEnum Method</span></span>

<span data-ttu-id="7eefc-103">Setzt einen Domänen Enumerator auf den Anfang der Domänen Liste zurück.</span><span class="sxs-lookup"><span data-stu-id="7eefc-103">Resets a domain enumerator back to the beginning of the domain list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7eefc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7eefc-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseEnum (  
    [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7eefc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7eefc-105">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="7eefc-106">in Der zurück zusetzenden Enumerator.</span><span class="sxs-lookup"><span data-stu-id="7eefc-106">[in] The enumerator to reset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7eefc-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7eefc-107">Return Value</span></span>  
  
|<span data-ttu-id="7eefc-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7eefc-108">HRESULT</span></span>|<span data-ttu-id="7eefc-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7eefc-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7eefc-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7eefc-110">S_OK</span></span>|<span data-ttu-id="7eefc-111">Der Vorgang wurde durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="7eefc-111">The operation was successful.</span></span>|  
|<span data-ttu-id="7eefc-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="7eefc-112">S_FALSE</span></span>|<span data-ttu-id="7eefc-113">Der Vorgang konnte nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="7eefc-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="7eefc-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7eefc-114">E_FAIL</span></span>|<span data-ttu-id="7eefc-115">Ein unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="7eefc-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="7eefc-116">Wenn eine Methode E_FAIL zurückgibt, ist die Common Language Runtime (CLR) im Prozess nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="7eefc-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="7eefc-117">Nachfolgende Aufrufe von Hosting-APIs geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="7eefc-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7eefc-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7eefc-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7eefc-119">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="7eefc-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7eefc-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7eefc-120">Requirements</span></span>  

 <span data-ttu-id="7eefc-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7eefc-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7eefc-122">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="7eefc-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7eefc-123">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7eefc-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7eefc-124">**.NET Framework Versionen:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="7eefc-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7eefc-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7eefc-125">See also</span></span>

- [<span data-ttu-id="7eefc-126">CorBindToRuntimeEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="7eefc-126">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)
- [<span data-ttu-id="7eefc-127">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7eefc-127">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
