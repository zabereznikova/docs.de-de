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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9f2073ed1ba2ed8644d825d24f36166e4f2ed3b4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478374"
---
# <a name="functionenter3-function"></a>FunctionEnter3-Funktion
Benachrichtigt den Profiler, dass das Steuerelement an eine Funktion übergeben wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __stdcall FunctionEnter3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a>Parameter  
 `functionOrRemappedID`  
 [in] Der Bezeichner der Funktion an der Steuerelement übergeben wird.  
  
## <a name="remarks"></a>Hinweise  
 Die `FunctionEnter3` Rückruffunktion benachrichtigt den Profiler an, wie Funktionen aufgerufen werden, aber es keine Unterstützung für Argument-Überprüfung ist. Verwenden der [ICorProfilerInfo3:: Setenterleavefunctionhooks3-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) auf die Implementierung dieser Funktion zu registrieren.  
  
 Die `FunctionEnter3` Funktion ist ein Rückruf, müssen Sie sie implementieren. Verwenden Sie die Implementierung muss die `__declspec(naked)` Storage-Class-Attribut.  
  
 Die ausführungs-Engine werden keine Register gespeichert, vor dem Aufrufen dieser Funktion.  
  
-   Auf den Eintrag müssen Sie alle Register speichern, die Sie, einschließlich derer in die Gleitkommaeinheit (FPU verwenden).  
  
-   Beim Beenden müssen Sie im Stapel wiederherstellen, indem Sie alle Parameter, die durch den Aufrufer weitergegeben wurden entfernt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [SetEnterLeaveFunctionHooks3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [SetFunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [Profilerstellung für globale statische Funktionen](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
