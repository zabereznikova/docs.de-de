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
ms.openlocfilehash: a73c0731c79dea3a0c411fe27a864ec9ac4e20b2
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616020"
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
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|COR_E_APPDOMAINUNLOADED|Die Anwendungsdomäne wurde entladen oder ist nicht vorhanden.|  
  
## <a name="remarks"></a>Hinweise  
 Statistiken werden erst nach einem vollen, blockierenden Garbage Collection aktualisiert. Das heißt, eine Auflistung, die alle Generationen einschließt und die Anwendung beendet, während die Auflistung auftritt. Die- <xref:System.GC.Collect?displayProperty=nameWithType> Methoden Überladung führt z. b. eine vollständige blockierende Auflistung aus. Gleichzeitige Garbage Collection treten im Hintergrund auf und blockieren die Anwendung nicht.  
  
 Die- `GetCurrentSurvived` Methode ist das nicht verwaltete Äquivalent der verwalteten- <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> Eigenschaft.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRAppDomainResourceMonitor-Schnittstelle](iclrappdomainresourcemonitor-interface.md)
- [Überwachung von Anwendungs Domänen Ressourcen](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [Hostingschnittstellen](hosting-interfaces.md)
- [Hosting](index.md)
