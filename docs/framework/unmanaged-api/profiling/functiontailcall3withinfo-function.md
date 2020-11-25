---
title: FunctionTailcall3WithInfo-Funktion
ms.date: 03/30/2017
api_name:
- FunctionTailcall3WithInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall3WithInfo
helpviewer_keywords:
- FunctionTailcall3WithInfo function [.NET Framework profiling]
ms.assetid: 46380fcc-0198-43ae-a1f5-2d4939425886
topic_type:
- apiref
ms.openlocfilehash: c23c791197c9925038f71e70409e4ca3ebabb23e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722861"
---
# <a name="functiontailcall3withinfo-function"></a>FunctionTailcall3WithInfo-Funktion

Benachrichtigt den Profiler, dass die gerade ausgeführte Funktion gerade einen Tail-Aufruf einer anderen Funktion ausführt, und stellt ein Handle bereit, das an die [ICorProfilerInfo3:: GetFunctionTailcall3Info-Methode](icorprofilerinfo3-getfunctiontailcall3info-method.md) zum Abrufen des Stapel Rahmens übermittelt werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
void __stdcall FunctionTailcall3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a>Parameter  

- `functionIDOrClientID`

  \[in] der Bezeichner der aktuell ausgeführten Funktion, die einen Tail-Aufruf durchführen soll.

- `eltInfo`

  \[in] ein undurchsichtiges handle, das Informationen zu einem angegebenen Stapel Rahmen darstellt. Dieses Handle ist nur während des Rückrufs gültig, an den er übermittelt wird.

## <a name="remarks"></a>Hinweise  

 Die `FunctionTailcall3WithInfo` Rückruf Methode benachrichtigt den Profiler, wenn Funktionen aufgerufen werden, und ermöglicht es dem Profiler, mithilfe der [ICorProfilerInfo3:: GetFunctionTailcall3Info-Methode](icorprofilerinfo3-getfunctiontailcall3info-method.md) den Stapel Rahmen zu überprüfen. Für den Zugriff auf Stapel Rahmen Informationen `COR_PRF_ENABLE_FRAME_INFO` muss das-Flag festgelegt werden. Der Profiler kann die [ICorProfilerInfo:: SetEventMask-Methode](icorprofilerinfo-seteventmask-method.md) verwenden, um die Ereignisflags festzulegen, und dann die [ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3WithInfo-Methode](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) verwenden, um die Implementierung dieser Funktion zu registrieren.  
  
 Die `FunctionTailcall3WithInfo` Funktion ist ein Rückruf. Sie müssen Sie implementieren. Die-Implementierung muss das `__declspec(naked)` Speicher Klassen Attribut verwenden.  
  
 Die Ausführungs-Engine speichert vor dem Aufrufen dieser Funktion keine Register.  
  
- Beim Eintrag müssen Sie alle von Ihnen verwendeten Register speichern, einschließlich der in der Gleit Komma Einheit (Gleit Komma Einheit).  
  
- Beim Beenden müssen Sie den Stapel wiederherstellen, indem Sie alle Parameter, die vom Aufrufer per Pushvorgang übermittelt wurden, per Ping löschen.  
  
 Die Implementierung von `FunctionTailcall3WithInfo` sollte nicht blockieren, da Garbage Collection verzögert wird. Die-Implementierung sollte keine Garbage Collection versuchen, weil der Stapel möglicherweise nicht in einem Garbage Collection freundlichen Zustand ist. Wenn versucht wird, eine Garbage Collection auszuführen, wird die Laufzeit blockiert, bis von zurückgegeben wird `FunctionTailcall3WithInfo` .  
  
 Außerdem darf die FunctionTailcall3WithInfo-Funktion keinen verwalteten Code abrufen oder eine verwaltete Speicher Belegung in irgendeiner Weise auslösen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Corprof. idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [FunctionEnter3](functionenter3-function.md)
- [FunctionLeave3](functionleave3-function.md)
- [FunctionTailcall3](functiontailcall3-function.md)
- [FunctionEnter3WithInfo](functiontailcall3-function.md)
- [FunctionLeave3WithInfo](functionleave3withinfo-function.md)
- [SetEnterLeaveFunctionHooks3](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md)
- [SetFunctionIDMapper2](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [Profilerstellung für globale statische Funktionen](profiling-global-static-functions.md)
