---
title: ICorProfilerInfo3::GetFunctionTailcall3Info-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetFunctionTailcall3Info Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetFunctionTailcall3Info
helpviewer_keywords:
- ICorProfilerInfo3::GetFunctionTailcall3Info method [.NET Framework profiling]
- GetFunctionTailcall3Info method [.NET Framework profiling]
ms.assetid: afdb5ac9-5bf5-4b91-b7cb-f81db23d7da3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c78d22c6566b49e85a59e4a682fa256d2d83ea3c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455584"
---
# <a name="icorprofilerinfo3getfunctiontailcall3info-method"></a>ICorProfilerInfo3::GetFunctionTailcall3Info-Methode
Stellt den Stapelrahmen der Funktion, die dem Profiler von gemeldet wird, ist die [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) Funktion. Diese Methode kann nur während des `FunctionTailcall3WithInfo`-Rückrufs aufgerufen werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetFunctionTailcall3Info(   
            [in]  FunctionID functionId,   
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo);  
```  
  
#### <a name="parameters"></a>Parameter  
 `functionId`  
 [in] Die `FunctionID` der Funktion, die zurückgegeben wird.  
  
 `eltInfo`  
 [in] Ein nicht transparentes Handle, das Informationen über einen bestimmten Stapelrahmen entspricht. Der Profiler sollte die gleiche bereitstellen `eltInfo` , wurde angegeben, um dem Profiler von der `FunctionTailcall3WithInfo` Funktion.  
  
 `pFrameInfo`  
 [out] Ein nicht transparentes Handle, das Generikainformationen zu einem bestimmten Stapelrahmen entspricht. Dieses Handle ist nur während des `FunctionTailcall3WithInfo`-Rückrufs gültig, in dem der Profiler die `GetFunctionTailcall3Info`-Methode aufgerufen hat.  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 [ICorProfilerInfo3-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Profilerstellung](../../../../docs/framework/unmanaged-api/profiling/index.md)
