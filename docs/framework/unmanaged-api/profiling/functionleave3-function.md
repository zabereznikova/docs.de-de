---
title: FunctionLeave3-Funktion
ms.date: 03/30/2017
api_name:
- FunctionLeave3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave3
helpviewer_keywords:
- FunctionLeave3 function [.NET Framework profiling]
ms.assetid: 5d798088-7992-48a0-ae55-d2a7ee31913f
topic_type:
- apiref
ms.openlocfilehash: 104a6c3c42c310513040cb45db7f51ffe729c19d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427440"
---
# <a name="functionleave3-function"></a>FunctionLeave3-Funktion
Benachrichtigt den Profiler, dass die Steuerung von einer Funktion zurückgegeben wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
void __stdcall FunctionLeave3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a>Parameter  
 `functionOrRemappedID`  
 in Der Bezeichner der Funktion, von der das Steuerelement zurückgegeben wird.  
  
## <a name="remarks"></a>Hinweise  
 Die `FunctionLeave3` Callback-Funktion benachrichtigt den Profiler, dass Funktionen aufgerufen werden, unterstützt jedoch keine Überprüfung des Rückgabewerts. Verwenden Sie die [ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) , um die Implementierung dieser Funktion zu registrieren.  
  
 Die `FunctionLeave3` Funktion ist ein Rückruf. Sie müssen ihn implementieren. Die-Implementierung muss das `__declspec(naked)`-Speicher Klassen Attribut verwenden.  
  
 Die Ausführungs-Engine speichert vor dem Aufrufen dieser Funktion keine Register.  
  
- Beim Eintrag müssen Sie alle von Ihnen verwendeten Register speichern, einschließlich der in der Gleit Komma Einheit (Gleit Komma Einheit).  
  
- Beim Beenden müssen Sie den Stapel wiederherstellen, indem Sie alle Parameter, die vom Aufrufer per Pushvorgang übermittelt wurden, per Ping löschen.  
  
 Die Implementierung von `FunctionLeave3` sollte nicht blockiert werden, da Sie Garbage Collection verzögert. Die-Implementierung sollte keine Garbage Collection versuchen, weil der Stapel möglicherweise nicht in einem Garbage Collection freundlichen Zustand ist. Wenn versucht wird, eine Garbage Collection auszuführen, wird die Laufzeit blockiert, bis `FunctionLeave3` zurückgibt.  
  
 Die `FunctionLeave3` Funktion darf keinen verwalteten Code abrufen oder eine verwaltete Speicher Belegung in irgendeiner Weise auslösen.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Corprof. idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [SetEnterLeaveFunctionHooks3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [SetFunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [Profilerstellung für globale statische Funktionen](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
