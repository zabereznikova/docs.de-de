---
title: ICLRGCManager-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRGCManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager
helpviewer_keywords:
- ICLRGCManager interface [.NET Framework hosting]
ms.assetid: fb511c9b-3fe4-41b0-822a-6ba4a079d1f5
topic_type:
- apiref
ms.openlocfilehash: f878e2f1f86bc42c0ff5abada8d7df4feb9ed228
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504188"
---
# <a name="iclrgcmanager-interface"></a>ICLRGCManager-Schnittstelle
Stellt Methoden bereit, mit denen ein Host mit dem Garbage Collection System des Common Language Runtime interagieren kann.  
  
> [!NOTE]
> Beginnend mit dem .NET Framework 4,5 können Sie die [ICLRGCManager2:: setgcstartuplimitsex](iclrgcmanager2-setgcstartuplimitsex-method.md) -Methode verwenden, um die Größe eines Garbage Collection Segments und die maximale Größe der Generation 0 des Garbage Collection Systems auf Werte festzulegen, die den `DWORD` von der [SetGCStartupLimits](iclrgcmanager-setgcstartuplimits-method.md) -Methode festgelegten Grenzwert überschreiten.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[Collect-Methode](iclrgcmanager-collect-method.md)|Erzwingt eine Garbage Collection für die angegebene Generierung.|  
|[GetStats-Methode](iclrgcmanager-getstats-method.md)|Ruft einen Satz aktueller Statistiken zum Garbage Collection System ab.|  
|[SetGCStartupLimits-Methode](iclrgcmanager-setgcstartuplimits-method.md)|Legt die Größe eines Garbage Collection Segments und die maximale Größe der Generation 0 des Garbage Collection Systems fest.|  
  
## <a name="remarks"></a>Bemerkungen  
 Der Common Language Runtime (CLR) implementiert seinen Garbage Collection Mechanismus mit dem verwalteten <xref:System.GC> Typ. Weitere Informationen zum Garbage Collection System finden Sie unter [Garbage Collection](../../../standard/garbage-collection/index.md).  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [Automatische Speicherverwaltung](../../../standard/automatic-memory-management.md)
- [COR_GC_STATS-Struktur](cor-gc-stats-structure.md)
- [ICLRControl-Schnittstelle](iclrcontrol-interface.md)
- [CLR-Hostingschnittstellen](clr-hosting-interfaces.md)
- [Hosten von Schnittstellen](hosting-interfaces.md)
- [Hosting](index.md)
