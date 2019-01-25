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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dd59b08537ebc49068b92d229f3ccab6e7280ace
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54591564"
---
# <a name="icorruntimehostcloseenum-method"></a><span data-ttu-id="15df2-102">ICorRuntimeHost::CloseEnum-Methode</span><span class="sxs-lookup"><span data-stu-id="15df2-102">ICorRuntimeHost::CloseEnum Method</span></span>
<span data-ttu-id="15df2-103">Setzt einen Domänenenumerator wieder an den Anfang der Domänenliste aus.</span><span class="sxs-lookup"><span data-stu-id="15df2-103">Resets a domain enumerator back to the beginning of the domain list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15df2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="15df2-104">Syntax</span></span>  
  
```  
HRESULT CloseEnum (  
    [in] HCORENUM hEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="15df2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="15df2-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="15df2-106">[in] Der Enumerator zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="15df2-106">[in] The enumerator to reset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="15df2-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="15df2-107">Return Value</span></span>  
  
|<span data-ttu-id="15df2-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="15df2-108">HRESULT</span></span>|<span data-ttu-id="15df2-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15df2-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="15df2-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="15df2-110">S_OK</span></span>|<span data-ttu-id="15df2-111">Der Vorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="15df2-111">The operation was successful.</span></span>|  
|<span data-ttu-id="15df2-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="15df2-112">S_FALSE</span></span>|<span data-ttu-id="15df2-113">Der Vorgang konnte nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="15df2-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="15df2-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="15df2-114">E_FAIL</span></span>|<span data-ttu-id="15df2-115">Ein Unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="15df2-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="15df2-116">Wenn eine Methode E_FAIL zurückgegeben wird, ist die common Language Runtime (CLR) nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="15df2-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="15df2-117">Nachfolgende Aufrufe von hosting-APIs HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="15df2-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="15df2-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="15df2-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="15df2-119">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="15df2-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="15df2-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="15df2-120">Requirements</span></span>  
 <span data-ttu-id="15df2-121">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15df2-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15df2-122">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="15df2-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="15df2-123">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="15df2-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="15df2-124">**.NET Framework-Versionen:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="15df2-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15df2-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="15df2-125">See also</span></span>
- [<span data-ttu-id="15df2-126">CorBindToRuntimeEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="15df2-126">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="15df2-127">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="15df2-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
