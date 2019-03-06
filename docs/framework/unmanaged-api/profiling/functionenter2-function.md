---
title: FunctionEnter2-Funktion
ms.date: 03/30/2017
api_name:
- FunctionEnter2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter2
helpviewer_keywords:
- FunctionEnter2 function [.NET Framework profiling]
ms.assetid: ce7a21f9-0ca3-4b92-bc4b-bb803cae3f51
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9fb9dd56cb19b62543d14ae02fe6f198c0164107
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468818"
---
# <a name="functionenter2-function"></a>FunctionEnter2-Funktion
Benachrichtigt den Profiler an, dass Steuerelement an eine Funktion übergeben wird und Informationen über den Stapelrahmen und die Funktionsargumente enthält. Diese Funktion ersetzt die [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) Funktion.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __stdcall FunctionEnter2 (  
    [in]  FunctionID                       funcId,   
    [in]  UINT_PTR                         clientData,   
    [in]  COR_PRF_FRAME_INFO               func,   
    [in]  COR_PRF_FUNCTION_ARGUMENT_INFO  *argumentInfo  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `funcId`  
 [in] Der Bezeichner der Funktion an der Steuerelement übergeben wird.  
  
 `clientData`  
 [in] Der Funktionsbezeichner, der der Profiler zuvor mithilfe des Parameters der [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) Funktion.  
  
 `func`  
 [in] Ein `COR_PRF_FRAME_INFO` -Wert, der auf Informationen über den Stapelrahmen verweist.  
  
 Der Profiler sollte dies als ein nicht transparentes Handle, das an die ausführungs-Engine in zurückgegeben werden kann behandeln die [ICorProfilerInfo2:: Getfunctioninfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) Methode.  
  
 `argumentInfo`  
 [in] Ein Zeiger auf eine [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) -Struktur, die Speicherorte im Arbeitsspeicher, der die Argumente der Funktion angibt.  
  
 Um die Argumentinformationen zugreifen, die `COR_PRF_ENABLE_FUNCTION_ARGS` Flag festgelegt werden muss. Der Profiler kann mithilfe der [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) Methode, um die Ereignisflags festgelegt.  
  
## <a name="remarks"></a>Hinweise  
 Die Werte der `func` und `argumentInfo` Parameter sind nicht gültig, nachdem die `FunctionEnter2` Funktion zurückgegeben werden, da die Werte möglicherweise geändert oder zerstört werden.  
  
 Die `FunctionEnter2` Funktion ist ein Rückruf, müssen Sie sie implementieren. Verwenden Sie die Implementierung muss die `__declspec`(`naked`) Storage-Class-Attribut.  
  
 Die ausführungs-Engine werden keine Register gespeichert, vor dem Aufrufen dieser Funktion.  
  
-   Auf den Eintrag müssen Sie alle Register speichern, die Sie, einschließlich derer in die Gleitkommaeinheit (FPU verwenden).  
  
-   Beim Beenden müssen Sie im Stapel wiederherstellen, indem Sie alle Parameter, die durch den Aufrufer weitergegeben wurden entfernt.  
  
 Die Implementierung der `FunctionEnter2` sollten nicht blockiert werden, da die Garbagecollection verzögert wird. Die Implementierung sollten eine Garbagecollection nicht versuchen, da der Stapel möglicherweise nicht in eine Garbage Collection geeigneten Zustand. Wenn eine Garbagecollection versucht wird, wird die Laufzeit blockiert, bis `FunctionEnter2` zurückgibt.  
  
 Darüber hinaus die `FunctionEnter2` Funktion darf keinen Aufrufen in verwaltetem Code oder auch eine verwaltete speicherbelegung.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [FunctionLeave2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [FunctionTailcall2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [SetEnterLeaveFunctionHooks2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [Profilerstellung für globale statische Funktionen](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
