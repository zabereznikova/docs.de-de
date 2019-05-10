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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4e10b1a77586a09f8f5f7a59e811953fbede8773
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64586897"
---
# <a name="functiontailcall2-function"></a>FunctionTailcall2-Funktion
Benachrichtigt den Profiler an, die gerade ausgeführte Funktion ist einen Endeaufruf an eine andere Funktion ausführen und enthält Informationen zu den Stapelrahmen.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __stdcall FunctionTailcall2 (  
    [in] FunctionID         funcId,   
    [in] UINT_PTR           clientData,   
    [in] COR_PRF_FRAME_INFO func  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `funcId`  
 [in] Der Bezeichner der derzeit ausgeführten Funktion, die einen Endeaufruf durchzuführen.  
  
 `clientData`  
 [in] Der Funktionsbezeichner, die zuvor angegeben haben der Profiler über [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md), der derzeit ausgeführten Funktion, die einen Endeaufruf durchzuführen.  
  
 `func`  
 [in] Ein `COR_PRF_FRAME_INFO` -Wert, der auf Informationen über den Stapelrahmen verweist.  
  
 Der Profiler sollte dies als ein nicht transparentes Handle, das an die ausführungs-Engine in zurückgegeben werden kann behandeln die [ICorProfilerInfo2:: Getfunctioninfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) Methode.  
  
## <a name="remarks"></a>Hinweise  
 Die Zielfunktion des Endaufrufs verwendet den aktuellen Stapelrahmen, und es ergibt sich direkt an den Aufrufer der Funktion, die den Endeaufruf ausgeführt hat. Dies bedeutet, dass eine [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) Rückruf wird nicht für eine Funktion, die das Ziel ein Endeaufruf ausgegeben.  
  
 Der Wert des der `func` Parameter ist nicht gültig, nachdem die `FunctionTailcall2` Funktion beendet, weil der Wert möglicherweise geändert oder zerstört werden.  
  
 Die `FunctionTailcall2` Funktion ist ein Rückruf, müssen Sie sie implementieren. Verwenden Sie die Implementierung muss die `__declspec`(`naked`) Storage-Class-Attribut.  
  
 Die ausführungs-Engine werden keine Register gespeichert, vor dem Aufrufen dieser Funktion.  
  
- Auf den Eintrag müssen Sie alle Register speichern, die Sie, einschließlich derer in die Gleitkommaeinheit (FPU verwenden).  
  
- Beim Beenden müssen Sie im Stapel wiederherstellen, indem Sie alle Parameter, die durch den Aufrufer weitergegeben wurden entfernt.  
  
 Die Implementierung der `FunctionTailcall2` sollten nicht blockiert werden, da die Garbagecollection verzögert wird. Die Implementierung sollten eine Garbagecollection nicht versuchen, da der Stapel möglicherweise nicht in eine Garbage Collection geeigneten Zustand. Wenn eine Garbagecollection versucht wird, wird die Laufzeit blockiert, bis `FunctionTailcall2` zurückgibt.  
  
 Darüber hinaus die `FunctionTailcall2` Funktion darf keinen Aufrufen in verwaltetem Code oder auch eine verwaltete speicherbelegung.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [FunctionEnter2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [FunctionLeave2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [SetEnterLeaveFunctionHooks2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [Profilerstellung für globale statische Funktionen](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
