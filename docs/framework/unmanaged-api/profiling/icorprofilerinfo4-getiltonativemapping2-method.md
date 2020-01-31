---
title: ICorProfilerInfo4::GetILToNativeMapping2-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetILToNativeMapping2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetILToNativeMapping2
helpviewer_keywords:
- ICorProfilerInfo4::GetILToNativeMapping2 method [.NET Framework profiling]
- GetILToNativeMapping2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 756c1c25-08a7-4060-9798-dbeaa2f3bee5
topic_type:
- apiref
ms.openlocfilehash: 4fccee3b94efd65312206afb22c87f30609f9e6b
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868459"
---
# <a name="icorprofilerinfo4getiltonativemapping2-method"></a>ICorProfilerInfo4::GetILToNativeMapping2-Methode
Ruft eine Zuordnung zwischen MSIL-Offsets (Microsoft Intermediate Language) und systemeigenen Offsets für den Code ab, der in der erneut JIT-kompilierten Version der angegebenen Funktion enthalten ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetILToNativeMapping(  
    [in] FunctionID functionId,  
    [in] ReJITID reJitId,  
    [in] ULONG32 cMap,  
    [out] ULONG32 *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]);  
```  
  
## <a name="parameters"></a>Parameters  
 `functionId`  
 [in] Die ID der Funktion, die den Code enthält.  
  
 `pReJitId`  
 [in] Die Identität der erneut JIT-kompilierten Funktion. Die Identität muss in der .NET Framework 4,5 den Wert 0 (null) aufweisen.  
  
 `cMap`  
 [in] Die maximale Größe des `map`-Arrays.  
  
 `pcMap`  
 [out] Die Gesamtanzahl verfügbarer COR_DEBUG_IL_TO_NATIVE_MAP-Strukturen.  
  
 `map`  
 [out] Ein Array von `COR_DEBUG_IL_TO_NATIVE_MAP`-Strukturen, die jeweils die Offsets angeben. Nach Rückgabe der `GetILToNativeMapping2`-Methode enthält `map` einige oder alle `COR_DEBUG_IL_TO_NATIVE_MAP`-Strukturen.  
  
## <a name="remarks"></a>Hinweise  
 `GetILToNativeMapping2` ähnelt der [ICorProfilerInfo:: GetILToNativeMapping](icorprofilerinfo-getiltonativemapping-method.md) -Methode, mit der Ausnahme, dass der Profiler die ID der neu kompilierten Funktion in zukünftigen Versionen angeben kann.  
  
> [!NOTE]
> Die [icorprofilerfunctioncontrol::](icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md) -Methode ist nicht im .NET Framework 4,5 implementiert, sodass Funktionen, die JIT-neu kompiliert wurden, nicht über eine Il-zu-Native-Zuordnung verfügen können, die von der ursprünglich kompilierten Funktion abweicht. Daher können `GetILToNativeMapping2` nicht mit einer JIT-neu kompilierten ID ungleich NULL im .NET Framework 4,5 aufgerufen werden.  
  
 Die `GetILToNativeMapping2`-Methode gibt ein Array von `COR_DEBUG_IL_TO_NATIVE_MAP`-Strukturen zurück. Um zu vermitteln, dass bestimmte Bereiche nativer Anweisungen speziellen Codebereichen entsprechen (z. b. dem Prolog), kann für einen Eintrag im Array das `ilOffset`-Feld auf einen Wert der [CorDebugIlToNativeMappingTypes](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md) -Enumeration festgelegt werden.  
  
 Nachdem `GetILToNativeMapping2` ausgeführt ist, müssen Sie sich vergewissern, dass der `map`-Puffer groß genug war, um alle `COR_DEBUG_IL_TO_NATIVE_MAP`-Strukturen zu enthalten. Vergleichen Sie hierzu den Wert von `cMap` mit dem Wert des `pcMap`-Parameters. Wenn der `pcMap`-Wert nach Multiplikation mit der Größe einer `COR_DEBUG_IL_TO_NATIVE_MAP`-Struktur größer als `cMap` ist, weisen Sie einen größeren `map`-Puffer zu, aktualisieren Sie `cMap` mit der neuen Größe, und rufen Sie `GetILToNativeMapping2` erneut auf.  
  
 Alternativ können Sie zuerst `GetILToNativeMapping2` mit einem `map`-Puffer der Länge 0 (NULL) aufrufen, um die richtige Puffergröße zu ermitteln. Sie können die Puffergröße dann auf den Wert festlegen, der von `pcMap` zurückgegeben wurde, und `GetILToNativeMapping2` erneut aufrufen.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [GetILToNativeMapping-Methode](icorprofilerinfo-getiltonativemapping-method.md)
- [ICorProfilerInfo4-Schnittstelle](icorprofilerinfo4-interface.md)
- [Profilerstellungsschnittstellen](profiling-interfaces.md)
- [Profilerstellung](index.md)
