---
title: ICLRAppDomainResourceMonitor::GetCurrentAllocated-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAppDomainResourceMonitor.GetCurrentAllocated
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAppDomainResourceMonitor::GetCurrentAllocated
helpviewer_keywords:
- GetCurrentAllocated method [.NET Framework hosting]
- ICLRAppDomainResourceMonitor::GetCurrentAllocated method [.NET Framework hosting]
ms.assetid: 7bab209c-efd4-44c2-af30-61abab0ae2fc
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dee616e1fbd071662a42af856fa2cd51f7bdd5d4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrappdomainresourcemonitorgetcurrentallocated-method"></a>ICLRAppDomainResourceMonitor::GetCurrentAllocated-Methode
Ruft die Gesamtgröße in Bytes aller speicherbelegungen, die von der Anwendungsdomäne seit der Erstellung, ohne Subtraktion des freigegebenen Speichers, die Sammlung veralteter Objekte aufgenommen wurde, vorgenommen wurden.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetCurrentAllocated([in]  DWORD dwAppDomainId,  
                            [out] ULONGLONG* pBytesAllocated);  
```  
  
#### <a name="parameters"></a>Parameter  
 `dwAppDomainId`  
 [in] Die ID der angeforderten Anwendungsdomäne.  
  
 `pBytesAllocated`  
 [out] Ein Zeiger auf die Gesamtgröße aller speicherbelegungen.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|COR_E_APPDOMAINUNLOADED|Die Anwendungsdomäne entladen wurde oder nicht vorhanden.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode ist die nicht verwaltete Entsprechung der verwalteten <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> Eigenschaft.  
  
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
