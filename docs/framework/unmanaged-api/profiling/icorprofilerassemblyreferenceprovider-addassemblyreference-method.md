---
title: ICorProfilerAssemblyReferenceProvider::AddAssemblyReference-Methode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorProfilerAssemblyReferenceProvider.AddAssemblyReference
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 3d5af8e7-c337-48f4-9fa6-97c83878b9b1
topic_type:
- apiref
ms.openlocfilehash: 2325e3034dbf00441e587017affa65b80821fbb1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128755"
---
# <a name="icorprofilerassemblyreferenceprovideraddassemblyreference-method"></a>ICorProfilerAssemblyReferenceProvider::AddAssemblyReference-Methode
[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]  
  
 Informiert den Common Language Runtime (CLR) über einen Assemblyverweis, den der Profiler plant, im [ICorProfilerCallback:: moduleloadabgeschlossene](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) -Rückruf hinzuzufügen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT AddAssemblyReference(  
        const COR_PRF_ASSEMBLY_REFERENCE_INFO* pAssemblyRefInfo  
);  
```  
  
## <a name="parameters"></a>Parameter  
 pAssemblyRefInfo  
 Ein Zeiger auf eine [COR_PRF_ASSEMBLY_REFERENCE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md) -Struktur, die der CLR Informationen über einen Assemblyverweis bereitstellt, der beim Ausführen eines assemblyverweisschließungs-Abschlusses berücksichtigt werden sollte.  
  
## <a name="remarks"></a>Hinweise  
 Der Profiler ruft diese Methode für jede Zielassembly auf, auf die er von der im `wszAssemblyPath`-Argument des [ICorProfilerCallback6:: getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) -Rückrufs angegebenen Assembly verweisen soll. Das [icorprofilerassemblyreferenceprovider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) -Schnittstellen Objekt wird zusammen mit dem Assemblypfad und dem Namen im `wszAssemblyPath` Argument an den [ICorProfilerCallback6:: getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) -Rückruf des Profilers übergeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerAssemblyReferenceProvider-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)
- [GetAssemblyReferences-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)
- [ModuleLoadFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)
