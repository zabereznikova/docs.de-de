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
ms.openlocfilehash: f2249d10159b1ff0be7ead0783efb8a2742d26b2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139604"
---
# <a name="icorruntimehostcurrentdomain-method"></a><span data-ttu-id="7c50f-102">ICorRuntimeHost::CurrentDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="7c50f-102">ICorRuntimeHost::CurrentDomain Method</span></span>
<span data-ttu-id="7c50f-103">Ruft einen Schnittstellen Zeiger vom Typ <xref:System.AppDomain?displayProperty=nameWithType> ab, der die Domäne darstellt, die für den aktuellen Thread geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="7c50f-103">Gets an interface pointer of type <xref:System.AppDomain?displayProperty=nameWithType> that represents the domain loaded on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c50f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7c50f-104">Syntax</span></span>  
  
```cpp  
HRESULT CurrentDomain (  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c50f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7c50f-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="7c50f-106">vorgenommen Ein Zeiger vom Typ <xref:System.AppDomain?displayProperty=nameWithType>, der die aktuelle Anwendungsdomäne des Threads darstellt.</span><span class="sxs-lookup"><span data-stu-id="7c50f-106">[out] A pointer of type <xref:System.AppDomain?displayProperty=nameWithType> that represents the thread's current application domain.</span></span> <span data-ttu-id="7c50f-107">Dieser Zeiger ist `IUnknown`typisiert. Daher sollten Aufrufer im allgemeinen `QueryInterface` abrufen, um einen Zeiger vom Typ <xref:System._AppDomain>zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="7c50f-107">This pointer is typed `IUnknown`, so callers should generally call `QueryInterface` to obtain a pointer of type <xref:System._AppDomain>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7c50f-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7c50f-108">Return Value</span></span>  
  
|<span data-ttu-id="7c50f-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7c50f-109">HRESULT</span></span>|<span data-ttu-id="7c50f-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7c50f-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7c50f-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="7c50f-111">S_OK</span></span>|<span data-ttu-id="7c50f-112">Der Vorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="7c50f-112">The operation was successful.</span></span>|  
|<span data-ttu-id="7c50f-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="7c50f-113">S_FALSE</span></span>|<span data-ttu-id="7c50f-114">Der Vorgang konnte nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="7c50f-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="7c50f-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7c50f-115">E_FAIL</span></span>|<span data-ttu-id="7c50f-116">Ein unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="7c50f-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="7c50f-117">Wenn eine Methode E_FAIL zurückgibt, kann die Common Language Runtime (CLR) im Prozess nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7c50f-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="7c50f-118">Nachfolgende Aufrufe von Hosting-APIs geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="7c50f-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7c50f-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7c50f-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7c50f-120">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="7c50f-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7c50f-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7c50f-121">Requirements</span></span>  
 <span data-ttu-id="7c50f-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c50f-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c50f-123">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="7c50f-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7c50f-124">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7c50f-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7c50f-125">**.NET Framework Versionen:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="7c50f-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c50f-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7c50f-126">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="7c50f-127">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7c50f-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
