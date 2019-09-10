---
title: ICorProfilerInfo4::GetReJITIDs-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetReJITIDs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetReJITIDs
helpviewer_keywords:
- GetReJITIDs method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetReJITIDs method [.NET Framework profiling]
ms.assetid: 634ac28c-a5b7-4fc3-af84-256c24ca8177
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 805ceb60d2ac122df2382656b95b7bf5e7509bfc
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855938"
---
# <a name="icorprofilerinfo4getrejitids-method"></a>ICorProfilerInfo4::GetReJITIDs-Methode
Gibt ein Array von IDs zurück, die alle JIT-neu kompilierten Versionen der angegebenen Funktion identifizieren, die noch zugeordnet sind. Dies schließt JIT-kompilierte Versionen von Funktionen ein, die anschließend wieder hergestellt, aber noch nicht freigegeben wurden (z. b. wenn die Anwendungsdomäne, die die wiederhergestellte Funktion enthält, noch verwendet wird).  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT GetReJITIDs (  
     [in]  FunctionID          functionId,  
     [in]  ULONG               cReJitIds,  
     [out] ULONG *             pcReJitIds,  
     [out, size_is(cReJitIds), length_is(*pcReJitIds)]   ReJITID        reJitIds[]);  
```  
  
## <a name="parameters"></a>Parameter  
 `functionId`  
 in Der `FunctionID` der Funktions Instanz, für die Versionen aufgelistet werden sollen.  
  
 `cReJitIds`  
 in Die Anzahl der im `reJitIds` Array zugeordneten JIT-neu kompilierten IDs.  
  
 `pcReJitIds`  
 vorgenommen Die tatsächliche Anzahl der JIT-neu kompilierten IDs.  
  
 `reJitIds`  
 vorgenommen Ein vom Aufrufer zugewiesenes Array, das die JIT-neu kompilierten IDs für die angegebene Funktion enthält.  
  
## <a name="remarks"></a>Hinweise  
 `GetReJITIDs`Listet die aktiven JIT-kompilierten IDs für eine angegebene Funktions Instanz auf. Es folgt dem gleichen Verwendungs Muster wie andere `ICorProfilerInfo` Funktionen, die vom Aufrufer zugewiesene Puffer akzeptieren.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Corprof. idl, Corprof. h  
  
 **Fern** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo4-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Profilerstellung](../../../../docs/framework/unmanaged-api/profiling/index.md)
