---
title: FunctionLeave2-Funktion
ms.date: 03/30/2017
api_name:
- FunctionLeave2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave2
helpviewer_keywords:
- FunctionLeave2 function [.NET Framework profiling]
ms.assetid: 8cdac941-8b94-4497-b874-4e571785f3fe
topic_type:
- apiref
ms.openlocfilehash: e40687f7f843dc563801bb01b503d2ae94a094fc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446015"
---
# <a name="functionleave2-function"></a>FunctionLeave2-Funktion
Benachrichtigt den Profiler, dass eine Funktion im Begriff ist, zum Aufrufer zurückzukehren, und stellt Informationen zum Stapel Rahmen und Funktionsrückgabewert bereit.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
void __stdcall FunctionLeave2 (  
    [in]  FunctionID                        funcId,  
    [in]  UINT_PTR                          clientData,  
    [in]  COR_PRF_FRAME_INFO                func,  
    [in]  COR_PRF_FUNCTION_ARGUMENT_RANGE  *retvalRange  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `funcId`  
 in Der Bezeichner der Funktion, die zurückgibt.  
  
 `clientData`  
 in Der neu zugeordnete Funktions Bezeichner, den der Profiler zuvor über die [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) -Funktion angegeben hat.  
  
 `func`  
 in Ein `COR_PRF_FRAME_INFO` Wert, der auf Informationen über den Stapel Rahmen zeigt.  
  
 Der Profiler sollte dies als ein undurchsichtiges Handle behandeln, das an die Ausführungs-Engine in der [ICorProfilerInfo2:: GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) -Methode zurückgegeben werden kann.  
  
 `retvalRange`  
 in Ein Zeiger auf eine [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) -Struktur, die die Speicherposition des Rückgabewerts der Funktion angibt.  
  
 Um auf Rückgabewert Informationen zugreifen zu können, muss das `COR_PRF_ENABLE_FUNCTION_RETVAL`-Flag festgelegt werden. Der Profiler kann die [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) -Methode verwenden, um die Ereignisflags festzulegen.  
  
## <a name="remarks"></a>Hinweise  
 Die Werte der Parameter "`func`" und "`retvalRange`" sind nicht gültig, nachdem die `FunctionLeave2` Funktion zurückgegeben wurde, da sich die Werte ändern oder gelöscht werden können.  
  
 Die `FunctionLeave2` Funktion ist ein Rückruf. Sie müssen ihn implementieren. Die-Implementierung muss das `__declspec`(`naked`)-Speicher Klassen Attribut verwenden.  
  
 Die Ausführungs-Engine speichert vor dem Aufrufen dieser Funktion keine Register.  
  
- Beim Eintrag müssen Sie alle von Ihnen verwendeten Register speichern, einschließlich der in der Gleit Komma Einheit (Gleit Komma Einheit).  
  
- Beim Beenden müssen Sie den Stapel wiederherstellen, indem Sie alle Parameter, die vom Aufrufer per Pushvorgang übermittelt wurden, per Ping löschen.  
  
 Die Implementierung von `FunctionLeave2` sollte nicht blockiert werden, da Sie Garbage Collection verzögert. Die-Implementierung sollte keine Garbage Collection versuchen, weil der Stapel möglicherweise nicht in einem Garbage Collection freundlichen Zustand ist. Wenn versucht wird, eine Garbage Collection auszuführen, wird die Laufzeit blockiert, bis `FunctionLeave2` zurückgibt.  
  
 Außerdem darf die `FunctionLeave2` Funktion keinen verwalteten Code aufruft oder eine verwaltete Speicher Belegung verursachen.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Corprof. idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [FunctionEnter2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [FunctionTailcall2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [SetEnterLeaveFunctionHooks2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [Profilerstellung für globale statische Funktionen](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
