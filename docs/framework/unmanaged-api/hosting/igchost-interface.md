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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 167e2477e5185112408793e145bc5a4fabea7fc8
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/30/2019
ms.locfileid: "66377613"
---
# <a name="igchost-interface"></a>IGCHost-Schnittstelle
Stellt Methoden zum Abrufen von Informationen über die Garbage Collection-System und zum Steuern einige Aspekte der Garbagecollection.  
  
> [!NOTE]
>  Ab .NET Framework 4.5, können Sie die [igchost2:: Setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) Methode, um die Größe der eine Garbage Collection-Segment und die maximale Größe der Garbage Collection-Systems die Generation 0 auf Werte größer als festlegen die `DWORD` Grenzwert, der vom auferlegt wird die [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md) Methode.  
  
> [!NOTE]
>  Diese Schnittstelle ist für die Verwendung durch Experten vorbehalten. Sie können die Leistung einer Anwendung beeinträchtigen, wenn nicht ordnungsgemäß verwendet.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Collect-Methode](../../../../docs/framework/unmanaged-api/hosting/igchost-collect-method.md)|Erzwingt, dass eine Collection für die angegebene Generation, unabhängig vom Status des aktuellen Garbagecollection durchgeführt.|  
|[GetStats-Methode](../../../../docs/framework/unmanaged-api/hosting/igchost-getstats-method.md)|Ruft die Statistiken für den aktuellen Zustand des Garbage Collection-Systems ab.|  
|[GetThreadStats-Methode](../../../../docs/framework/unmanaged-api/hosting/igchost-getthreadstats-method.md)|Ruft die Statistiken pro Thread für die Garbagecollection ab.|  
|[SetGCStartupLimits-Methode](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md)|Legt die Größe des Segments und die maximale Größe für Generation 0 fest.|  
|[SetVirtualMemLimit-Methode](../../../../docs/framework/unmanaged-api/hosting/igchost-setvirtualmemlimit-method.md)|Legt die maximale Größe des virtuellen Arbeitsspeichers von der Laufzeit fest.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** GCHost.idl, GCHost.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [CorRuntimeHost-Co-Klasse](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
