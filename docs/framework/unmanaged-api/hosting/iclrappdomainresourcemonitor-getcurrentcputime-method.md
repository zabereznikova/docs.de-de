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
ms.openlocfilehash: de57fec05c338e51d0691ccfa0d0bffb334848de
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126786"
---
# <a name="iclrappdomainresourcemonitorgetcurrentcputime-method"></a>ICLRAppDomainResourceMonitor::GetCurrentCpuTime-Methode
Ruft die gesamte Prozessorzeit ab, die während der Ausführung in der aktuellen Anwendungsdomäne von allen Threads verwendet wurde, seit die Anwendungsdomäne erstellt wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetCurrentCpuTime([in]  DWORD dwAppDomainId,  
                          [out] ULONGLONG* pMilliseconds);  
```  
  
## <a name="parameters"></a>Parameter  
 `dwAppDomainId`  
 in Die ID der angeforderten Anwendungsdomäne.  
  
 `pMilliseconds`  
 vorgenommen Ein Zeiger auf die gesamte Prozessorzeit, die von allen Threads während der Ausführung in der aktuellen Anwendungsdomäne seit der Erstellung der Anwendungsdomäne verwendet wurde. Dieser Parameter kann `null` sein.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|COR_E_APPDOMAINUNLOADED|Die Anwendungsdomäne wurde entladen oder ist nicht vorhanden.|  
|E_FAIL|Die Überwachung der Anwendungs Domänen Ressource ist nicht aktiviert.<br /><br /> - oder -<br /><br /> Alle anderen Fehler.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode ist die nicht verwaltete Entsprechung der verwalteten <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType>-Eigenschaft.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRAppDomainResourceMonitor-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Überwachung von Anwendungsdomänenressourcen](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
