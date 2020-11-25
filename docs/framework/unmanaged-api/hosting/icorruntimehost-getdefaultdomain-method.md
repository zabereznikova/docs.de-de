---
title: ICorRuntimeHost::GetDefaultDomain-Methode
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.GetDefaultDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::GetDefaultDomain
helpviewer_keywords:
- ICorRuntimeHost::GetDefaultDomain method [.NET Framework hosting]
- GetDefaultDomain method [.NET Framework hosting]
ms.assetid: 5e17a6fc-f335-4aae-9bb0-c3e1271a9426
topic_type:
- apiref
ms.openlocfilehash: 673c32c86c808c36db6454b8a9f0d8e68f9b1258
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720632"
---
# <a name="icorruntimehostgetdefaultdomain-method"></a><span data-ttu-id="f5fd8-102">ICorRuntimeHost::GetDefaultDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="f5fd8-102">ICorRuntimeHost::GetDefaultDomain Method</span></span>

<span data-ttu-id="f5fd8-103">Ruft einen Schnittstellen Zeiger vom Typ ab <xref:System._AppDomain?displayProperty=nameWithType> , der die Standard Domäne für den aktuellen Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="f5fd8-103">Gets an interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType> that represents the default domain for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5fd8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f5fd8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDefaultDomain (  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5fd8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f5fd8-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="f5fd8-106">vorgenommen Ein Schnittstellen Zeiger vom Typ <xref:System._AppDomain?displayProperty=nameWithType> für die- <xref:System.AppDomain> Instanz, die die Standard Anwendungsdomäne für den Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="f5fd8-106">[out] An interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType> to the <xref:System.AppDomain> instance that represents the default application domain for the process.</span></span>  
  
 <span data-ttu-id="f5fd8-107">Dieser Zeiger ist typisiert. `IUnknown` daher sollten Aufrufer im allgemeinen aufzurufen, `QueryInterface` um einen Schnittstellen Zeiger vom Typ zu erhalten <xref:System._AppDomain?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="f5fd8-107">This pointer is typed `IUnknown`, so callers should generally call `QueryInterface` to obtain an interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f5fd8-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f5fd8-108">Return Value</span></span>  
  
|<span data-ttu-id="f5fd8-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f5fd8-109">HRESULT</span></span>|<span data-ttu-id="f5fd8-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f5fd8-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f5fd8-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="f5fd8-111">S_OK</span></span>|<span data-ttu-id="f5fd8-112">Der Vorgang wurde durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="f5fd8-112">The operation was successful.</span></span>|  
|<span data-ttu-id="f5fd8-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="f5fd8-113">S_FALSE</span></span>|<span data-ttu-id="f5fd8-114">Der Vorgang konnte nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f5fd8-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="f5fd8-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f5fd8-115">E_FAIL</span></span>|<span data-ttu-id="f5fd8-116">Ein unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="f5fd8-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="f5fd8-117">Wenn eine Methode E_FAIL zurückgibt, ist die Common Language Runtime (CLR) im Prozess nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="f5fd8-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="f5fd8-118">Nachfolgende Aufrufe von Hosting-APIs geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="f5fd8-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f5fd8-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f5fd8-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f5fd8-120">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="f5fd8-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f5fd8-121">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f5fd8-121">Requirements</span></span>  

 <span data-ttu-id="f5fd8-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5fd8-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5fd8-123">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="f5fd8-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f5fd8-124">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f5fd8-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f5fd8-125">**.NET Framework Versionen:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="f5fd8-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5fd8-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f5fd8-126">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="f5fd8-127">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f5fd8-127">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
