---
title: ICLRAppDomainResourceMonitor::GetCurrentSurvived-Methode
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentSurvived
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentSurvived
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentSurvived method [.NET Framework hosting]
- GetCurrentSurvived method [.NET Framework hosting]
ms.assetid: 392e9009-40ef-40e3-ad4d-7ce93a989e78
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bf285b6e1f703c8776937fa33c7ab5801f04f80f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950159"
---
# <a name="iclrappdomainresourcemonitorgetcurrentsurvived-method"></a>ICLRAppDomainResourceMonitor::GetCurrentSurvived-Methode
Ruft die Anzahl der Bytes ab, die die letzte vollständige Blockierung Garbage Collection und auf die von der aktuellen Anwendungsdomäne verwiesen wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT STDMETHODCALLTYPE GetCurrentSurvived(  
             [in]  DWORD dwAppDomainId,  
             [out] ULONGLONG *pAppDomainBytesSurvived,  
             [out] ULONGLONG *pTotalBytesSurvived);  
```  
  
## <a name="parameters"></a>Parameter  
 `dwAppDomainId`  
 in Die ID der angeforderten Anwendungsdomäne.  
  
 `pAppDomainBytesSurvived`  
 vorgenommen Ein Zeiger auf die Anzahl der Bytes, die nach der letzten Garbage Collection, die von dieser Anwendungsdomäne aufbewahrt werden, noch nicht angezeigt werden. Nach einer vollständigen Sammlung ist diese Zahl genau und vollständig. Nach einer kurzlebigen Auflistung ist diese Zahl potenziell unvollständig. Dieser Parameter kann `null` sein.  
  
 `pRuntimeBytesSurvived`  
 vorgenommen Ein Zeiger auf die Gesamtanzahl der Bytes, die seit dem letzten Garbage Collection noch nicht angezeigt wurden. Nach einer vollständigen Auflistung stellt diese Anzahl die Anzahl der Bytes dar, die in verwalteten Heaps aufbewahrt werden. Nach einer kurzlebigen Auflistung stellt diese Anzahl die Anzahl der Bytes dar, die in kurzlebigen Generationen Live gespeichert werden. Dieser Parameter kann `null` sein.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|COR_E_APPDOMAINUNLOADED|Die Anwendungsdomäne wurde entladen oder ist nicht vorhanden.|  
  
## <a name="remarks"></a>Hinweise  
 Statistiken werden erst nach einem vollen, blockierenden Garbage Collection aktualisiert. Das heißt, eine Auflistung, die alle Generationen einschließt und die Anwendung beendet, während die Auflistung auftritt. Die <xref:System.GC.Collect?displayProperty=nameWithType> -Methoden Überladung führt z. b. eine vollständige blockierende Auflistung aus. Gleichzeitige Garbage Collection treten im Hintergrund auf und blockieren die Anwendung nicht.  
  
 Die `GetCurrentSurvived` -Methode ist das nicht verwaltete Äquivalent der verwalteten <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> -Eigenschaft.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost.h  
  
 **Fern** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRAppDomainResourceMonitor-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [Überwachung von Anwendungsdomänenressourcen](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
