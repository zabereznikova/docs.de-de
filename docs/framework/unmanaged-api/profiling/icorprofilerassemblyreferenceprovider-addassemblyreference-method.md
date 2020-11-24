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
ms.openlocfilehash: 56468fd38bc110318e04d9b1beda61e279f731d1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685319"
---
# <a name="icorprofilerassemblyreferenceprovideraddassemblyreference-method"></a>ICorProfilerAssemblyReferenceProvider::AddAssemblyReference-Methode

[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]  
  
 Informiert den Common Language Runtime (CLR) über einen Assemblyverweis, den der Profiler plant, im [ICorProfilerCallback:: moduleloadabgeschlossene](icorprofilercallback-moduleloadfinished-method.md) -Rückruf hinzuzufügen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT AddAssemblyReference(  
        const COR_PRF_ASSEMBLY_REFERENCE_INFO* pAssemblyRefInfo  
);  
```  
  
## <a name="parameters"></a>Parameter

- `pAssemblyRefInfo`

  Ein Zeiger auf eine [COR_PRF_ASSEMBLY_REFERENCE_INFO](cor-prf-assembly-reference-info-structure.md) Struktur, die der CLR Informationen über einen Assemblyverweis bereitstellt, die beim Ausführen eines assemblyverweisschließungs-Abschlusses berücksichtigt werden sollten.
  
## <a name="remarks"></a>Hinweise  

 Der Profiler ruft diese Methode für jede Zielassembly auf, auf die er von der im- `wszAssemblyPath` Argument des [ICorProfilerCallback6:: getassemblyreferences](icorprofilercallback6-getassemblyreferences-method.md) -Rückrufs angegebenen Assembly verweisen soll. Das [icorprofilerassemblyreferenceprovider](icorprofilerassemblyreferenceprovider-interface.md) -Schnittstellen Objekt wird zusammen mit dem Assemblypfad und-Namen im-Argument an den [ICorProfilerCallback6:: getassemblyreferences](icorprofilercallback6-getassemblyreferences-method.md) -Rückruf des Profilers übergeben `wszAssemblyPath` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorProfilerAssemblyReferenceProvider-Schnittstelle](icorprofilerassemblyreferenceprovider-interface.md)
- [GetAssemblyReferences-Methode](icorprofilercallback6-getassemblyreferences-method.md)
- [ModuleLoadFinished-Methode](icorprofilercallback-moduleloadfinished-method.md)
