---
title: ICorProfilerCallback6::GetAssemblyReferences-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- cpp
api_name:
- ICorProfilerCallback6.GetAssemblyReferences
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: 8b391afb-d79f-41bd-94ce-43ce62c6b5fc
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bc2e80d6d8207a869d43beb46cc9448bdd86dfec
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback6getassemblyreferences-method"></a>ICorProfilerCallback6::GetAssemblyReferences-Methode
[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]  
  
 Benachrichtigt den Profiler, dass ein Assembly sich in einer sehr frühen Ladephase befindet, wenn die Common Language Runtime einen "Closure Walk" des Assemblyverweises durchführt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT GetAssemblyReferences(        [in, string] const WCHAR* wszAssemblyPath,  
        [in] ICorProfilerAssemblyReferenceProvider* pAsmRefProvider  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `wszAssemblyPath`  
 [in] Der Pfad und Name des Assemblys, dessen Metadaten geändert werden.  
  
 `pAsmRefProvider`  
 [in] Ein Zeiger auf die Adresse des ein [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) Schnittstelle, der angibt, die Assembly verweist, hinzufügen.  
  
## <a name="return-value"></a>Rückgabewert  
 Rückgabewerte von diesem Rückruf werden ignoriert.  
  
## <a name="remarks"></a>Hinweise  
 Dieser Rückruf wird gesteuert durch Festlegen der [COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) ereignismaskenkennzeichnens beim Aufrufen der [icorprofilercallback5:: Seteventmask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) Methode. Wenn der Profiler für registriert die [icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) Rückrufmethode darstellt, die Common Language Runtime übergibt, der Pfad und Name der Assembly geladen und zusammen mit einem Zeiger auf eine [ ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) -Schnittstellenobjekt an diese Methode. Der Profiler ruft dann die [AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) Methode mit einem `COR_PRF_ASSEMBLY_REFERENCE_INFO` -Objekt für jede Zielassembly auf aus der Assembly aus verweisen die `GetAssemblyReferences` Rückruf.  
  
 Verwenden Sie den `GetAssemblyReferences`-Rückruf nur, wenn der Profiler die Metadaten einer Assembly für das Hinzufügen von Assemblyreferenzen ändern muss. (Beachten Sie, die die tatsächliche Änderung der Metadaten einer Assembly in erfolgt jedoch die [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)Rückrufmethode.) Der Profiler muss die Rückrufmethode `GetAssemblyReferences` implementieren, um die Common Language Runtime (CLR) zu informieren, dass Assemblyverweise hinzugefügt werden, nachdem das Modul geladen wurde.  Damit kann sichergestellt werden, dass die Freigabeentscheidungen der Assembly, die in dieser frühen Phase von der CLR getroffen werden, gültig bleiben, auch wenn der Profiler die Assemblyverweise der Metadaten später ändert.  Damit kann verhindert werden, dass manche Instanzen mit Profiler-Metadatenänderungen einen `SECURITY_E_INCOMPATIBLE_SHARE`-Fehler verursachen.  
  
 Der Profiler verwendet das [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) Objekt, das von dieser Methode hinzuzufügenden Assemblyverweise die CLR Assemblyverweis-abschlussdurchlaufs bereitgestellt.  Die [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) Objekt sollte nur von innerhalb dieses Rückrufs verwendet werden. Aufrufe von der [AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) Methode, die von diesem Rückruf führen nicht zu geänderten Metadaten, aber nur in einem geänderten Assemblyverweis-abschlussdurchlauf. Der Profiler weiterhin verwenden, müssen ein [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) Objekt explizit hinzuzufügenden Assemblyverweise innerhalb der [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) Rückruf für die verweisende Assembly, selbst wenn es implementiert die `GetAssemblyReferences` Rückruf.  
  
 Der Profiler sollte darauf vorbereitet sein, empfangen doppelter Aufrufe auf diesen Rückruf für dieselbe Assembly und sollte für jeden solchen Aufruf identisch reagieren (indem Sie den gleichen Satz von [ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) Aufrufe).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback6-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md)  
 [ModuleLoadFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)  
 [COR_PRF_ASSEMBLY_REFERENCE_INFO-Struktur](../../../../docs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md)  
 [ICorProfilerAssemblyReferenceProvider-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)
