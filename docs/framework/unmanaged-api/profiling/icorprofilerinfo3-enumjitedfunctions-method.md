---
title: ICorProfilerInfo3::EnumJITedFunctions-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.EnumJITedFunctions Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::EnumJITedFunctions
helpviewer_keywords:
- ICorProfilerInfo3::EnumJITedFunctions method [.NET Framework profiling]
- EnumJITedFunctions method [.NET Framework profiling]
ms.assetid: e2847a36-f460-45e2-9b6c-b33b008f40d9
topic_type:
- apiref
ms.openlocfilehash: a22a0de9a20f32ce1c9818bbcf29222a4b331420
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862424"
---
# <a name="icorprofilerinfo3enumjitedfunctions-method"></a>ICorProfilerInfo3::EnumJITedFunctions-Methode
Gibt einen Enumerator für alle Funktionen zurück, die zuvor JIT-kompiliert wurden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a>Parameters  
 `ppEnum`  
 vorgenommen Ein Zeiger auf den [icorprofilerfunctionenumerator](icorprofilerfunctionenum-interface.md) -Enumerator.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode überschneidet sich möglicherweise mit `JITCompilation` Rückrufen wie z. b. der [ICorProfilerCallback:: JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) -Methode. Der von dieser Methode zurückgegebene Enumerator enthält keine Funktionen, die aus mit Ngen. exe generierten systemeigenen Images geladen werden.  
  
> [!NOTE]
> Die zurückgegebene Enumeration enthält nur "0" für den Wert des `COR_PRF_FUNCTION::reJitId` Felds.  Wenn Sie gültige `COR_PRF_FUNCTION::reJitId` Werte benötigen, verwenden Sie die [ICorProfilerInfo4:: EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md) -Methode.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo3-Schnittstelle](icorprofilerinfo3-interface.md)
- [Profilerstellungsschnittstellen](profiling-interfaces.md)
- [Profilerstellung](index.md)
