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
ms.openlocfilehash: 2ac645cbaaa45554568874653be016e4691bbd2f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707476"
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
 in Die Anzahl der im Array zugeordneten JIT-neu kompilierten IDs `reJitIds` .  
  
 `pcReJitIds`  
 vorgenommen Die tatsächliche Anzahl der JIT-neu kompilierten IDs.  
  
 `reJitIds`  
 vorgenommen Ein vom Aufrufer zugewiesenes Array, das die JIT-neu kompilierten IDs für die angegebene Funktion enthält.  
  
## <a name="remarks"></a>Hinweise  

 `GetReJITIDs` Listet die aktiven JIT-kompilierten IDs für eine angegebene Funktions Instanz auf. Es folgt dem gleichen Verwendungs Muster wie andere `ICorProfilerInfo` Funktionen, die vom Aufrufer zugewiesene Puffer akzeptieren.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorProfilerInfo4-Schnittstelle](icorprofilerinfo4-interface.md)
- [Profilerstellungsschnittstellen](profiling-interfaces.md)
- [Profilerstellung](index.md)
