---
title: ICorRuntimeHost::NextDomain-Methode
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.NextDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::NextDomain
helpviewer_keywords:
- ICorRuntimeHost::NextDomain method [.NET Framework hosting]
- NextDomain method [.NET Framework hosting]
ms.assetid: fe07a05b-f6d6-44b5-ab01-b9a6eb15c350
topic_type:
- apiref
ms.openlocfilehash: 598c46d50d7b4a67c1b2c0d844c9b12deb12a428
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671368"
---
# <a name="icorruntimehostnextdomain-method"></a><span data-ttu-id="ba8e4-102">ICorRuntimeHost::NextDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="ba8e4-102">ICorRuntimeHost::NextDomain Method</span></span>

<span data-ttu-id="ba8e4-103">Ruft einen Schnittstellen Zeiger auf die nächste Domäne in der-Enumeration ab.</span><span class="sxs-lookup"><span data-stu-id="ba8e4-103">Gets an interface pointer to the next domain in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba8e4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ba8e4-104">Syntax</span></span>  
  
```cpp  
HRESULT NextDomain (  
    [in] HCORENUM hEnum,  
    [out] void** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba8e4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ba8e4-105">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="ba8e4-106">in Der Enumerator, der durch einen aufzurufenden [Enumerator](icorruntimehost-enumdomains-method.md)abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="ba8e4-106">[in] The enumerator that was obtained through a call to [EnumDomains](icorruntimehost-enumdomains-method.md).</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="ba8e4-107">vorgenommen Ein Schnittstellen Zeiger auf den <xref:System._AppDomain?displayProperty=nameWithType> Typ, der die nächste Domäne in der Enumeration darstellt, oder NULL, wenn keine weiteren Domänen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="ba8e4-107">[out] An interface pointer to the <xref:System._AppDomain?displayProperty=nameWithType> type that represents the next domain in the enumeration, or null, if no more domains exist.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ba8e4-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ba8e4-108">Return Value</span></span>  
  
|<span data-ttu-id="ba8e4-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ba8e4-109">HRESULT</span></span>|<span data-ttu-id="ba8e4-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ba8e4-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ba8e4-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ba8e4-111">S_OK</span></span>|<span data-ttu-id="ba8e4-112">Der Vorgang wurde durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="ba8e4-112">The operation was successful.</span></span>|  
|<span data-ttu-id="ba8e4-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="ba8e4-113">S_FALSE</span></span>|<span data-ttu-id="ba8e4-114">Der Vorgang konnte nicht ausgeführt werden, oder es sind keine weiteren Domänen in der Enumeration vorhanden.</span><span class="sxs-lookup"><span data-stu-id="ba8e4-114">The operation failed to complete, or there are no more domains in the enumeration.</span></span>|  
|<span data-ttu-id="ba8e4-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ba8e4-115">E_FAIL</span></span>|<span data-ttu-id="ba8e4-116">Ein unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="ba8e4-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="ba8e4-117">Wenn eine Methode E_FAIL zurückgibt, ist die Common Language Runtime (CLR) im Prozess nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="ba8e4-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="ba8e4-118">Nachfolgende Aufrufe von Hosting-APIs geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="ba8e4-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ba8e4-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ba8e4-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ba8e4-120">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="ba8e4-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ba8e4-121">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ba8e4-121">Requirements</span></span>  

 <span data-ttu-id="ba8e4-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba8e4-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba8e4-123">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="ba8e4-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ba8e4-124">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ba8e4-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ba8e4-125">**.NET Framework Versionen:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="ba8e4-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba8e4-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ba8e4-126">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="ba8e4-127">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ba8e4-127">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
