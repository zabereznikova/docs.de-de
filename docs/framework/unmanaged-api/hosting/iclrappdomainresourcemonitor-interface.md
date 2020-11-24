---
title: ICLRAppDomainResourceMonitor-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor
helpviewer_keywords:
- ICLRAppDomainResourceMonitor interface [.NET Framework hosting]
ms.assetid: 72fa83a1-8997-41d7-b355-ab177a24a303
topic_type:
- apiref
ms.openlocfilehash: 84c53f0666d0e04b898e28c1d8e146eab566ca1b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674696"
---
# <a name="iclrappdomainresourcemonitor-interface"></a>ICLRAppDomainResourceMonitor-Schnittstelle

Stellt Methoden bereit, die den Arbeitsspeicher und die CPU-Auslastung einer Anwendungsdomäne überprüfen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetCurrentAllocated-Methode](iclrappdomainresourcemonitor-getcurrentallocated-method.md)|Ruft die Gesamtgröße (in Bytes) aller Speicher Belegungen ab, die von der Anwendungsdomäne seit der Erstellung vorgenommen wurden, ohne Subtraktion von Speicher, der in die Garbage Collection aufgenommen wurde.|  
|[GetCurrentSurvived-Methode](iclrappdomainresourcemonitor-getcurrentsurvived-method.md)|Ruft die Anzahl der Bytes ab, die die letzte vollständige Blockierung Garbage Collection und auf die von der aktuellen Anwendungsdomäne verwiesen wird.|  
|[GetCurrentCpuTime-Methode](iclrappdomainresourcemonitor-getcurrentcputime-method.md)|Ruft die gesamte Prozessorzeit ab, die während der Ausführung in der aktuellen Anwendungsdomäne von allen Threads verwendet wurde, seit die Anwendungsdomäne erstellt wurde.|  
  
## <a name="remarks"></a>Hinweise  

 Die- `ICLRAppDomainResourceMonitor` Schnittstelle bietet eine ähnliche Funktionalität wie die folgenden verwalteten Eigenschaften:  
  
- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringSurvivedProcessMemorySize%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType>  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [\<appDomainResourceMonitoring>-Element](../../configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)
- [Überwachung von Anwendungs Domänen Ressourcen](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [Hosten von Schnittstellen](hosting-interfaces.md)
- [Hosting](index.md)
