---
title: ICorRuntimeHost::CurrentDomain-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.UnloadDomain
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::UnloadDomain
helpviewer_keywords:
- ICorRuntimeHost::UnloadDomain method [.NET Framework hosting]
- UnloadDomain method [.NET Framework hosting]
ms.assetid: dd9e9204-a80d-44f3-8192-779224b35056
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 067b60b9da02300e9e7316712d0058a61ab8a697
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorruntimehostunloaddomain-method"></a><span data-ttu-id="7aeb8-102">ICorRuntimeHost::CurrentDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="7aeb8-102">ICorRuntimeHost::UnloadDomain Method</span></span>
<span data-ttu-id="7aeb8-103">Entlädt die angegebene Anwendungsdomäne vom aktuellen Prozess an.</span><span class="sxs-lookup"><span data-stu-id="7aeb8-103">Unloads the specified application domain from the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7aeb8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7aeb8-104">Syntax</span></span>  
  
```  
HRESULT UnloadDomain (  
    [in] IUnknown* pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7aeb8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7aeb8-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="7aeb8-106">[in] Ein Zeiger des Typs <xref:System._AppDomain?displayProperty=nameWithType> , die die Domäne so das Entladen darstellt.</span><span class="sxs-lookup"><span data-stu-id="7aeb8-106">[in] A pointer of type <xref:System._AppDomain?displayProperty=nameWithType> that represents the domain to be unloaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7aeb8-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7aeb8-107">Return Value</span></span>  
  
|<span data-ttu-id="7aeb8-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7aeb8-108">HRESULT</span></span>|<span data-ttu-id="7aeb8-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7aeb8-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7aeb8-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7aeb8-110">S_OK</span></span>|<span data-ttu-id="7aeb8-111">Der Vorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="7aeb8-111">The operation was successful.</span></span>|  
|<span data-ttu-id="7aeb8-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="7aeb8-112">S_FALSE</span></span>|<span data-ttu-id="7aeb8-113">Der Vorgang konnte nicht abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="7aeb8-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="7aeb8-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7aeb8-114">E_FAIL</span></span>|<span data-ttu-id="7aeb8-115">Ein Unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="7aeb8-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="7aeb8-116">Wenn eine Methode E_FAIL zurückgibt, ist die common Language Runtime (CLR) nicht mehr im Prozess verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="7aeb8-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="7aeb8-117">Nachfolgende Aufrufe hosting-APIs HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="7aeb8-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7aeb8-118">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="7aeb8-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7aeb8-119">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="7aeb8-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7aeb8-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7aeb8-120">Requirements</span></span>  
 <span data-ttu-id="7aeb8-121">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7aeb8-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7aeb8-122">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7aeb8-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7aeb8-123">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7aeb8-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7aeb8-124">**.NET Framework-Version:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="7aeb8-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7aeb8-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7aeb8-125">See Also</span></span>  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="7aeb8-126">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7aeb8-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
