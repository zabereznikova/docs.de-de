---
title: 'ICorProfilerInfo7:: applymetadata-Methode'
ms.date: 02/15/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo7.ApplyMetaData
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: a1bfb649-4584-4d35-b3e6-8fe59b53992a
ms.openlocfilehash: 00d9bef1e2b59a2d2207d1e343380e0e81bee848
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130348"
---
# <a name="icorprofilerinfo7applymetadata-method"></a>ICorProfilerInfo7:: applymetadata-Methode
[Wird nur in .NET Framework 4.6.1 und höheren Versionen unterstützt]  
  
 Wendet die durch die `IMetadataEmit::Define*`-Methoden neu definierten Metadaten auf ein angegebenes Modul an.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT ApplyMetaData(  
        [in] ModuleID moduleID  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `moduleID`  
 in Der Bezeichner des Moduls, dessen Metadaten geändert wurden.  
  
## <a name="remarks"></a>Hinweise  
 Wenn nach dem [moduleloadbeendeten](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) -Rückruf Metadatenänderungen vorgenommen werden, müssen Sie diese Methode vor der Verwendung der neuen Metadaten abrufen.  
  
 `ApplyMetaData` unterstützt nur das Hinzufügen der folgenden Metadatentypen:  
  
- `AssemblyRef` Datensätze, die Sie durch Aufrufen von [IMetaDataAssemblyEmit::D efineassemblyref](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)erstellen. -Methode.  
  
- `TypeRef` Datensätze, die Sie durch Aufrufen der [IMetaDataEmit::D efinetyperefbyname](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) -Methode erstellen.  
  
- `TypeSpec` Datensätze, die Sie durch Aufrufen der [IMetaDataEmit:: GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) -Methode erstellen.  
  
- `MemberRef` Datensätze, die Sie durch Aufrufen der [IMetaDataEmit::D efinemembership Ref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) -Methode erstellen.  
  
- `MemberSpec` Datensätze, die Sie durch Aufrufen der [IMetaDataEmit2::D efinemethodspec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) -Methode erstellen.  
  
- `UserString` Datensätze, die Sie durch Aufrufen der [IMetaDataEmit::D efineuserstring](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) -Methode erstellen.  

Ab .net Core 3,0 unterstützt `ApplyMetaData` auch die folgenden Typen:

- `TypeDef` Datensätze, die Sie durch Aufrufen der [IMetaDataEmit::D efinetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) -Methode erstellen.

- `MethodDef` Datensätze, die Sie durch Aufrufen der [IMetaDataEmit::D efinemethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md) -Methode erstellen. Das Hinzufügen von virtuellen Methoden zu einem vorhandenen Typ wird jedoch nicht unterstützt. Vor dem [moduleloadbeendeten](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) -Rückruf müssen virtuelle Methoden hinzugefügt werden.

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo7-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
