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
ms.openlocfilehash: f19ac39737d08c10c23ce0bde03131f52b660cac
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126812"
---
# <a name="iclrappdomainresourcemonitorgetcurrentallocated-method"></a><span data-ttu-id="2b89c-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated-Methode</span><span class="sxs-lookup"><span data-stu-id="2b89c-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated Method</span></span>
<span data-ttu-id="2b89c-103">Ruft die Gesamtgröße (in Bytes) aller Speicher Belegungen ab, die von der Anwendungsdomäne seit der Erstellung vorgenommen wurden, ohne Subtraktion von Speicher, der in die Garbage Collection aufgenommen wurde.</span><span class="sxs-lookup"><span data-stu-id="2b89c-103">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b89c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2b89c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentAllocated([in]  DWORD dwAppDomainId,  
                            [out] ULONGLONG* pBytesAllocated);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b89c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2b89c-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="2b89c-106">in Die ID der angeforderten Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="2b89c-106">[in] The ID of the requested application domain.</span></span>  
  
 `pBytesAllocated`  
 <span data-ttu-id="2b89c-107">vorgenommen Ein Zeiger auf die Gesamtgröße aller Speicher Belegungen.</span><span class="sxs-lookup"><span data-stu-id="2b89c-107">[out] A pointer to the total size of all memory allocations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2b89c-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2b89c-108">Return Value</span></span>  
 <span data-ttu-id="2b89c-109">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="2b89c-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="2b89c-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2b89c-110">HRESULT</span></span>|<span data-ttu-id="2b89c-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2b89c-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2b89c-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="2b89c-112">S_OK</span></span>|<span data-ttu-id="2b89c-113">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="2b89c-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="2b89c-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="2b89c-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="2b89c-115">Die Anwendungsdomäne wurde entladen oder ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="2b89c-115">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b89c-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2b89c-116">Remarks</span></span>  
 <span data-ttu-id="2b89c-117">Diese Methode ist die nicht verwaltete Entsprechung der verwalteten <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="2b89c-117">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b89c-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2b89c-118">Requirements</span></span>  
 <span data-ttu-id="2b89c-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b89c-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b89c-120">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="2b89c-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="2b89c-121">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2b89c-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2b89c-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b89c-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b89c-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b89c-123">See also</span></span>

- [<span data-ttu-id="2b89c-124">ICLRAppDomainResourceMonitor-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2b89c-124">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="2b89c-125">Überwachung von Anwendungsdomänenressourcen</span><span class="sxs-lookup"><span data-stu-id="2b89c-125">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="2b89c-126">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="2b89c-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="2b89c-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="2b89c-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
