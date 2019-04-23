---
title: ICorRuntimeHost::CreateDomainSetup-Methode
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomainSetup
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomainSetup
helpviewer_keywords:
- CreateDomainSetup method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomainSetup method [.NET Framework hosting]
ms.assetid: c21dab60-fb65-47d9-8a94-7fd47ca53b48
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 88f5de9882f8a029769d0ccbdac21aec541582a4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59157364"
---
# <a name="icorruntimehostcreatedomainsetup-method"></a><span data-ttu-id="25658-102">ICorRuntimeHost::CreateDomainSetup-Methode</span><span class="sxs-lookup"><span data-stu-id="25658-102">ICorRuntimeHost::CreateDomainSetup Method</span></span>
<span data-ttu-id="25658-103">Ruft ein Schnittstellenzeiger geben IAppDomainSetup auf eine <xref:System.AppDomainSetup?displayProperty=nameWithType> Instanz.</span><span class="sxs-lookup"><span data-stu-id="25658-103">Gets an interface pointer of type IAppDomainSetup to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="25658-104">`IAppDomainSetup` Stellt Methoden zum Aspekte einer Anwendungsdomäne zu konfigurieren, bevor es erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="25658-104">`IAppDomainSetup` provides methods to configure aspects of an application domain before it is created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25658-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="25658-105">Syntax</span></span>  
  
```  
HRESULT CreateDomainSetup (  
    [out] IUnknown** pAppDomainSetup  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25658-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="25658-106">Parameters</span></span>  
 `pAppDomainSetup`  
 <span data-ttu-id="25658-107">[out] Einen Schnittstellenzeiger auf ein <xref:System.AppDomainSetup?displayProperty=nameWithType> Instanz.</span><span class="sxs-lookup"><span data-stu-id="25658-107">[out] An interface pointer to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="25658-108">Dieser Parameter wird als typisiert `IUnknown`, sodass Aufrufer, in der Regel aufrufen müssen `QueryInterface` für diesen Zeiger auf einen Schnittstellenzeiger des Typs erhalten `IAppDomainSetup`.</span><span class="sxs-lookup"><span data-stu-id="25658-108">This parameter is typed as `IUnknown`, so callers should generally call `QueryInterface` on this pointer to obtain an interface pointer of type `IAppDomainSetup`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="25658-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="25658-109">Return Value</span></span>  
  
|<span data-ttu-id="25658-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="25658-110">HRESULT</span></span>|<span data-ttu-id="25658-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="25658-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="25658-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="25658-112">S_OK</span></span>|<span data-ttu-id="25658-113">Der Vorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="25658-113">The operation was successful.</span></span>|  
|<span data-ttu-id="25658-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="25658-114">S_FALSE</span></span>|<span data-ttu-id="25658-115">Der Vorgang konnte nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="25658-115">The operation failed to complete.</span></span>|  
|<span data-ttu-id="25658-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="25658-116">E_FAIL</span></span>|<span data-ttu-id="25658-117">Ein Unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="25658-117">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="25658-118">Wenn eine Methode E_FAIL zurückgegeben wird, ist die common Language Runtime (CLR) nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="25658-118">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="25658-119">Nachfolgende Aufrufe von hosting-APIs HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="25658-119">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="25658-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="25658-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="25658-121">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="25658-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="25658-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="25658-122">Remarks</span></span>  
 <span data-ttu-id="25658-123">Der Zeiger, die von dieser Methode zurückgegebene wird in der Regel als Parameter an übergeben die [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="25658-123">The pointer returned from this method is typically passed as a parameter to the [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25658-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="25658-124">Requirements</span></span>  
 <span data-ttu-id="25658-125">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25658-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25658-126">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="25658-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="25658-127">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="25658-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="25658-128">**.NET Framework Version:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="25658-128">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25658-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="25658-129">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [<span data-ttu-id="25658-130">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="25658-130">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
