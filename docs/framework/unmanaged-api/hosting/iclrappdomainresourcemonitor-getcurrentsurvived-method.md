---
title: ICLRAppDomainResourceMonitor::GetCurrentSurvived-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAppDomainResourceMonitor.GetCurrentSurvived
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAppDomainResourceMonitor::GetCurrentSurvived
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentSurvived method [.NET Framework hosting]
- GetCurrentSurvived method [.NET Framework hosting]
ms.assetid: 392e9009-40ef-40e3-ad4d-7ce93a989e78
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b9fe624c83be5dcf762f1c6036f8e4264f0e45c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrappdomainresourcemonitorgetcurrentsurvived-method"></a>ICLRAppDomainResourceMonitor::GetCurrentSurvived-Methode
Ruft die Anzahl der Bytes, die die letzte vollständige blockierende Garbagecollection noch vorhanden sind und verwiesen wird, werden von der aktuellen Anwendungsdomäne, ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT STDMETHODCALLTYPE GetCurrentSurvived(  
             [in]  DWORD dwAppDomainId,  
             [out] ULONGLONG *pAppDomainBytesSurvived,  
             [out] ULONGLONG *pTotalBytesSurvived);  
```  
  
#### <a name="parameters"></a>Parameter  
 `dwAppDomainId`  
 [in] Die ID der angeforderten Anwendungsdomäne.  
  
 `pAppDomainBytesSurvived`  
 [out] Ein Zeiger auf die Anzahl der Bytes, die nach der letzten Garbagecollection noch vorhanden sind, die von dieser Anwendungsdomäne gehalten werden. Nach einer vollständigen Auflistung ist diese Nummer genauer und vollständiger. Nach einer kurzlebigen Auflistung ist diese Nummer möglicherweise unvollständig. Dieser Parameter kann `null` sein.  
  
 `pRuntimeBytesSurvived`  
 [out] Ein Zeiger auf die Gesamtanzahl der Bytes, die von der letzten Garbagecollection noch vorhanden sind. Nach einer vollständigen Auflistung stellt diese Anzahl die Anzahl der Bytes, die in verwalteten Heaps gehalten werden. Nach einer kurzlebigen Auflistung stellt diese Anzahl die Anzahl der Bytes, die in kurzlebigen Generationen live gespeichert werden. Dieser Parameter kann `null` sein.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|COR_E_APPDOMAINUNLOADED|Die Anwendungsdomäne entladen wurde oder nicht vorhanden.|  
  
## <a name="remarks"></a>Hinweise  
 Statistiken werden erst nach eine vollständige blockierende Garbagecollection aktualisiert. Tritt auf, d. h. eine Auflistung, die alle Generationen umfasst, und Beenden der Anwendung während der Auflistung, an. Z. B. die <xref:System.GC.Collect?displayProperty=nameWithType> methodenüberladung führt eine vollständige blockierende Garbage Collection. Die gleichzeitige Garbagecollection erfolgt im Hintergrund und die Anwendung nicht blockiert.  
  
 Die `GetCurrentSurvived` Methode ist die nicht verwaltete Entsprechung der verwalteten <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> Eigenschaft.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRAppDomainResourceMonitor-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 [Überwachung von Anwendungsdomänenressourcen](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)  
 [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
