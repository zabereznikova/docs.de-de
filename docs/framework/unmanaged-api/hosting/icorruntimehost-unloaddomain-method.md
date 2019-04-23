---
title: ICorRuntimeHost::CurrentDomain-Methode
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.UnloadDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::UnloadDomain
helpviewer_keywords:
- ICorRuntimeHost::UnloadDomain method [.NET Framework hosting]
- UnloadDomain method [.NET Framework hosting]
ms.assetid: dd9e9204-a80d-44f3-8192-779224b35056
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 492a60d3c8d18bec4e99ae778686fec6e8724248
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59140568"
---
# <a name="icorruntimehostunloaddomain-method"></a><span data-ttu-id="23acc-102">ICorRuntimeHost::CurrentDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="23acc-102">ICorRuntimeHost::UnloadDomain Method</span></span>
<span data-ttu-id="23acc-103">Entlädt die angegebene Anwendungsdomäne, die vom aktuellen Prozess an.</span><span class="sxs-lookup"><span data-stu-id="23acc-103">Unloads the specified application domain from the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23acc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="23acc-104">Syntax</span></span>  
  
```  
HRESULT UnloadDomain (  
    [in] IUnknown* pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="23acc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="23acc-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="23acc-106">[in] Ein Zeiger des Typs <xref:System._AppDomain?displayProperty=nameWithType> , das darstellt, der Domäne, entladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="23acc-106">[in] A pointer of type <xref:System._AppDomain?displayProperty=nameWithType> that represents the domain to be unloaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="23acc-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="23acc-107">Return Value</span></span>  
  
|<span data-ttu-id="23acc-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="23acc-108">HRESULT</span></span>|<span data-ttu-id="23acc-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="23acc-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="23acc-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="23acc-110">S_OK</span></span>|<span data-ttu-id="23acc-111">Der Vorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="23acc-111">The operation was successful.</span></span>|  
|<span data-ttu-id="23acc-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="23acc-112">S_FALSE</span></span>|<span data-ttu-id="23acc-113">Der Vorgang konnte nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="23acc-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="23acc-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="23acc-114">E_FAIL</span></span>|<span data-ttu-id="23acc-115">Ein Unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="23acc-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="23acc-116">Wenn eine Methode E_FAIL zurückgegeben wird, ist die common Language Runtime (CLR) nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="23acc-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="23acc-117">Nachfolgende Aufrufe von hosting-APIs HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="23acc-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="23acc-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="23acc-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="23acc-119">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="23acc-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="23acc-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="23acc-120">Requirements</span></span>  
 <span data-ttu-id="23acc-121">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23acc-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23acc-122">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="23acc-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="23acc-123">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="23acc-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="23acc-124">**.NET Framework Version:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="23acc-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23acc-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="23acc-125">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="23acc-126">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23acc-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
