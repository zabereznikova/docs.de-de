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
ms.openlocfilehash: 08c46ecbad85e3cc15f60d1cc8dae6b8281702ef
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141132"
---
# <a name="iclrgcmanager-interface"></a>ICLRGCManager-Schnittstelle
Stellt Methoden bereit, mit denen ein Host mit dem Garbage Collection System des Common Language Runtime interagieren kann.  
  
> [!NOTE]
> Beginnend mit dem .NET Framework 4,5 können Sie die [ICLRGCManager2:: setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) -Methode verwenden, um die Größe eines Garbage Collection Segments und die maximale Größe der Generation 0 des Garbage Collection Systems auf Werte festzulegen, die größer als die `DWORD` Limit, das von der [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md) -Methode vorgegeben wird.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Collect-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-collect-method.md)|Erzwingt eine Garbage Collection für die angegebene Generierung.|  
|[GetStats-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md)|Ruft einen Satz aktueller Statistiken zum Garbage Collection System ab.|  
|[SetGCStartupLimits-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md)|Legt die Größe eines Garbage Collection Segments und die maximale Größe der Generation 0 des Garbage Collection Systems fest.|  
  
## <a name="remarks"></a>Hinweise  
 Der Common Language Runtime (CLR) implementiert seinen Garbage Collection Mechanismus mit dem verwalteten <xref:System.GC> Typ. Weitere Informationen zum Garbage Collection System finden Sie unter [Garbage Collection](../../../standard/garbage-collection/index.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Automatische Speicherverwaltung](../../../standard/automatic-memory-management.md)
- [COR_GC_STATS-Struktur](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [ICLRControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [CLR-Hostingschnittstellen](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
