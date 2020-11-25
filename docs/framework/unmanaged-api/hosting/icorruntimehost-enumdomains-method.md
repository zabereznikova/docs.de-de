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
ms.openlocfilehash: f4338429dc24bf5196b92d3f18e73c98442f61e7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720661"
---
# <a name="icorruntimehostenumdomains-method"></a><span data-ttu-id="009fc-102">ICorRuntimeHost::EnumDomains-Methode</span><span class="sxs-lookup"><span data-stu-id="009fc-102">ICorRuntimeHost::EnumDomains Method</span></span>

<span data-ttu-id="009fc-103">Ruft einen Enumerator für die Domänen im aktuellen Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="009fc-103">Gets an enumerator for the domains in the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="009fc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="009fc-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumDomains (  
    [out] HCORENUM *hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="009fc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="009fc-105">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="009fc-106">vorgenommen Ein Enumerator für die Domänen.</span><span class="sxs-lookup"><span data-stu-id="009fc-106">[out] An enumerator for the domains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="009fc-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="009fc-107">Return Value</span></span>  
  
|<span data-ttu-id="009fc-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="009fc-108">HRESULT</span></span>|<span data-ttu-id="009fc-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="009fc-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="009fc-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="009fc-110">S_OK</span></span>|<span data-ttu-id="009fc-111">Der Vorgang wurde durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="009fc-111">The operation was successful.</span></span>|  
|<span data-ttu-id="009fc-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="009fc-112">S_FALSE</span></span>|<span data-ttu-id="009fc-113">Der Vorgang konnte nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="009fc-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="009fc-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="009fc-114">E_FAIL</span></span>|<span data-ttu-id="009fc-115">Ein unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="009fc-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="009fc-116">Wenn eine Methode E_FAIL zurückgibt, ist die Common Language Runtime (CLR) im Prozess nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="009fc-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="009fc-117">Nachfolgende Aufrufe von Hosting-APIs geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="009fc-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="009fc-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="009fc-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="009fc-119">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="009fc-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="009fc-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="009fc-120">Requirements</span></span>  

 <span data-ttu-id="009fc-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="009fc-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="009fc-122">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="009fc-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="009fc-123">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="009fc-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="009fc-124">**.NET Framework Version:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="009fc-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="009fc-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="009fc-125">See also</span></span>

- [<span data-ttu-id="009fc-126">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="009fc-126">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
