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
ms.openlocfilehash: 9069498a4f62f4d9dbb50a7075323b14c3cc5ab9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868446"
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
  
## <a name="parameters"></a>Parameters  
 `functionId`  
 in Der `FunctionID` der Funktions Instanz, für die Versionen aufgelistet werden sollen.  
  
 `cReJitIds`  
 in Die Anzahl der im `reJitIds` Array zugeordneten JIT-neu kompilierten IDs.  
  
 `pcReJitIds`  
 vorgenommen Die tatsächliche Anzahl der JIT-neu kompilierten IDs.  
  
 `reJitIds`  
 vorgenommen Ein vom Aufrufer zugewiesenes Array, das die JIT-neu kompilierten IDs für die angegebene Funktion enthält.  
  
## <a name="remarks"></a>Hinweise  
 `GetReJITIDs` listet die aktiven JIT-neu kompilierten IDs für eine angegebene Funktions Instanz auf. Es folgt dem gleichen Verwendungs Muster wie andere `ICorProfilerInfo` Funktionen, die vom Aufrufer zugewiesene Puffer akzeptieren.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo4-Schnittstelle](icorprofilerinfo4-interface.md)
- [Profilerstellungsschnittstellen](profiling-interfaces.md)
- [Profilerstellung](index.md)
