---
title: ICLRAppDomainResourceMonitor::GetCurrentCpuTime-Methode
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentCpuTime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentCpuTime
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentCpuTime method [.NET Framework hosting]
- GetCurrentCpuTime method [.NET Framework hosting]
ms.assetid: ebc9cc33-fcd6-4cae-9ecb-ea21c51874e6
topic_type:
- apiref
ms.openlocfilehash: a0b966e85bedcbef622aba2f6b181b98e0950e01
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700677"
---
# <a name="iclrappdomainresourcemonitorgetcurrentcputime-method"></a><span data-ttu-id="e44c7-102">ICLRAppDomainResourceMonitor::GetCurrentCpuTime-Methode</span><span class="sxs-lookup"><span data-stu-id="e44c7-102">ICLRAppDomainResourceMonitor::GetCurrentCpuTime Method</span></span>

<span data-ttu-id="e44c7-103">Ruft die gesamte Prozessorzeit ab, die während der Ausführung in der aktuellen Anwendungsdomäne von allen Threads verwendet wurde, seit die Anwendungsdomäne erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="e44c7-103">Gets the total processor time that has been used by all threads while executing in the current application domain, since the application domain was created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e44c7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e44c7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentCpuTime([in]  DWORD dwAppDomainId,  
                          [out] ULONGLONG* pMilliseconds);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e44c7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e44c7-105">Parameters</span></span>  

 `dwAppDomainId`  
 <span data-ttu-id="e44c7-106">in Die ID der angeforderten Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="e44c7-106">[in] The ID of the requested application domain.</span></span>  
  
 `pMilliseconds`  
 <span data-ttu-id="e44c7-107">vorgenommen Ein Zeiger auf die gesamte Prozessorzeit, die von allen Threads während der Ausführung in der aktuellen Anwendungsdomäne seit der Erstellung der Anwendungsdomäne verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="e44c7-107">[out] A pointer to the total processor time that has been used by all threads while executing in the current application domain since the application domain was created.</span></span> <span data-ttu-id="e44c7-108">Dieser Parameter kann `null` sein.</span><span class="sxs-lookup"><span data-stu-id="e44c7-108">This parameter can be `null`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e44c7-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e44c7-109">Return Value</span></span>  
  
|<span data-ttu-id="e44c7-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e44c7-110">HRESULT</span></span>|<span data-ttu-id="e44c7-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e44c7-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e44c7-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="e44c7-112">S_OK</span></span>|<span data-ttu-id="e44c7-113">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="e44c7-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="e44c7-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="e44c7-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="e44c7-115">Die Anwendungsdomäne wurde entladen oder ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="e44c7-115">The application domain has been unloaded or does not exist.</span></span>|  
|<span data-ttu-id="e44c7-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e44c7-116">E_FAIL</span></span>|<span data-ttu-id="e44c7-117">Die Überwachung der Anwendungs Domänen Ressource ist nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="e44c7-117">Application domain resource monitoring is not enabled.</span></span><br /><br /> <span data-ttu-id="e44c7-118">- oder -</span><span class="sxs-lookup"><span data-stu-id="e44c7-118">-or-</span></span><br /><br /> <span data-ttu-id="e44c7-119">Alle anderen Fehler.</span><span class="sxs-lookup"><span data-stu-id="e44c7-119">All other failures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e44c7-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e44c7-120">Remarks</span></span>  

 <span data-ttu-id="e44c7-121">Bei dieser Methode handelt es sich um das nicht verwaltete Äquivalent der verwalteten- <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e44c7-121">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e44c7-122">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e44c7-122">Requirements</span></span>  

 <span data-ttu-id="e44c7-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e44c7-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e44c7-124">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="e44c7-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e44c7-125">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e44c7-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e44c7-126">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e44c7-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e44c7-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e44c7-127">See also</span></span>

- [<span data-ttu-id="e44c7-128">ICLRAppDomainResourceMonitor-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e44c7-128">ICLRAppDomainResourceMonitor Interface</span></span>](iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="e44c7-129">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e44c7-129">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="e44c7-130">Überwachung von Anwendungs Domänen Ressourcen</span><span class="sxs-lookup"><span data-stu-id="e44c7-130">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="e44c7-131">Hosting</span><span class="sxs-lookup"><span data-stu-id="e44c7-131">Hosting</span></span>](index.md)
