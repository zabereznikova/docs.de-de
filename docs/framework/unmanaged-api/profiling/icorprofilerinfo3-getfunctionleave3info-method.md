---
title: ICorProfilerInfo3::GetFunctionLeave3Info-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetFunctionLeave3Info Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetFunctionLeave3Info
helpviewer_keywords:
- GetFunctionLeave3Info method [.NET Framework profiling]
- ICorProfilerInfo3::GetFunctionLeave3Info method [.NET Framework profiling]
ms.assetid: df7083d2-fd43-44c7-9ce5-912c25cef0ff
topic_type:
- apiref
ms.openlocfilehash: bacb50520df9f1553226ec6bf1e878238b64bb17
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449705"
---
# <a name="icorprofilerinfo3getfunctionleave3info-method"></a>ICorProfilerInfo3::GetFunctionLeave3Info-Methode
Stellt den Stapel Rahmen und den Rückgabewert der Funktion bereit, die dem Profiler von der FunctionLeave3WithInfo- [Funktions](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) Funktion gemeldet wird. Diese Methode kann nur während des `FunctionLeave3WithInfo`-Rückrufs aufgerufen werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetFunctionLeave3Info(  
            [in]  FunctionID functionId,  
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo,  
            [out] COR_PRF_FUNCTION_ARGUMENT_RANGE *pRetvalRange);  
```  
  
## <a name="parameters"></a>Parameter  
 `functionId`  
 in Der `FunctionID` der Funktion, die zurückgibt.  
  
 `eltInfo`  
 [in] Ein nicht transparentes Handle, das Informationen über einen bestimmten Stapelrahmen entspricht. Der Profiler sollte die gleiche `eltInfo` bereitstellen, die dem Profiler von der [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) -Funktion übergeben wurde.  
  
 `pFrameInfo`  
 [out] Ein nicht transparentes Handle, das Genericsinformationen zu einem bestimmten Stapelrahmen entspricht. Dieses Handle ist nur während des `FunctionLeave3WithInfo`-Rückrufs gültig, in dem der Profiler die `GetFunctionLeave3Info`-Methode aufgerufen hat.  
  
 `pRetvalRange`  
 vorgenommen Ein Zeiger auf eine [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) Struktur, die den Wert enthält, der von der Funktion zurückgegeben wird. Für den Zugriff auf Rückgabewert Informationen muss das `COR_PRF_ENABLE_FUNCTION_RETVAL`-Flag festgelegt werden. Der Profiler kann die [ICorProfilerInfo:: SetEventMask-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) verwenden, um die Ereignisflags festzulegen.  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [ICorProfilerInfo3-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Profilerstellung](../../../../docs/framework/unmanaged-api/profiling/index.md)
