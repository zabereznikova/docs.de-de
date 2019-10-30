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
ms.openlocfilehash: 72ffd7b47795ee8e46f8fbff07559133843793e6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141158"
---
# <a name="iclrgcmanager2-interface"></a>ICLRGCManager2-Schnittstelle
Stellt Methoden bereit, mit denen ein Host mit dem Garbage Collection System des Common Language Runtime interagieren kann.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[SetGCStartupLimitsEx-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)|Legt die Größe eines Garbage Collection Segments und die maximale Größe der Generation 0 des Garbage Collection Systems fest. Aktiviert Generation 0 und Segment Größen, die größer als `DWORD`sind.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Schnittstelle erbt von der [ICLRGCManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).  
  
 Der Common Language Runtime (CLR) implementiert seinen Garbage Collection Mechanismus mit dem verwalteten <xref:System.GC> Typ. Weitere Informationen zum Garbage Collection System finden Sie unter [Garbage Collection](../../../standard/garbage-collection/index.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Automatische Speicherverwaltung](../../../standard/automatic-memory-management.md)
- [COR_GC_STATS-Struktur](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [ICLRControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [In .NET Framework 4 und 4.5 hinzugefügte CLR-Hostingschnittstellen](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
