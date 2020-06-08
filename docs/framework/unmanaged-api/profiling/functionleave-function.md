---
title: FunctionLeave-Funktion
ms.date: 03/30/2017
api_name:
- FunctionLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave
helpviewer_keywords:
- FunctionLeave function [.NET Framework profiling]
ms.assetid: 18e89f45-e068-426a-be16-9f53a4346860
topic_type:
- apiref
ms.openlocfilehash: 836e4843ead940bc9f76ff6bdd0433e21e400afd
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500636"
---
# <a name="functionleave-function"></a>FunctionLeave-Funktion
Benachrichtigt den Profiler, dass eine Funktion im Begriff ist, zum Aufrufer zurückzukehren.  
  
> [!NOTE]
> Die- `FunctionLeave` Funktion ist in der .NET Framework 2,0 veraltet. Es wird weiterhin funktionieren, führt jedoch zu einer Leistungs Einbuße. Verwenden Sie stattdessen die [FunctionLeave2](functionleave2-function.md) -Funktion.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
void __stdcall FunctionLeave (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a>Parameter

- `funcID`

  \[in] der Bezeichner der Funktion, die zurückgibt.

## <a name="remarks"></a>Bemerkungen  
 Die `FunctionLeave` Funktion ist ein Rückruf. Sie müssen Sie implementieren. Die-Implementierung muss das `__declspec` `naked` Speicher Klassen Attribut () verwenden.  
  
 Die Ausführungs-Engine speichert vor dem Aufrufen dieser Funktion keine Register.  
  
- Beim Eintrag müssen Sie alle von Ihnen verwendeten Register speichern, einschließlich der in der Gleit Komma Einheit (Gleit Komma Einheit).  
  
- Beim Beenden müssen Sie den Stapel wiederherstellen, indem Sie alle Parameter, die vom Aufrufer per Pushvorgang übermittelt wurden, per Ping löschen.  
  
 Die Implementierung von `FunctionLeave` sollte nicht blockiert werden, da Sie Garbage Collection verzögert. Die-Implementierung sollte keine Garbage Collection versuchen, weil der Stapel möglicherweise nicht in einem Garbage Collection freundlichen Zustand ist. Wenn versucht wird, eine Garbage Collection auszuführen, wird die Laufzeit blockiert, bis von zurückgegeben wird `FunctionLeave` .  
  
 Außerdem darf die `FunctionLeave` Funktion keinen verwalteten Code aufruft oder eine verwaltete Speicher Belegung verursachen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Corprof. idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** 1,1, 1,0  
  
## <a name="see-also"></a>Weitere Informationen:

- [FunctionEnter2-Funktion](functionenter2-function.md)
- [FunctionLeave2-Funktion](functionleave2-function.md)
- [FunctionTailcall2-Funktion](functiontailcall2-function.md)
- [SetEnterLeaveFunctionHooks2-Methode](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [Profilerstellung für globale statische Funktionen](profiling-global-static-functions.md)
