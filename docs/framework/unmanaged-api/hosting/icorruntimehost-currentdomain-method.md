---
title: ICorRuntimeHost::CurrentDomain-Methode
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CurrentDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CurrentDomain
helpviewer_keywords:
- ICorRuntimeHost::CreateDomain method [.NET Framework hosting]
- CurrentDomain method [.NET Framework hosting]
ms.assetid: dd2afb38-675b-4c3c-a9f3-8ab3b133eb02
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d3aa6bc844d2c6629085b0596127c0b51b99357d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766351"
---
# <a name="icorruntimehostcurrentdomain-method"></a><span data-ttu-id="7e04d-102">ICorRuntimeHost::CurrentDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="7e04d-102">ICorRuntimeHost::CurrentDomain Method</span></span>
<span data-ttu-id="7e04d-103">Ruft einen Schnittstellenzeiger vom Typ <xref:System.AppDomain?displayProperty=nameWithType> , das die Domäne geladen werden, für den aktuellen Thread darstellt.</span><span class="sxs-lookup"><span data-stu-id="7e04d-103">Gets an interface pointer of type <xref:System.AppDomain?displayProperty=nameWithType> that represents the domain loaded on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e04d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7e04d-104">Syntax</span></span>  
  
```cpp  
HRESULT CurrentDomain (  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e04d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7e04d-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="7e04d-106">[out] Ein Zeiger des Typs <xref:System.AppDomain?displayProperty=nameWithType> , das aktuelle Anwendungsdomäne des Threads darstellt.</span><span class="sxs-lookup"><span data-stu-id="7e04d-106">[out] A pointer of type <xref:System.AppDomain?displayProperty=nameWithType> that represents the thread's current application domain.</span></span> <span data-ttu-id="7e04d-107">Dieser Zeiger wird als `IUnknown`, sodass Aufrufer, in der Regel aufrufen müssen `QueryInterface` einen Zeiger des Typs abrufen <xref:System._AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="7e04d-107">This pointer is typed `IUnknown`, so callers should generally call `QueryInterface` to obtain a pointer of type <xref:System._AppDomain>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7e04d-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7e04d-108">Return Value</span></span>  
  
|<span data-ttu-id="7e04d-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7e04d-109">HRESULT</span></span>|<span data-ttu-id="7e04d-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7e04d-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7e04d-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="7e04d-111">S_OK</span></span>|<span data-ttu-id="7e04d-112">Der Vorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="7e04d-112">The operation was successful.</span></span>|  
|<span data-ttu-id="7e04d-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="7e04d-113">S_FALSE</span></span>|<span data-ttu-id="7e04d-114">Der Vorgang konnte nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="7e04d-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="7e04d-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7e04d-115">E_FAIL</span></span>|<span data-ttu-id="7e04d-116">Ein Unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="7e04d-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="7e04d-117">Wenn eine Methode E_FAIL zurückgegeben wird, ist die common Language Runtime (CLR) nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7e04d-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="7e04d-118">Nachfolgende Aufrufe von hosting-APIs HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="7e04d-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7e04d-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7e04d-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7e04d-120">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="7e04d-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7e04d-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7e04d-121">Requirements</span></span>  
 <span data-ttu-id="7e04d-122">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e04d-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e04d-123">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7e04d-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7e04d-124">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7e04d-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7e04d-125">**.NET Framework-Versionen:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="7e04d-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e04d-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7e04d-126">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="7e04d-127">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7e04d-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
