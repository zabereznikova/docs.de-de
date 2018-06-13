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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f2351fbb26a38f408d330db3f7600120bd57d6e1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437881"
---
# <a name="icorruntimehostgetdefaultdomain-method"></a><span data-ttu-id="efc9c-102">ICorRuntimeHost::GetDefaultDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="efc9c-102">ICorRuntimeHost::GetDefaultDomain Method</span></span>
<span data-ttu-id="efc9c-103">Ruft einen Schnittstellenzeiger vom Typ <xref:System._AppDomain?displayProperty=nameWithType> , die die Standarddomäne für den aktuellen Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="efc9c-103">Gets an interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType> that represents the default domain for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efc9c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="efc9c-104">Syntax</span></span>  
  
```  
HRESULT GetDefaultDomain (  
    [out] IUnknown** pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="efc9c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="efc9c-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="efc9c-106">[out] Einen Schnittstellenzeiger vom Typ <xref:System._AppDomain?displayProperty=nameWithType> auf die <xref:System.AppDomain> Instanz, die die Standardanwendungsdomäne für den Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="efc9c-106">[out] An interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType> to the <xref:System.AppDomain> instance that represents the default application domain for the process.</span></span>  
  
 <span data-ttu-id="efc9c-107">This-Zeiger typisiert ist `IUnknown`, sodass Aufrufer in der Regel aufrufen sollte `QueryInterface` abzurufenden einen Schnittstellenzeiger vom Typ <xref:System._AppDomain?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="efc9c-107">This pointer is typed `IUnknown`, so callers should generally call `QueryInterface` to obtain an interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="efc9c-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="efc9c-108">Return Value</span></span>  
  
|<span data-ttu-id="efc9c-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="efc9c-109">HRESULT</span></span>|<span data-ttu-id="efc9c-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="efc9c-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="efc9c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="efc9c-111">S_OK</span></span>|<span data-ttu-id="efc9c-112">Der Vorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="efc9c-112">The operation was successful.</span></span>|  
|<span data-ttu-id="efc9c-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="efc9c-113">S_FALSE</span></span>|<span data-ttu-id="efc9c-114">Der Vorgang konnte nicht abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="efc9c-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="efc9c-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="efc9c-115">E_FAIL</span></span>|<span data-ttu-id="efc9c-116">Ein Unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="efc9c-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="efc9c-117">Wenn eine Methode E_FAIL zurückgibt, ist die common Language Runtime (CLR) nicht mehr im Prozess verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="efc9c-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="efc9c-118">Nachfolgende Aufrufe hosting-APIs HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="efc9c-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="efc9c-119">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="efc9c-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="efc9c-120">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="efc9c-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="efc9c-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="efc9c-121">Requirements</span></span>  
 <span data-ttu-id="efc9c-122">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="efc9c-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efc9c-123">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="efc9c-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="efc9c-124">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="efc9c-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="efc9c-125">**.NET Framework-Versionen:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="efc9c-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efc9c-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="efc9c-126">See Also</span></span>  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="efc9c-127">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="efc9c-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
