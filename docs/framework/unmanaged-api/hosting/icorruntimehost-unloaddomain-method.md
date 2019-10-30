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
ms.openlocfilehash: dfdcb9b8aedeb3ccbbd27864e79ce43338942922
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133359"
---
# <a name="icorruntimehostunloaddomain-method"></a><span data-ttu-id="546b9-102">ICorRuntimeHost::CurrentDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="546b9-102">ICorRuntimeHost::UnloadDomain Method</span></span>
<span data-ttu-id="546b9-103">Entlädt die angegebene Anwendungsdomäne aus dem aktuellen Prozess.</span><span class="sxs-lookup"><span data-stu-id="546b9-103">Unloads the specified application domain from the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="546b9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="546b9-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadDomain (  
    [in] IUnknown* pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="546b9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="546b9-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="546b9-106">in Ein Zeiger vom Typ <xref:System._AppDomain?displayProperty=nameWithType>, der die zu entladende Domäne darstellt.</span><span class="sxs-lookup"><span data-stu-id="546b9-106">[in] A pointer of type <xref:System._AppDomain?displayProperty=nameWithType> that represents the domain to be unloaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="546b9-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="546b9-107">Return Value</span></span>  
  
|<span data-ttu-id="546b9-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="546b9-108">HRESULT</span></span>|<span data-ttu-id="546b9-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="546b9-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="546b9-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="546b9-110">S_OK</span></span>|<span data-ttu-id="546b9-111">Der Vorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="546b9-111">The operation was successful.</span></span>|  
|<span data-ttu-id="546b9-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="546b9-112">S_FALSE</span></span>|<span data-ttu-id="546b9-113">Der Vorgang konnte nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="546b9-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="546b9-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="546b9-114">E_FAIL</span></span>|<span data-ttu-id="546b9-115">Ein unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="546b9-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="546b9-116">Wenn eine Methode E_FAIL zurückgibt, kann die Common Language Runtime (CLR) im Prozess nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="546b9-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="546b9-117">Nachfolgende Aufrufe von Hosting-APIs geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="546b9-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="546b9-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="546b9-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="546b9-119">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="546b9-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="546b9-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="546b9-120">Requirements</span></span>  
 <span data-ttu-id="546b9-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="546b9-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="546b9-122">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="546b9-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="546b9-123">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="546b9-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="546b9-124">**.NET Framework Version:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="546b9-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="546b9-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="546b9-125">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="546b9-126">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="546b9-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
