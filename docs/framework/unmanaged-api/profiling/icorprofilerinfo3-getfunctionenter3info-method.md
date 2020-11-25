---
title: ICorProfilerInfo3::GetFunctionEnter3Info-Methode
ms.date: 03/30/2017
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
ms.openlocfilehash: 4e240743894e0a7076e593b55966307d304ebd28
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731188"
---
# <a name="icorprofilerinfo3getfunctionenter3info-method"></a>ICorProfilerInfo3::GetFunctionEnter3Info-Methode

Stellt den Stapel Rahmen und die Argument Informationen der Funktion bereit, die dem Profiler von der [FunctionEnter3WithInfo](functionenter3withinfo-function.md) -Funktion gemeldet wird. Diese Methode kann nur während des `FunctionEnter3WithInfo`-Rückrufs aufgerufen werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetFunctionEnter3Info(  
            [in]  FunctionID functionId,
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo,  
            [in, out] ULONG *pcbArgumentInfo,  
            [out, size_is(*pcbArgumentInfo)]  
                  COR_PRF_FUNCTION_ARGUMENT_INFO *pArgumentInfo);  
```  
  
## <a name="parameters"></a>Parameter  

 `functionId`  
 [in] Die `FunctionID` der Funktion, die aufgerufen wird.  
  
 `eltInfo`  
 [in] Ein nicht transparentes Handle, das Informationen über einen bestimmten Stapelrahmen entspricht. Der Profiler sollte die gleiche bereitstellen wie `eltInfo` die [FunctionEnter3WithInfo](functionenter3withinfo-function.md) -Funktion.  
  
 `pFrameInfo`  
 [out] Ein nicht transparentes Handle, das Genericsinformationen zu einem bestimmten Stapelrahmen entspricht. Dieses Handle ist nur während des `FunctionEnter3WithInfo`-Rückrufs gültig, in dem der Profiler die `GetFunctionEnter3Info`-Methode aufgerufen hat.  
  
 `pcbArgumentInfo`  
 [in, out] Ein Zeiger auf die Gesamtgröße (in Bytes) der [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) Struktur (zuzüglich aller zusätzlichen [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) Strukturen für die Argument Bereiche, auf die von verwiesen wird `pArgumentInfo` ). Wenn die angegebene Größe nicht ausreichend ist, wird ERROR_INSUFFICIENT_BUFFER zurückgegeben, und die erwartete Größe wird in `pcbArgumentInfo` gespeichert. Um `GetFunctionEnter3Info` so aufzurufen, dass nur der erwartete Wert für `*pcbArgumentInfo` abgerufen wird, legen `*pcbArgumentInfo`= 0 und `pArgumentInfo`= NULL fest.  
  
 `pArgumentInfo`  
 vorgenommen Ein Zeiger auf eine [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) -Struktur, die die Positionen der Argumente der Funktion im Arbeitsspeicher in der Reihenfolge von links nach rechts beschreibt.  
  
## <a name="remarks"></a>Hinweise  

 Der Profiler muss genügend Speicherplatz für die `COR_PRF_FUNCTION_ARGUMENT_INFO`-Struktur der Funktion reservieren, die geprüft wird, und er muss die Größe im `pcbArgumentInfo`-Parameter angeben.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [FunctionEnter3WithInfo](functionenter3withinfo-function.md)
- [FunctionLeave3WithInfo](functionleave3withinfo-function.md)
- [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md)
- [ICorProfilerInfo3-Schnittstelle](icorprofilerinfo3-interface.md)
- [Profilerstellungsschnittstellen](profiling-interfaces.md)
- [Profilerstellung](index.md)
