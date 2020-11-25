---
title: FunctionTailcall2-Funktion
ms.date: 03/30/2017
api_name:
- FunctionTailcall2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall2
helpviewer_keywords:
- FunctionTailcall2 function [.NET Framework profiling]
ms.assetid: 249f9892-b5a9-41e1-b329-28a925904df6
topic_type:
- apiref
ms.openlocfilehash: e1cd3ef78d303aaa325699e1bcdec95f077fef21
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703979"
---
# <a name="functiontailcall2-function"></a>FunctionTailcall2-Funktion

Benachrichtigt den Profiler, dass die gerade ausgeführte Funktion gerade einen Endaufruf einer anderen Funktion ausführt und Informationen über den Stapel Rahmen bereitstellt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
void __stdcall FunctionTailcall2 (  
    [in] FunctionID         funcId,
    [in] UINT_PTR           clientData,
    [in] COR_PRF_FRAME_INFO func  
);  
```  
  
## <a name="parameters"></a>Parameter

- `funcId`

  \[in] der Bezeichner der aktuell ausgeführten Funktion, die einen Tail-Aufruf durchführen soll.

- `clientData`

  \[in] der neu zugeordnete Funktions Bezeichner, den der Profiler zuvor über [FunctionIDMapper](functionidmapper-function.md)angegeben hat, der aktuell ausgeführten Funktion, die einen Tail-Aufruf durchführen soll.
  
- `func`

  \[in] ein- `COR_PRF_FRAME_INFO` Wert, der auf Informationen über den Stapel Rahmen zeigt.

  Der Profiler sollte dies als ein undurchsichtiges Handle behandeln, das an die Ausführungs-Engine in der [ICorProfilerInfo2:: GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) -Methode zurückgegeben werden kann.

## <a name="remarks"></a>Hinweise  

 Die Zielfunktion des Tail-Aufrufs verwendet den aktuellen Stapel Rahmen und kehrt direkt zum Aufrufer der Funktion zurück, die den Tail-Aufruf durchgeführt hat. Dies bedeutet, dass ein [FunctionLeave2](functionleave2-function.md) -Rückruf nicht für eine Funktion ausgegeben wird, die das Ziel eines Tail-Aufrufs ist.  
  
 Der Wert des- `func` Parameters ist nicht gültig, nachdem die Funktion zurückgegeben wurde, `FunctionTailcall2` da sich der Wert ändern oder zerstört werden kann.  
  
 Die `FunctionTailcall2` Funktion ist ein Rückruf. Sie müssen Sie implementieren. Die-Implementierung muss das `__declspec` `naked` Speicher Klassen Attribut () verwenden.  
  
 Die Ausführungs-Engine speichert vor dem Aufrufen dieser Funktion keine Register.  
  
- Beim Eintrag müssen Sie alle von Ihnen verwendeten Register speichern, einschließlich der in der Gleit Komma Einheit (Gleit Komma Einheit).  
  
- Beim Beenden müssen Sie den Stapel wiederherstellen, indem Sie alle Parameter, die vom Aufrufer per Pushvorgang übermittelt wurden, per Ping löschen.  
  
 Die Implementierung von `FunctionTailcall2` sollte nicht blockiert werden, da Sie Garbage Collection verzögert. Die-Implementierung sollte keine Garbage Collection versuchen, weil der Stapel möglicherweise nicht in einem Garbage Collection freundlichen Zustand ist. Wenn versucht wird, eine Garbage Collection auszuführen, wird die Laufzeit blockiert, bis von zurückgegeben wird `FunctionTailcall2` .  
  
 Außerdem darf die `FunctionTailcall2` Funktion keinen verwalteten Code aufruft oder eine verwaltete Speicher Belegung verursachen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Corprof. idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [FunctionEnter2-Funktion](functionenter2-function.md)
- [FunctionLeave2-Funktion](functionleave2-function.md)
- [SetEnterLeaveFunctionHooks2-Methode](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [Profilerstellung für globale statische Funktionen](profiling-global-static-functions.md)
