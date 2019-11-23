---
title: ICorProfilerInfo::GetILToNativeMapping-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILToNativeMapping
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILToNativeMapping
helpviewer_keywords:
- GetILToNativeMapping method, ICorProfilerInfo interface [.NET Framework profiling]
- ICorProfilerInfo::GetILToNativeMapping method [.NET Framework profiling]
ms.assetid: 6a5431ef-22fb-4e53-bac5-703986297eb1
topic_type:
- apiref
ms.openlocfilehash: 8dc551b2b1e29aba371e56eecfd981f16b4b1e3e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439036"
---
# <a name="icorprofilerinfogetiltonativemapping-method"></a>ICorProfilerInfo::GetILToNativeMapping-Methode
Ruft für den in der angegebenen Funktion enthaltenen Code eine Zuordnung von MSIL-Offsets (Microsoft Intermediate Language) zu systemeigenen Offsets ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetILToNativeMapping(  
    [in] FunctionID functionId,  
    [in] ULONG32 cMap,  
    [out] ULONG32 *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]);  
```  
  
## <a name="parameters"></a>Parameter  
 `functionId`  
 [in] Die ID der Funktion, die den Code enthält.  
  
 `cMap`  
 [in] Die maximale Größe des `map`-Arrays.  
  
 `pcMap`  
 [out] The total number of available COR_DEBUG_IL_TO_NATIVE_MAP structures.  
  
 `map`  
 [out] Ein Array von `COR_DEBUG_IL_TO_NATIVE_MAP`-Strukturen, die jeweils die Offsets angeben. Nach Rückgabe der `GetILToNativeMapping`-Methode enthält `map` einige oder alle `COR_DEBUG_IL_TO_NATIVE_MAP`-Strukturen.  
  
## <a name="remarks"></a>Hinweise  
 Die `GetILToNativeMapping`-Methode gibt ein Array von `COR_DEBUG_IL_TO_NATIVE_MAP`-Strukturen zurück. To convey that certain ranges of native instructions correspond to special regions of code (for example, the prolog), an entry in the array can have its `ilOffset` field set to a value of the [CorDebugIlToNativeMappingTypes](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md) enumeration.  
  
 Nachdem `GetILToNativeMapping` ausgeführt ist, müssen Sie sich vergewissern, dass der `map`-Puffer groß genug war, um alle `COR_DEBUG_IL_TO_NATIVE_MAP`-Strukturen zu enthalten. Vergleichen Sie hierzu den Wert von `cMap` mit dem Wert des `pcMap`-Parameters. Wenn der `pcMap`-Wert nach Multiplikation mit der Größe einer `COR_DEBUG_IL_TO_NATIVE_MAP`-Struktur größer als `cMap` ist, weisen Sie einen größeren `map`-Puffer zu, aktualisieren Sie `cMap` mit der neuen Größe, und rufen Sie `GetILToNativeMapping` erneut auf.  
  
 Alternativ können Sie zuerst `GetILToNativeMapping` mit einem `map`-Puffer der Länge 0 (NULL) aufrufen, um die richtige Puffergröße zu ermitteln. Sie können die Puffergröße dann auf den Wert festlegen, der von `pcMap` zurückgegeben wurde, und `GetILToNativeMapping` erneut aufrufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [GetILToNativeMapping2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getiltonativemapping2-method.md)
- [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Profilerstellung](../../../../docs/framework/unmanaged-api/profiling/index.md)
