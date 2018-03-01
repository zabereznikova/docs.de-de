---
title: ICorProfilerInfo3::GetFunctionEnter3Info-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerInfo3.GetFunctionEnter3Info Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetFunctionEnter3Info
helpviewer_keywords:
- GetFunctionEnter3Info method [.NET Framework profiling]
- ICorProfilerInfo3::GetFunctionEnter3Info method [.NET Framework profiling]
ms.assetid: 542c7c65-dd56-4651-b76f-5db2465e4a15
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6b7053f526d415dbaef872e37d139d25ae5ac462
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo3getfunctionenter3info-method"></a>ICorProfilerInfo3::GetFunctionEnter3Info-Methode
Stellt den Stapel und die Argumentinformationen der Funktion, die dem Profiler von gemeldet wird, ist die [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) Funktion. Diese Methode kann nur während des `FunctionEnter3WithInfo`-Rückrufs aufgerufen werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetFunctionEnter3Info(  
            [in]  FunctionID functionId,   
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo,  
            [in, out] ULONG *pcbArgumentInfo,  
            [out, size_is(*pcbArgumentInfo)]  
                  COR_PRF_FUNCTION_ARGUMENT_INFO *pArgumentInfo);  
```  
  
#### <a name="parameters"></a>Parameter  
 `functionId`  
 [in] Die `FunctionID` der Funktion, die aufgerufen wird.  
  
 `eltInfo`  
 [in] Ein nicht transparentes Handle, das Informationen über einen bestimmten Stapelrahmen entspricht. Der Profiler sollte die gleiche bereitstellen `eltInfo` , die es wurde angegeben, indem die [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) Funktion.  
  
 `pFrameInfo`  
 [out] Ein nicht transparentes Handle, das Generikainformationen zu einem bestimmten Stapelrahmen entspricht. Dieses Handle ist nur während des `FunctionEnter3WithInfo`-Rückrufs gültig, in dem der Profiler die `GetFunctionEnter3Info`-Methode aufgerufen hat.  
  
 `pcbArgumentInfo`  
 [in, out] Ein Zeiger auf die Gesamtgröße in Bytes, der die [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) Struktur (sowie alle weiteren [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) Strukturen für die argumentbereiche verweist`pArgumentInfo`). Wenn die angegebene Größe nicht ausreichend ist, wird ERROR_INSUFFICIENT_BUFFER zurückgegeben, und die erwartete Größe wird in `pcbArgumentInfo` gespeichert. Um `GetFunctionEnter3Info` so aufzurufen, dass nur der erwartete Wert für `*pcbArgumentInfo` abgerufen wird, legen `*pcbArgumentInfo`= 0 und `pArgumentInfo`= NULL fest.  
  
 `pArgumentInfo`  
 [out] Ein Zeiger auf eine [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) -Struktur, die die Argumente der Funktion im Arbeitsspeicher in links-nach-rechts-Reihenfolge die Positionen beschrieben.  
  
## <a name="remarks"></a>Hinweise  
 Der Profiler muss genügend Speicherplatz für die `COR_PRF_FUNCTION_ARGUMENT_INFO`-Struktur der Funktion reservieren, die geprüft wird, und er muss die Größe im `pcbArgumentInfo`-Parameter angeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 [ICorProfilerInfo3-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Profilerstellung](../../../../docs/framework/unmanaged-api/profiling/index.md)
