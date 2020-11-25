---
title: IGCHost-Schnittstelle
ms.date: 03/30/2017
api_name:
- IGCHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost
helpviewer_keywords:
- IGCHost interface [.NET Framework hosting]
ms.assetid: 9ad70ffd-6963-4ab2-8c84-3d86c3fb8deb
topic_type:
- apiref
ms.openlocfilehash: 8965797321e68443c01d05f97d147f2320a76739
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724296"
---
# <a name="igchost-interface"></a>IGCHost-Schnittstelle

Bietet Methoden zum Abrufen von Informationen über das Garbage Collection System und zum Steuern einiger Aspekte von Garbage Collection.  
  
> [!NOTE]
> Beginnend mit dem .NET Framework 4,5 können Sie die [IGCHost2:: setgcstartuplimitsex](igchost2-setgcstartuplimitsex-method.md) -Methode verwenden, um die Größe eines Garbage Collection Segments und die maximale Größe der Generation 0 des Garbage Collection Systems auf Werte festzulegen, die den `DWORD` von der [SetGCStartupLimits](igchost-setgcstartuplimits-method.md) -Methode festgelegten Grenzwert überschreiten.  
  
> [!NOTE]
> Diese Schnittstelle ist nur für die Verwendung durch Experten vorgesehen. Dies kann die Leistung einer Anwendung beeinträchtigen, wenn Sie nicht ordnungsgemäß verwendet wird.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[Collect-Methode](igchost-collect-method.md)|Erzwingt, dass eine Auflistung für die angegebene Generierung stattfindet, unabhängig vom Zustand des aktuellen Garbage Collection.|  
|[GetStats-Methode](igchost-getstats-method.md)|Ruft die Statistiken für den aktuellen Status des Garbage Collection Systems ab.|  
|[GetThreadStats-Methode](igchost-getthreadstats-method.md)|Ruft die Statistiken pro Thread für Garbage Collection ab.|  
|[SetGCStartupLimits-Methode](igchost-setgcstartuplimits-method.md)|Legt die Segmentgröße und die maximale Größe für die Generation 0 fest.|  
|[SetVirtualMemLimit-Methode](igchost-setvirtualmemlimit-method.md)|Legt die maximale Größe des virtuellen Arbeitsspeichers der Laufzeit fest.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Gchost. idl, gchost. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Hosten von Schnittstellen](hosting-interfaces.md)
- [CorRuntimeHost-Co-Klasse](corruntimehost-coclass.md)
