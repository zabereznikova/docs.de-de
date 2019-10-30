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
ms.openlocfilehash: 6dc25cbeef2576a2ecc6ec39b2cb3f9abb7b9964
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139551"
---
# <a name="icorruntimehostgetdefaultdomain-method"></a><span data-ttu-id="34623-102">ICorRuntimeHost::GetDefaultDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="34623-102">ICorRuntimeHost::GetDefaultDomain Method</span></span>
<span data-ttu-id="34623-103">Ruft einen Schnittstellen Zeiger vom Typ <xref:System._AppDomain?displayProperty=nameWithType> ab, der die Standard Domäne für den aktuellen Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="34623-103">Gets an interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType> that represents the default domain for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34623-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="34623-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDefaultDomain (  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34623-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="34623-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="34623-106">vorgenommen Ein Schnittstellen Zeiger vom Typ <xref:System._AppDomain?displayProperty=nameWithType> auf die <xref:System.AppDomain> Instanz, die die Standard Anwendungsdomäne für den Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="34623-106">[out] An interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType> to the <xref:System.AppDomain> instance that represents the default application domain for the process.</span></span>  
  
 <span data-ttu-id="34623-107">Dieser Zeiger ist `IUnknown`typisiert. Daher sollten Aufrufer im allgemeinen `QueryInterface` abrufen, um einen Schnittstellen Zeiger vom Typ <xref:System._AppDomain?displayProperty=nameWithType>zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="34623-107">This pointer is typed `IUnknown`, so callers should generally call `QueryInterface` to obtain an interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="34623-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="34623-108">Return Value</span></span>  
  
|<span data-ttu-id="34623-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="34623-109">HRESULT</span></span>|<span data-ttu-id="34623-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="34623-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="34623-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="34623-111">S_OK</span></span>|<span data-ttu-id="34623-112">Der Vorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="34623-112">The operation was successful.</span></span>|  
|<span data-ttu-id="34623-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="34623-113">S_FALSE</span></span>|<span data-ttu-id="34623-114">Der Vorgang konnte nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="34623-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="34623-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="34623-115">E_FAIL</span></span>|<span data-ttu-id="34623-116">Ein unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="34623-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="34623-117">Wenn eine Methode E_FAIL zurückgibt, kann die Common Language Runtime (CLR) im Prozess nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="34623-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="34623-118">Nachfolgende Aufrufe von Hosting-APIs geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="34623-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="34623-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="34623-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="34623-120">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="34623-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="34623-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="34623-121">Requirements</span></span>  
 <span data-ttu-id="34623-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34623-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34623-123">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="34623-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="34623-124">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="34623-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="34623-125">**.NET Framework Versionen:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="34623-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34623-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="34623-126">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="34623-127">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="34623-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
