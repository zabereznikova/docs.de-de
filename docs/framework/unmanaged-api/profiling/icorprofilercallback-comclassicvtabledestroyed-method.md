---
title: ICorProfilerCallback::COMClassicVTableDestroyed-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.COMClassicVTableDestroyed
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::COMClassicVTableDestroyed
helpviewer_keywords:
- ICorProfilerCallback::COMClassicVTableDestroyed method [.NET Framework profiling]
- COMClassicVTableDestroyed method [.NET Framework profiling]
ms.assetid: 29da20ca-bf39-4356-8099-d9c3ac3423a9
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 74ee3f0ca092710342b48b8adbaa5f5cf7e8b980
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackcomclassicvtabledestroyed-method"></a>ICorProfilerCallback::COMClassicVTableDestroyed-Methode
Benachrichtigt den Profiler, dass eine COM-Interop-Vtable zerstört wird.  
  
> [!NOTE]
>  Dieser Rückruf wird wahrscheinlich nie auftreten, da die Zerstörung der v-Tabellen sehr nahe Herunterfahren auftritt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT COMClassicVTableDestroyed(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable);  
```  
  
#### <a name="parameters"></a>Parameter  
 `wrappedClasId`  
 [in] Die ID der Klasse für die diese Vtable erstellt wurde.  
  
 `implementedIID`  
 [in] Die ID der Schnittstelle, die von der Klasse implementiert. Dieser Wert kann NULL sein, wenn die Schnittstelle nur intern verfügbar ist.  
  
 `pVTable`  
 [in] Ein Zeiger auf den Anfang des Vtable.  
  
## <a name="remarks"></a>Hinweise  
 Der Profiler sollte in ihrer Implementierung dieser Methode nicht blockieren, da der Stapel nicht in einem Zustand ist, die Garbagecollection zulässt, und deshalb Präemptive Garbagecollection nicht aktiviert werden kann. Wenn der Profiler hier blockiert und Garbagecollection wird versucht, die Laufzeit blockiert, bis dieser Rückruf zurückgegeben.  
  
 Der Profiler Implementierung dieser Methode sollten nicht in verwaltetem Code oder in einer verwalteten Speicher reservieren aufrufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [COMClassicVTableCreated-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtablecreated-method.md)
