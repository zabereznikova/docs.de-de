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
ms.openlocfilehash: a97471e1c257902633b7eb363c3cc51288c70917
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762252"
---
# <a name="icorruntimehostenumdomains-method"></a><span data-ttu-id="0dda7-102">ICorRuntimeHost::EnumDomains-Methode</span><span class="sxs-lookup"><span data-stu-id="0dda7-102">ICorRuntimeHost::EnumDomains Method</span></span>
<span data-ttu-id="0dda7-103">Ruft einen Enumerator für die Domänen im aktuellen Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="0dda7-103">Gets an enumerator for the domains in the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0dda7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0dda7-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumDomains (  
    [out] HCORENUM *hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0dda7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0dda7-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="0dda7-106">vorgenommen Ein Enumerator für die Domänen.</span><span class="sxs-lookup"><span data-stu-id="0dda7-106">[out] An enumerator for the domains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0dda7-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0dda7-107">Return Value</span></span>  
  
|<span data-ttu-id="0dda7-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0dda7-108">HRESULT</span></span>|<span data-ttu-id="0dda7-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0dda7-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0dda7-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0dda7-110">S_OK</span></span>|<span data-ttu-id="0dda7-111">Der Vorgang wurde durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="0dda7-111">The operation was successful.</span></span>|  
|<span data-ttu-id="0dda7-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="0dda7-112">S_FALSE</span></span>|<span data-ttu-id="0dda7-113">Der Vorgang konnte nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0dda7-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="0dda7-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0dda7-114">E_FAIL</span></span>|<span data-ttu-id="0dda7-115">Ein unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0dda7-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="0dda7-116">Wenn eine Methode E_FAIL zurückgibt, ist die Common Language Runtime (CLR) im Prozess nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="0dda7-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="0dda7-117">Nachfolgende Aufrufe von Hosting-APIs geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="0dda7-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0dda7-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0dda7-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0dda7-119">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="0dda7-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0dda7-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0dda7-120">Requirements</span></span>  
 <span data-ttu-id="0dda7-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0dda7-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0dda7-122">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="0dda7-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0dda7-123">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0dda7-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0dda7-124">**.NET Framework Version:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="0dda7-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dda7-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0dda7-125">See also</span></span>

- [<span data-ttu-id="0dda7-126">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0dda7-126">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
