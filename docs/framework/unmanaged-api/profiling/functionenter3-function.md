---
title: FunctionEnter3-Funktion
ms.date: 03/30/2017
api_name:
- FunctionEnter3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter3
helpviewer_keywords:
- FunctionEnter3 function [.NET Framework profiling]
ms.assetid: ef782c53-dae7-4990-b4ad-fddb1e690d4e
topic_type:
- apiref
ms.openlocfilehash: b435e1a3504dd623421f977ffc48264f8b0dcb5a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500701"
---
# <a name="functionenter3-function"></a>FunctionEnter3-Funktion
Benachrichtigt den Profiler, dass das Steuerelement an eine Funktion übermittelt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
void __stdcall FunctionEnter3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a>Parameter

- `functionOrRemappedID`

  \[in] der Bezeichner der Funktion, an die das Steuerelement übermittelt wird.

## <a name="remarks"></a>Bemerkungen  
 Die `FunctionEnter3` Rückruffunktion benachrichtigt den Profiler, dass Funktionen aufgerufen werden, unterstützt jedoch keine Argument Überprüfung. Verwenden Sie die [ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3-Methode](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) , um die Implementierung dieser Funktion zu registrieren.  
  
 Die `FunctionEnter3` Funktion ist ein Rückruf. Sie müssen Sie implementieren. Die-Implementierung muss das `__declspec(naked)` Speicher Klassen Attribut verwenden.  
  
 Die Ausführungs-Engine speichert vor dem Aufrufen dieser Funktion keine Register.  
  
- Beim Eintrag müssen Sie alle von Ihnen verwendeten Register speichern, einschließlich der in der Gleit Komma Einheit (Gleit Komma Einheit).  
  
- Beim Beenden müssen Sie den Stapel wiederherstellen, indem Sie alle Parameter, die vom Aufrufer per Pushvorgang übermittelt wurden, per Ping löschen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Corprof. idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [FunctionLeave3](functionleave3-function.md)
- [FunctionTailcall3](functiontailcall3-function.md)
- [FunctionEnter3WithInfo](functionenter3withinfo-function.md)
- [FunctionLeave3WithInfo](functionleave3withinfo-function.md)
- [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md)
- [SetEnterLeaveFunctionHooks3](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md)
- [SetFunctionIDMapper2](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [Profilerstellung für globale statische Funktionen](profiling-global-static-functions.md)
