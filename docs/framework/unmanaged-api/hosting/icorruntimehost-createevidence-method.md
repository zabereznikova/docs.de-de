---
title: ICorRuntimeHost::CreateEvidence-Methode
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateEvidence
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateEvidence
helpviewer_keywords:
- CreateEvidence method [.NET Framework hosting]
- ICorRuntimeHost::CreateEvidence method [.NET Framework hosting]
ms.assetid: e235ea80-b84c-4442-a4c3-fc96c25a8eb9
topic_type:
- apiref
ms.openlocfilehash: 429ce0510162b3256cdf58f4820b04dd80243e29
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139637"
---
# <a name="icorruntimehostcreateevidence-method"></a><span data-ttu-id="c857a-102">ICorRuntimeHost::CreateEvidence-Methode</span><span class="sxs-lookup"><span data-stu-id="c857a-102">ICorRuntimeHost::CreateEvidence Method</span></span>
<span data-ttu-id="c857a-103">Ruft einen Schnittstellen Zeiger vom Typ "<xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>" ab, der dem Host das Erstellen von Sicherheits beweisen ermöglicht, die an die Methode " [kreatedomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) " oder " [kreatedomainex](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) " übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="c857a-103">Gets an interface pointer of type <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>, which allows the host to create security evidence to pass to the [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) or [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c857a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c857a-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateEvidence (  
    [out] IUnknown** pEvidence  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c857a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c857a-105">Parameters</span></span>  
 `pEvidence`  
 <span data-ttu-id="c857a-106">vorgenommen Ein Schnittstellen Zeiger auf eine <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>-Instanz, mit der Sicherheits Beweise erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="c857a-106">[out] A interface pointer to an <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> instance used to create security evidence.</span></span> <span data-ttu-id="c857a-107">Dieser Zeiger ist `IUnknown`typisiert. Daher sollten Aufrufer in der Regel `QueryInterface` auf dieser Schnittstelle aufzurufen, um einen Zeiger auf eine <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="c857a-107">This pointer is typed `IUnknown`, so callers should typically call `QueryInterface` on this interface to obtain a pointer to an <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c857a-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c857a-108">Return Value</span></span>  
  
|<span data-ttu-id="c857a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c857a-109">HRESULT</span></span>|<span data-ttu-id="c857a-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c857a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c857a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c857a-111">S_OK</span></span>|<span data-ttu-id="c857a-112">Der Vorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="c857a-112">The operation was successful.</span></span>|  
|<span data-ttu-id="c857a-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="c857a-113">S_FALSE</span></span>|<span data-ttu-id="c857a-114">Der Vorgang konnte nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c857a-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="c857a-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c857a-115">E_FAIL</span></span>|<span data-ttu-id="c857a-116">Ein unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="c857a-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="c857a-117">Wenn eine Methode E_FAIL zurückgibt, kann die Common Language Runtime (CLR) im Prozess nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c857a-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="c857a-118">Nachfolgende Aufrufe von Hosting-APIs geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="c857a-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c857a-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c857a-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c857a-120">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="c857a-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c857a-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c857a-121">Remarks</span></span>  
 <span data-ttu-id="c857a-122">Diese Methode gibt eine leere Auflistung zurück, die nicht aus nativem Code aufgefüllt werden kann.</span><span class="sxs-lookup"><span data-stu-id="c857a-122">This method returns an empty collection that cannot be populated from native code.</span></span> <span data-ttu-id="c857a-123">Verwenden Sie stattdessen die <xref:System.Security.Policy.Evidence>-Methode.</span><span class="sxs-lookup"><span data-stu-id="c857a-123">You should use the <xref:System.Security.Policy.Evidence> method instead.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c857a-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c857a-124">Requirements</span></span>  
 <span data-ttu-id="c857a-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c857a-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c857a-126">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="c857a-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c857a-127">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c857a-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c857a-128">**.NET Framework Version:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="c857a-128">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c857a-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c857a-129">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="c857a-130">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c857a-130">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
