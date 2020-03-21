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
ms.openlocfilehash: 5346792cb2a1309268cb4ba48625aa559777fbaf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176993"
---
# <a name="icorprofilerinfo3getfunctiontailcall3info-method"></a>ICorProfilerInfo3::GetFunctionTailcall3Info-Methode
Stellt den Stapelrahmen der Funktion bereit, die dem Profiler von der [Funktion FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) gemeldet wird. Diese Methode kann nur während des `FunctionTailcall3WithInfo`-Rückrufs aufgerufen werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetFunctionTailcall3Info(
            [in]  FunctionID functionId,
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo);  
```  
  
## <a name="parameters"></a>Parameter  
 `functionId`  
 [in] Die `FunctionID` der Funktion, die zurückgegeben wird.  
  
 `eltInfo`  
 [in] Ein nicht transparentes Handle, das Informationen über einen bestimmten Stapelrahmen entspricht. Der Profiler sollte `eltInfo` dasselbe bereitstellen, das dem `FunctionTailcall3WithInfo` Profiler von der Funktion gegeben wurde.  
  
 `pFrameInfo`  
 [out] Ein nicht transparentes Handle, das Genericsinformationen zu einem bestimmten Stapelrahmen entspricht. Dieses Handle ist nur während des `FunctionTailcall3WithInfo`-Rückrufs gültig, in dem der Profiler die `GetFunctionTailcall3Info`-Methode aufgerufen hat.  
  
## <a name="remarks"></a>Bemerkungen  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [FunctionEnter3WithInfo](functionenter3withinfo-function.md)
- [FunctionLeave3WithInfo](functionleave3withinfo-function.md)
- [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md)
- [ICorProfilerInfo3-Schnittstelle](icorprofilerinfo3-interface.md)
- [Profilerstellungsschnittstellen](profiling-interfaces.md)
- [Profilerstellung](index.md)
