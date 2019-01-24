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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 63f5687787a9b0cdb30790b7e80e4160cdf413f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54737243"
---
# <a name="iclrappdomainresourcemonitorgetcurrentcputime-method"></a>ICLRAppDomainResourceMonitor::GetCurrentCpuTime-Methode
Ruft die gesamte Prozessorzeit, die von allen Threads beim Ausführen in der aktuellen Anwendungsdomäne seit der Erstellung der Anwendungsdomäne verwendet wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetCurrentCpuTime([in]  DWORD dwAppDomainId,  
                          [out] ULONGLONG* pMilliseconds);  
```  
  
#### <a name="parameters"></a>Parameter  
 `dwAppDomainId`  
 [in] Die ID des angeforderten Anwendungsdomäne.  
  
 `pMilliseconds`  
 [out] Ein Zeiger auf die gesamte Prozessorzeit, die von allen Threads beim Ausführen in der aktuellen Anwendungsdomäne seit der Erstellung der Anwendungsdomäne verwendet wurde. Dieser Parameter kann `null` sein.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|COR_E_APPDOMAINUNLOADED|Die Anwendungsdomäne entladen wurde, oder es ist nicht vorhanden.|  
|E_FAIL|Ressourcenüberwachung der Anwendungsdomäne ist nicht aktiviert.<br /><br /> - oder - <br /><br /> Alle anderen Fehler.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode ist, die nicht verwaltete Entsprechung der verwalteten <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> Eigenschaft.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICLRAppDomainResourceMonitor-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Überwachung von Anwendungsdomänenressourcen](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
