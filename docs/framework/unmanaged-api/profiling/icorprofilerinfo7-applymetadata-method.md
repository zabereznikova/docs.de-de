---
title: ICorProfilerInfo7::ApplyMetaData-Methode
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aff6f63bb9f41fe45b22854787667070929bf987
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61650800"
---
# <a name="icorprofilerinfo7applymetadata-method"></a>ICorProfilerInfo7::ApplyMetaData-Methode
[Wird nur in .NET Framework 4.6.1 und höheren Versionen unterstützt]  
  
 Wendet die Metadaten von neu definiert die `IMetadataEmit::Define*` Methoden für ein angegebenes Modul.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT ApplyMetaData(  
        [in] ModuleID moduleID  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `moduleID`  
 [in] Der Bezeichner des Moduls, dessen Metadaten geändert wurde.  
  
## <a name="remarks"></a>Hinweise  
 Wenn Metadaten-Änderungen vorgenommen werden, nach der [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) Rückruf, müssen Sie diese Methode aufrufen, bevor Sie die neue Metadaten verwenden.  
  
 `ApplyMetaData` unterstützt nur die folgenden Arten von Metadaten hinzufügen:  
  
- `AssemblyRef` Datensätze, die Sie, durch den Aufruf Erstellen der [IMetaDataAssemblyEmit:: DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md). -Methode.  
  
- `TypeRef` Datensätze, die Sie, durch den Aufruf Erstellen der [IMetaDataEmit:: DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) Methode.  
  
- `TypeSpec` Datensätze, die Sie, durch den Aufruf Erstellen der [IMetaDataEmit:: GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) Methode.  
  
- `MemberRef` Datensätze, die Sie, durch den Aufruf Erstellen der [DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) Methode.  
  
- `MemberSpec` Datensätze, die Sie, durch den Aufruf Erstellen der [IMetaDataEmit2:: DefineMethodSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) Methode.  
  
- `UserString` Datensätze, die Sie, durch den Aufruf Erstellen der [IMetaDataEmit:: DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) Methode.  

Beginnend mit .NET Core 3.0, `ApplyMetaData` unterstützt auch die folgenden Typen:

- `TypeDef` Datensätze, die Sie, durch den Aufruf Erstellen der [IMetaDataEmit:: DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) Methode.

- `MethodDef` Datensätze, die Sie, durch den Aufruf Erstellen der [IMetaDataEmit:: DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md) Methode. Hinzufügen von virtuellen Methoden zu einem vorhandenen Typ wird jedoch nicht unterstützt. Virtuelle Methoden müssen hinzugefügt werden, bevor die [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) Rückruf.

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo7-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
