---
title: ICLRAppDomainResourceMonitor::GetCurrentAllocated-Methode
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentAllocated
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentAllocated
helpviewer_keywords:
- GetCurrentAllocated method [.NET Framework hosting]
- ICLRAppDomainResourceMonitor::GetCurrentAllocated method [.NET Framework hosting]
ms.assetid: 7bab209c-efd4-44c2-af30-61abab0ae2fc
topic_type:
- apiref
ms.openlocfilehash: d3bd948dfe4a5cf97e3e3e430f551e7bc6404690
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700781"
---
# <a name="iclrappdomainresourcemonitorgetcurrentallocated-method"></a><span data-ttu-id="4c971-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated-Methode</span><span class="sxs-lookup"><span data-stu-id="4c971-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated Method</span></span>

<span data-ttu-id="4c971-103">Ruft die Gesamtgröße (in Bytes) aller Speicher Belegungen ab, die von der Anwendungsdomäne seit der Erstellung vorgenommen wurden, ohne Subtraktion von Speicher, der in die Garbage Collection aufgenommen wurde.</span><span class="sxs-lookup"><span data-stu-id="4c971-103">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c971-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4c971-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentAllocated([in]  DWORD dwAppDomainId,  
                            [out] ULONGLONG* pBytesAllocated);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c971-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4c971-105">Parameters</span></span>  

 `dwAppDomainId`  
 <span data-ttu-id="4c971-106">in Die ID der angeforderten Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="4c971-106">[in] The ID of the requested application domain.</span></span>  
  
 `pBytesAllocated`  
 <span data-ttu-id="4c971-107">vorgenommen Ein Zeiger auf die Gesamtgröße aller Speicher Belegungen.</span><span class="sxs-lookup"><span data-stu-id="4c971-107">[out] A pointer to the total size of all memory allocations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4c971-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4c971-108">Return Value</span></span>  

 <span data-ttu-id="4c971-109">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="4c971-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="4c971-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4c971-110">HRESULT</span></span>|<span data-ttu-id="4c971-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4c971-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4c971-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="4c971-112">S_OK</span></span>|<span data-ttu-id="4c971-113">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="4c971-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="4c971-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="4c971-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="4c971-115">Die Anwendungsdomäne wurde entladen oder ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="4c971-115">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4c971-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4c971-116">Remarks</span></span>  

 <span data-ttu-id="4c971-117">Bei dieser Methode handelt es sich um das nicht verwaltete Äquivalent der verwalteten- <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="4c971-117">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c971-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="4c971-118">Requirements</span></span>  

 <span data-ttu-id="4c971-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c971-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c971-120">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="4c971-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="4c971-121">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="4c971-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4c971-122">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c971-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c971-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4c971-123">See also</span></span>

- [<span data-ttu-id="4c971-124">ICLRAppDomainResourceMonitor-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4c971-124">ICLRAppDomainResourceMonitor Interface</span></span>](iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="4c971-125">Überwachung von Anwendungs Domänen Ressourcen</span><span class="sxs-lookup"><span data-stu-id="4c971-125">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="4c971-126">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="4c971-126">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="4c971-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="4c971-127">Hosting</span></span>](index.md)
