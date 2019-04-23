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
ms.openlocfilehash: 9d2d48e5fb070ec0334de579d2e28146177a87b1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59121614"
---
# <a name="icorprofilerinfo4getrejitids-method"></a>ICorProfilerInfo4::GetReJITIDs-Methode
Gibt ein Array von IDs, die alle erneut JIT-kompilierte Versionen der angegebenen Funktion zu identifizieren, die immer noch zugeordnet sind. Dies schließt erneut JIT-kompilierte Versionen der Funktionen, die anschließend zurückgesetzt, aber noch nicht verfügbar (z. B. wenn die Anwendungsdomäne mit der wiederhergestellten Funktion noch verwendet wird).  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetReJITIDs (  
     [in]  FunctionID          functionId,  
     [in]  ULONG               cReJitIds,  
     [out] ULONG *             pcReJitIds,  
     [out, size_is(cReJitIds), length_is(*pcReJitIds)]   ReJITID        reJitIds[]);  
```  
  
## <a name="parameters"></a>Parameter  
 `functionId`  
 [in] Die `FunctionID` Funktion-Instanz für die Versionen aufgelistet werden sollen.  
  
 `cReJitIds`  
 [in] Die Anzahl der erneut JIT-kompilierten IDs zugewiesen werden, der `reJitIds` Array.  
  
 `pcReJitIds`  
 [out] Die tatsächliche Anzahl der erneut JIT-kompilierten-IDs.  
  
 `reJitIds`  
 [out] Ein vom Aufrufer reservierte Array, die die erneut JIT-kompilierten-IDs für die angegebene Funktion enthält.  
  
## <a name="remarks"></a>Hinweise  
 `GetReJITIDs` Listet die aktiven erneut JIT-kompilierten-IDs für eine Instanz für die angegebene Funktion auf. Dabei wird das gleiche Verwendungsmuster wie andere `ICorProfilerInfo` Funktionen, die vom Aufrufer reservierte Puffer zu akzeptieren.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo4-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Profilerstellung](../../../../docs/framework/unmanaged-api/profiling/index.md)
