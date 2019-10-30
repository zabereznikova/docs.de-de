---
title: ICorRuntimeHost::EnumDomains-Methode
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.EnumDomains
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::EnumDomains
helpviewer_keywords:
- ICorRuntimeHost::EnumDomains method [.NET Framework hosting]
- EnumDomains method [.NET Framework hosting]
ms.assetid: 96b74995-0cde-4876-b6df-7fc164e6a5d1
topic_type:
- apiref
ms.openlocfilehash: e5a1642f968228c5815732ecd470cb8f02a0eb83
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139586"
---
# <a name="icorruntimehostenumdomains-method"></a><span data-ttu-id="d3a0e-102">ICorRuntimeHost::EnumDomains-Methode</span><span class="sxs-lookup"><span data-stu-id="d3a0e-102">ICorRuntimeHost::EnumDomains Method</span></span>
<span data-ttu-id="d3a0e-103">Ruft einen Enumerator für die Domänen im aktuellen Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="d3a0e-103">Gets an enumerator for the domains in the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3a0e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d3a0e-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumDomains (  
    [out] HCORENUM *hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3a0e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d3a0e-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="d3a0e-106">vorgenommen Ein Enumerator für die Domänen.</span><span class="sxs-lookup"><span data-stu-id="d3a0e-106">[out] An enumerator for the domains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d3a0e-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d3a0e-107">Return Value</span></span>  
  
|<span data-ttu-id="d3a0e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d3a0e-108">HRESULT</span></span>|<span data-ttu-id="d3a0e-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d3a0e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d3a0e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d3a0e-110">S_OK</span></span>|<span data-ttu-id="d3a0e-111">Der Vorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="d3a0e-111">The operation was successful.</span></span>|  
|<span data-ttu-id="d3a0e-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="d3a0e-112">S_FALSE</span></span>|<span data-ttu-id="d3a0e-113">Der Vorgang konnte nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d3a0e-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="d3a0e-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d3a0e-114">E_FAIL</span></span>|<span data-ttu-id="d3a0e-115">Ein unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="d3a0e-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="d3a0e-116">Wenn eine Methode E_FAIL zurückgibt, kann die Common Language Runtime (CLR) im Prozess nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d3a0e-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="d3a0e-117">Nachfolgende Aufrufe von Hosting-APIs geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="d3a0e-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d3a0e-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d3a0e-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d3a0e-119">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="d3a0e-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d3a0e-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d3a0e-120">Requirements</span></span>  
 <span data-ttu-id="d3a0e-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3a0e-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3a0e-122">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="d3a0e-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d3a0e-123">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d3a0e-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d3a0e-124">**.NET Framework Version:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="d3a0e-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3a0e-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d3a0e-125">See also</span></span>

- [<span data-ttu-id="d3a0e-126">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d3a0e-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
