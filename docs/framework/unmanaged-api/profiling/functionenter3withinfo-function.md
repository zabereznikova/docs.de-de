---
title: FunctionEnter3WithInfo-Funktion
ms.date: 03/30/2017
api_name:
- FunctionEnter3WithInfo
api_location:
- mscorwks.cll
api_type:
- COM
f1_keywords:
- FunctionEnter3WithInfo
helpviewer_keywords:
- FunctionEnter3WithInfo function [.NET Framework profiling]
ms.assetid: 277c3344-d0cb-431e-beae-eb1eeeba8eea
topic_type:
- apiref
ms.openlocfilehash: b511c5abe10ab6c0ec856a5686b082132ed4a5d9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722860"
---
# <a name="functionenter3withinfo-function"></a>FunctionEnter3WithInfo-Funktion

Benachrichtigt den Profiler, dass die Steuerung an eine Funktion übermittelt wird, und stellt ein Handle bereit, das an die [ICorProfilerInfo3:: GetFunctionEnter3Info-Methode](icorprofilerinfo3-getfunctionenter3info-method.md) zum Abrufen des Stapel Rahmens und der Funktionsargumente übermittelt werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
void __stdcall FunctionEnter3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a>Parameter

- `functionIDOrClientID`

  \[in] der Bezeichner der Funktion, an die das Steuerelement übermittelt wird.

- `eltInfo`

  \[in] ein undurchsichtiges handle, das Informationen zu einem angegebenen Stapel Rahmen darstellt. Dieses Handle ist nur während des Rückrufs gültig, an den er übermittelt wird.

## <a name="remarks"></a>Hinweise  

 Die `FunctionEnter3WithInfo` Rückruf Methode benachrichtigt den Profiler, wenn Funktionen aufgerufen werden, und ermöglicht es dem Profiler, mithilfe der [ICorProfilerInfo3:: GetFunctionEnter3Info-Methode](icorprofilerinfo3-getfunctionenter3info-method.md) Argument Werte zu überprüfen. Für den Zugriff auf Argument Informationen `COR_PRF_ENABLE_FUNCTION_ARGS` muss das-Flag festgelegt werden. Der Profiler kann die [ICorProfilerInfo:: SetEventMask-Methode](icorprofilerinfo-seteventmask-method.md) verwenden, um die Ereignisflags festzulegen, und dann die [ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3WithInfo-Methode](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) verwenden, um die Implementierung dieser Funktion zu registrieren.  
  
 Die `FunctionEnter3WithInfo` Funktion ist ein Rückruf. Sie müssen Sie implementieren. Die-Implementierung muss das `__declspec(naked)` Speicher Klassen Attribut verwenden.  
  
 Die Ausführungs-Engine speichert vor dem Aufrufen dieser Funktion keine Register.  
  
- Beim Eintrag müssen Sie alle von Ihnen verwendeten Register speichern, einschließlich der in der Gleit Komma Einheit (Gleit Komma Einheit).  
  
- Beim Beenden müssen Sie den Stapel wiederherstellen, indem Sie alle Parameter, die vom Aufrufer per Pushvorgang übermittelt wurden, per Ping löschen.  
  
 Die Implementierung von `FunctionEnter3WithInfo` sollte nicht blockieren, da Garbage Collection verzögert wird. Die-Implementierung sollte keine Garbage Collection versuchen, weil der Stapel möglicherweise nicht in einem Garbage Collection freundlichen Zustand ist. Wenn versucht wird, eine Garbage Collection auszuführen, wird die Laufzeit blockiert, bis von zurückgegeben wird `FunctionEnter3WithInfo` .  
  
 Die `FunctionEnter3WithInfo` Funktion darf keinen verwalteten Code anrufen oder eine verwaltete Speicher Belegung in irgendeiner Weise auslösen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Corprof. idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md)
- [FunctionEnter3](functionenter3-function.md)
- [FunctionLeave3](functionleave3-function.md)
- [Profilerstellung für globale statische Funktionen](profiling-global-static-functions.md)
