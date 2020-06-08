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
ms.openlocfilehash: c30206145d08a22af49c4a6a0dc83fd7382bcc06
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495506"
---
# <a name="icorprofilerinfo7applymetadata-method"></a>ICorProfilerInfo7:: applymetadata-Methode
[Wird nur in .NET Framework 4.6.1 und höheren Versionen unterstützt]  
  
 Wendet die durch die-Methoden neu definierten Metadaten auf ein angegebenes `IMetadataEmit::Define*` Modul an.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT ApplyMetaData(  
        [in] ModuleID moduleID  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `moduleID`  
 in Der Bezeichner des Moduls, dessen Metadaten geändert wurden.  
  
## <a name="remarks"></a>Bemerkungen  
 Wenn nach dem [moduleloadbeendeten](icorprofilercallback-moduleloadfinished-method.md) -Rückruf Metadatenänderungen vorgenommen werden, müssen Sie diese Methode vor der Verwendung der neuen Metadaten abrufen.  
  
 `ApplyMetaData`unterstützt nur das Hinzufügen der folgenden Metadatentypen:  
  
- `AssemblyRef`Datensätze, die durch Aufrufen von [IMetaDataAssemblyEmit::D efineassemblyref](../metadata/imetadataassemblyemit-defineassemblyref-method.md)erstellt werden. -Methode.  
  
- `TypeRef`Datensätze, die Sie durch Aufrufen der [IMetaDataEmit::D efinetyperefbyname](../metadata/imetadataemit-definetyperefbyname-method.md) -Methode erstellen.  
  
- `TypeSpec`Datensätze, die Sie durch Aufrufen der [IMetaDataEmit:: GetTokenFromTypeSpec](../metadata/imetadataemit-gettokenfromtypespec-method.md) -Methode erstellen.  
  
- `MemberRef`Datensätze, die Sie durch Aufrufen der [IMetaDataEmit::D efinemembership Ref](../metadata/imetadataemit-definememberref-method.md) -Methode erstellen.  
  
- `MemberSpec`Datensätze, die Sie durch Aufrufen der [IMetaDataEmit2::D efinemethodspec](../metadata/imetadataemit2-definemethodspec-method.md) -Methode erstellen.  
  
- `UserString`Datensätze, die Sie durch Aufrufen der [IMetaDataEmit::D efineuserstring](../metadata/imetadataemit-defineuserstring-method.md) -Methode erstellen.  

Ab .net Core 3,0 `ApplyMetaData` unterstützt auch die folgenden Typen:

- `TypeDef`Datensätze, die Sie durch Aufrufen der [IMetaDataEmit::D efinetypedef](../metadata/imetadataemit-definetypedef-method.md) -Methode erstellen.

- `MethodDef`Datensätze, die Sie durch Aufrufen der [IMetaDataEmit::D efinemethod](../metadata/imetadataemit-definemethod-method.md) -Methode erstellen. Das Hinzufügen von virtuellen Methoden zu einem vorhandenen Typ wird jedoch nicht unterstützt. Vor dem [moduleloadbeendeten](icorprofilercallback-moduleloadfinished-method.md) -Rückruf müssen virtuelle Methoden hinzugefügt werden.

## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICorProfilerInfo7-Schnittstelle](icorprofilerinfo7-interface.md)
