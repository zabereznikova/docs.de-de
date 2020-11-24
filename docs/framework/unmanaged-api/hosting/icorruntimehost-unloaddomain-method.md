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
ms.openlocfilehash: 94c84d876e19ec2ff7baba5a5a7420eec68d58c6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690108"
---
# <a name="icorruntimehostunloaddomain-method"></a><span data-ttu-id="43ec4-102">ICorRuntimeHost::CurrentDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="43ec4-102">ICorRuntimeHost::UnloadDomain Method</span></span>

<span data-ttu-id="43ec4-103">Entlädt die angegebene Anwendungsdomäne aus dem aktuellen Prozess.</span><span class="sxs-lookup"><span data-stu-id="43ec4-103">Unloads the specified application domain from the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43ec4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="43ec4-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadDomain (  
    [in] IUnknown* pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43ec4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="43ec4-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="43ec4-106">in Ein Zeiger vom Typ <xref:System._AppDomain?displayProperty=nameWithType> , der die zu entladende Domäne darstellt.</span><span class="sxs-lookup"><span data-stu-id="43ec4-106">[in] A pointer of type <xref:System._AppDomain?displayProperty=nameWithType> that represents the domain to be unloaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="43ec4-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="43ec4-107">Return Value</span></span>  
  
|<span data-ttu-id="43ec4-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="43ec4-108">HRESULT</span></span>|<span data-ttu-id="43ec4-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="43ec4-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="43ec4-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="43ec4-110">S_OK</span></span>|<span data-ttu-id="43ec4-111">Der Vorgang wurde durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="43ec4-111">The operation was successful.</span></span>|  
|<span data-ttu-id="43ec4-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="43ec4-112">S_FALSE</span></span>|<span data-ttu-id="43ec4-113">Der Vorgang konnte nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="43ec4-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="43ec4-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="43ec4-114">E_FAIL</span></span>|<span data-ttu-id="43ec4-115">Ein unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="43ec4-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="43ec4-116">Wenn eine Methode E_FAIL zurückgibt, ist die Common Language Runtime (CLR) im Prozess nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="43ec4-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="43ec4-117">Nachfolgende Aufrufe von Hosting-APIs geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="43ec4-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="43ec4-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="43ec4-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="43ec4-119">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="43ec4-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="43ec4-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="43ec4-120">Requirements</span></span>  

 <span data-ttu-id="43ec4-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43ec4-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43ec4-122">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="43ec4-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="43ec4-123">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="43ec4-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="43ec4-124">**.NET Framework Version:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="43ec4-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43ec4-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="43ec4-125">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="43ec4-126">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43ec4-126">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
