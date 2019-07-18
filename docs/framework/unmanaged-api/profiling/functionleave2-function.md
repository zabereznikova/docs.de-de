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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 124921f2f99ca4d8da88cc3713624383e225a26f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781269"
---
# <a name="functionleave2-function"></a>FunctionLeave2-Funktion
Benachrichtigt den Profiler, dass eine Funktion an den Aufrufer zurückgegeben wird, und Informationen über den Stapel Frame und Funktion-Rückgabewert enthält.  
  
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
 [in] Der Bezeichner der Funktion, die zurückgegeben wird.  
  
 `clientData`  
 [in] Der Funktionsbezeichner, die zuvor angegeben haben der Profiler über den [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) Funktion.  
  
 `func`  
 [in] Ein `COR_PRF_FRAME_INFO` -Wert, der auf Informationen über den Stapelrahmen verweist.  
  
 Der Profiler sollte dies als ein nicht transparentes Handle, das an die ausführungs-Engine in zurückgegeben werden kann behandeln die [ICorProfilerInfo2:: Getfunctioninfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) Methode.  
  
 `retvalRange`  
 [in] Ein Zeiger auf eine [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) Struktur, die den Speicherort des Rückgabewerts der Funktion angibt.  
  
 Informationen zum Rückgabewert, den Zugriff auf die `COR_PRF_ENABLE_FUNCTION_RETVAL` Flag festgelegt werden muss. Der Profiler kann mithilfe der [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) Methode, um die Ereignisflags festgelegt.  
  
## <a name="remarks"></a>Hinweise  
 Die Werte der `func` und `retvalRange` Parameter sind nicht gültig, nachdem die `FunctionLeave2` Funktion zurückgegeben werden, da die Werte möglicherweise geändert oder zerstört werden.  
  
 Die `FunctionLeave2` Funktion ist ein Rückruf, müssen Sie sie implementieren. Verwenden Sie die Implementierung muss die `__declspec`(`naked`) Storage-Class-Attribut.  
  
 Die ausführungs-Engine werden keine Register gespeichert, vor dem Aufrufen dieser Funktion.  
  
- Auf den Eintrag müssen Sie alle Register speichern, die Sie, einschließlich derer in die Gleitkommaeinheit (FPU verwenden).  
  
- Beim Beenden müssen Sie im Stapel wiederherstellen, indem Sie alle Parameter, die durch den Aufrufer weitergegeben wurden entfernt.  
  
 Die Implementierung der `FunctionLeave2` sollten nicht blockiert werden, da die Garbagecollection verzögert wird. Die Implementierung sollten eine Garbagecollection nicht versuchen, da der Stapel möglicherweise nicht in eine Garbage Collection geeigneten Zustand. Wenn eine Garbagecollection versucht wird, wird die Laufzeit blockiert, bis `FunctionLeave2` zurückgibt.  
  
 Darüber hinaus die `FunctionLeave2` Funktion darf keinen Aufrufen in verwaltetem Code oder auch eine verwaltete speicherbelegung.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [FunctionEnter2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [FunctionTailcall2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [SetEnterLeaveFunctionHooks2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [Profilerstellung für globale statische Funktionen](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
