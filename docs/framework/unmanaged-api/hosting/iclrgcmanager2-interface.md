---
title: ICLRGCManager2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRGCManager2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager2
helpviewer_keywords:
- ICLRGCManager2 interface [.NET Framework hosting]
ms.assetid: 4b5ffd7b-9ad7-41cd-9bba-34030ae3da7e
topic_type:
- apiref
ms.openlocfilehash: 0f3ecc0d497eaee937647df47ba0956335a2fe41
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703944"
---
# <a name="iclrgcmanager2-interface"></a>ICLRGCManager2-Schnittstelle
Stellt Methoden bereit, mit denen ein Host mit dem Garbage Collection System des Common Language Runtime interagieren kann.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[SetGCStartupLimitsEx-Methode](iclrgcmanager2-setgcstartuplimitsex-method.md)|Legt die Größe eines Garbage Collection Segments und die maximale Größe der Generation 0 des Garbage Collection Systems fest. Aktiviert die Generation 0 und die Segment Größen größer als `DWORD` .|  
  
## <a name="remarks"></a>Hinweise  
 Diese Schnittstelle erbt von der [ICLRGCManager-Schnittstelle](iclrgcmanager-interface.md).  
  
 Der Common Language Runtime (CLR) implementiert seinen Garbage Collection Mechanismus mit dem verwalteten <xref:System.GC> Typ. Weitere Informationen zum Garbage Collection System finden Sie unter [Garbage Collection](../../../standard/garbage-collection/index.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Automatische Speicherverwaltung](../../../standard/automatic-memory-management.md)
- [COR_GC_STATS-Struktur](cor-gc-stats-structure.md)
- [ICLRControl-Schnittstelle](iclrcontrol-interface.md)
- [In .NET Framework 4 und 4.5 hinzugefügte CLR-Hostingschnittstellen](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [Hostingschnittstellen](hosting-interfaces.md)
- [Hosting](index.md)
