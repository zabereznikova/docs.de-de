---
title: ICorRuntimeHost::CloseEnum-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 677ab3a97b7fcceccd8ceb0943c62df8bc999649
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorruntimehostcloseenum-method"></a><span data-ttu-id="d137f-102">ICorRuntimeHost::CloseEnum-Methode</span><span class="sxs-lookup"><span data-stu-id="d137f-102">ICorRuntimeHost::CloseEnum Method</span></span>
<span data-ttu-id="d137f-103">Setzt einen Domänenenumerator wieder an den Anfang der Domänenliste aus.</span><span class="sxs-lookup"><span data-stu-id="d137f-103">Resets a domain enumerator back to the beginning of the domain list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d137f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d137f-104">Syntax</span></span>  
  
```  
HRESULT CloseEnum (  
    [in] HCORENUM hEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d137f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d137f-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="d137f-106">[in] Der Enumerator zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="d137f-106">[in] The enumerator to reset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d137f-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d137f-107">Return Value</span></span>  
  
|<span data-ttu-id="d137f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d137f-108">HRESULT</span></span>|<span data-ttu-id="d137f-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d137f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d137f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d137f-110">S_OK</span></span>|<span data-ttu-id="d137f-111">Der Vorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="d137f-111">The operation was successful.</span></span>|  
|<span data-ttu-id="d137f-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="d137f-112">S_FALSE</span></span>|<span data-ttu-id="d137f-113">Der Vorgang konnte nicht abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="d137f-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="d137f-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d137f-114">E_FAIL</span></span>|<span data-ttu-id="d137f-115">Ein Unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="d137f-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="d137f-116">Wenn eine Methode E_FAIL zurückgibt, ist die common Language Runtime (CLR) nicht mehr im Prozess verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="d137f-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="d137f-117">Nachfolgende Aufrufe hosting-APIs HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="d137f-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d137f-118">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="d137f-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d137f-119">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="d137f-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d137f-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d137f-120">Requirements</span></span>  
 <span data-ttu-id="d137f-121">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d137f-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d137f-122">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d137f-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d137f-123">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d137f-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d137f-124">**.NET Framework-Versionen:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="d137f-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d137f-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d137f-125">See Also</span></span>  
 [<span data-ttu-id="d137f-126">CorBindToRuntimeEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="d137f-126">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [<span data-ttu-id="d137f-127">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d137f-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
