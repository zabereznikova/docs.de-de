---
title: ICorProfilerInfo4::GetReJITIDs-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo4.GetReJITIDs
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo4::GetReJITIDs
helpviewer_keywords:
- GetReJITIDs method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetReJITIDs method [.NET Framework profiling]
ms.assetid: 634ac28c-a5b7-4fc3-af84-256c24ca8177
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: cc16cd932fc2ce0cf5cb53c227081501e79ed2d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo4getrejitids-method"></a>ICorProfilerInfo4::GetReJITIDs-Methode
Gibt ein Array von IDs, die alle JIT-kompilierten Version der angegebenen Funktion zu identifizieren, die dennoch zugeordnet sind. Dies schließt die JIT-kompilierten Versionen der Funktionen, die anschließend wiederhergestellt, jedoch noch nicht verfügbar (z. B. wenn die Anwendungsdomäne mit der wiederhergestellten Funktion weiterhin verwendet wird).  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetReJITIDs (  
     [in]  FunctionID          functionId,  
     [in]  ULONG               cReJitIds,  
     [out] ULONG *             pcReJitIds,  
     [out, size_is(cReJitIds), length_is(*pcReJitIds)]   ReJITID        reJitIds[]);  
```  
  
#### <a name="parameters"></a>Parameter  
 `functionId`  
 [in] Die `FunctionID` Funktion-Instanz für die Versionen aufgezählt.  
  
 `cReJitIds`  
 [in] Die Anzahl der JIT-kompilierten IDs zugeordnet, die der `reJitIds` Array.  
  
 `pcReJitIds`  
 [out] Die tatsächliche Anzahl der JIT-kompilierten-IDs.  
  
 `reJitIds`  
 [out] Ein vom Aufrufer zugewiesene Array, die der JIT-kompilierten-IDs für die angegebene Funktion enthält.  
  
## <a name="remarks"></a>Hinweise  
 `GetReJITIDs`Listet die aktiven JIT-kompilierten-IDs für eine Instanz für die angegebene Funktion auf. Es folgt demselben Nutzungsmuster wie andere `ICorProfilerInfo` Funktionen, die vom Aufrufer reservierte Puffer zu akzeptieren.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerInfo4-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Profilerstellung](../../../../docs/framework/unmanaged-api/profiling/index.md)
