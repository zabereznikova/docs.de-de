---
title: FunctionLeave3WithInfo-Funktion
ms.date: 03/30/2017
api_name:
- FunctionLeave3WithInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave3WithInfo
helpviewer_keywords:
- FunctionLeave3WithInfo function [.NET Framework profiling]
ms.assetid: 5fa68a67-ced6-41c6-a2c0-467060fd0692
topic_type:
- apiref
ms.openlocfilehash: 69ee0ea78e0c7edbb61999ef8fba1791e6f682bc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722244"
---
# <a name="functionleave3withinfo-function"></a>FunctionLeave3WithInfo-Funktion

Benachrichtigt den Profiler, dass die Steuerung von einer Funktion zurückgegeben wird, und stellt ein Handle bereit, das an die [ICorProfilerInfo3:: GetFunctionLeave3Info-Methode](icorprofilerinfo3-getfunctionleave3info-method.md) zum Abrufen des Stapel Rahmens und des Rückgabewerts übermittelt werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
void __stdcall FunctionLeave3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a>Parameter

- `functionIDOrClientID`

  \[in] der Bezeichner der Funktion, von der das Steuerelement zurückgegeben wird.

- `eltInfo`

  \[in] ein undurchsichtiges handle, das Informationen zu einem angegebenen Stapel Rahmen darstellt. Dieses Handle ist nur während des Rückrufs gültig, an den er übermittelt wird.

## <a name="remarks"></a>Hinweise  

 Die `FunctionLeave3WithInfo` Rückruf Methode benachrichtigt den Profiler, wenn Funktionen aufgerufen werden, und ermöglicht es dem Profiler, die [ICorProfilerInfo3:: GetFunctionLeave3Info-Methode](icorprofilerinfo3-getfunctionleave3info-method.md) zu verwenden, um den Rückgabewert zu überprüfen. Für den Zugriff auf Rückgabewert Informationen `COR_PRF_ENABLE_FUNCTION_RETVAL` muss das-Flag festgelegt werden. Der Profiler kann die [ICorProfilerInfo:: SetEventMask-Methode](icorprofilerinfo-seteventmask-method.md) verwenden, um die Ereignisflags festzulegen, und dann die [ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3WithInfo-Methode](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) verwenden, um die Implementierung dieser Funktion zu registrieren.  
  
 Die `FunctionLeave3WithInfo` Funktion ist ein Rückruf. Sie müssen Sie implementieren. Die-Implementierung muss das `__declspec(naked)` Speicher Klassen Attribut verwenden.  
  
 Die Ausführungs-Engine speichert vor dem Aufrufen dieser Funktion keine Register.  
  
- Beim Eintrag müssen Sie alle von Ihnen verwendeten Register speichern, einschließlich der in der Gleit Komma Einheit (Gleit Komma Einheit).  
  
- Beim Beenden müssen Sie den Stapel wiederherstellen, indem Sie alle Parameter, die vom Aufrufer per Pushvorgang übermittelt wurden, per Ping löschen.  
  
 Die Implementierung von `FunctionLeave3WithInfo` sollte nicht blockieren, da Garbage Collection verzögert wird. Die-Implementierung sollte keine Garbage Collection versuchen, weil der Stapel möglicherweise nicht in einem Garbage Collection freundlichen Zustand ist. Wenn versucht wird, eine Garbage Collection auszuführen, wird die Laufzeit blockiert, bis von zurückgegeben wird `FunctionLeave3WithInfo` .  
  
 Die `FunctionLeave3WithInfo` Funktion darf keinen verwalteten Code anrufen oder eine verwaltete Speicher Belegung in irgendeiner Weise auslösen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Corprof. idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [GetFunctionLeave3Info](icorprofilerinfo3-getfunctionleave3info-method.md)
- [FunctionEnter3](functionenter3-function.md)
- [FunctionLeave3](functionleave3-function.md)
- [FunctionTailcall3](functiontailcall3-function.md)
- [FunctionEnter3WithInfo](functionenter3withinfo-function.md)
- [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md)
- [SetEnterLeaveFunctionHooks3](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md)
- [SetFunctionIDMapper2](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [Profilerstellung für globale statische Funktionen](profiling-global-static-functions.md)
