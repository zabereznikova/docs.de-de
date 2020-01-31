---
title: ICorProfilerCallback6::GetAssemblyReferences-Methode
ms.date: 03/30/2017
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
ms.openlocfilehash: 0717ef5fdb6c0447ceeb801f239be08f8cca5988
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865050"
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
  
## <a name="parameters"></a>Parameters  
 `wszAssemblyPath`  
 [in] Der Pfad und Name des Assemblys, dessen Metadaten geändert werden.  
  
 `pAsmRefProvider`  
 in Ein Zeiger auf die Adresse einer [icorprofilerassemblyreferenceprovider](icorprofilerassemblyreferenceprovider-interface.md) -Schnittstelle, die die hinzu zufügenden Assemblyverweise angibt.  
  
## <a name="return-value"></a>Rückgabewert  
 Rückgabewerte von diesem Rückruf werden ignoriert.  
  
## <a name="remarks"></a>Hinweise  
 Dieser Rückruf wird gesteuert, indem das Flag für die [COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES](cor-prf-high-monitor-enumeration.md) -Ereignis Maske beim Aufrufen der [ICorProfilerCallback5:: SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) -Methode festgelegt wird. Wenn der Profiler für die [ICorProfilerCallback6:: getassemblyreferences](icorprofilercallback6-getassemblyreferences-method.md) -Rückruf Methode registriert, übergibt die Laufzeit den Pfad und den Namen der zu ladenden Assembly zusammen mit einem Zeiger auf ein [icorprofilerassemblyreferenceprovider](icorprofilerassemblyreferenceprovider-interface.md) -Schnittstellen Objekt an diese Methode. Der Profiler kann dann die [icorprofilerassemblyreferenceprovider:: AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) -Methode mit einem `COR_PRF_ASSEMBLY_REFERENCE_INFO`-Objekt für jede Zielassembly abrufen, auf die von der im `GetAssemblyReferences`-Rückruf angegebenen Assembly verwiesen werden soll.  
  
 Verwenden Sie den `GetAssemblyReferences`-Rückruf nur, wenn der Profiler die Metadaten einer Assembly für das Hinzufügen von Assemblyreferenzen ändern muss. (Beachten Sie jedoch, dass die tatsächliche Änderung der Metadaten einer Assembly in der [ICorProfilerCallback:: moduleloadabgeschlossene](icorprofilercallback-moduleloadfinished-method.md)-Rückruf Methode erfolgt.) Der Profiler sollte die `GetAssemblyReferences` Rückruf Methode implementieren, um die Common Language Runtime (CLR) zu informieren, dass Assemblyverweise hinzugefügt werden, wenn das Modul geladen wurde.  Damit kann sichergestellt werden, dass die Freigabeentscheidungen der Assembly, die in dieser frühen Phase von der CLR getroffen werden, gültig bleiben, auch wenn der Profiler die Assemblyverweise der Metadaten später ändert.  Damit kann verhindert werden, dass manche Instanzen mit Profiler-Metadatenänderungen einen `SECURITY_E_INCOMPATIBLE_SHARE`-Fehler verursachen.  
  
 Der Profiler verwendet das von dieser Methode bereitgestellte [icorprofilerassemblyreferenceprovider](icorprofilerassemblyreferenceprovider-interface.md) -Objekt zum Hinzufügen von Assemblyverweisen zum CLR-assemblyverweisclosure  Das [icorprofilerassemblyreferenceprovider](icorprofilerassemblyreferenceprovider-interface.md) -Objekt darf nur innerhalb dieses Rückrufs verwendet werden. Aufrufe der [icorprofilerassemblyreferenceprovider:: AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) -Methode von diesem Rückruf ergeben nicht geänderte Metadaten, sondern nur in einem geänderten Assemblyverweis-Abschluss Durchlauf. Der Profiler muss weiterhin ein [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) -Objekt verwenden, um Assemblyverweise explizit aus dem Rückruf " [ICorProfilerCallback:: moduleloadbeendet](icorprofilercallback-moduleloadfinished-method.md) " für die referenzierende Assembly hinzuzufügen, auch wenn er den `GetAssemblyReferences` Rückruf implementiert.  
  
 Der Profiler sollte darauf vorbereitet sein, doppelte Aufrufe dieses Rückrufs für dieselbe Assembly zu empfangen, und sollte für jeden solchen doppelten Aufruf identisch sein (durch Ausführen desselben Satzes von [icorprofilerassemblyreferenceprovider:: AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) -aufrufen).  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback6-Schnittstelle](icorprofilercallback6-interface.md)
- [ModuleLoadFinished-Methode](icorprofilercallback-moduleloadfinished-method.md)
- [COR_PRF_ASSEMBLY_REFERENCE_INFO-Struktur](cor-prf-assembly-reference-info-structure.md)
- [ICorProfilerAssemblyReferenceProvider-Schnittstelle](icorprofilerassemblyreferenceprovider-interface.md)
