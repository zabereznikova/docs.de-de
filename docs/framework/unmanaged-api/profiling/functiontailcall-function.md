---
title: FunctionTailcall-Funktion
ms.date: 03/30/2017
api_name:
- FunctionTailcall
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall
helpviewer_keywords:
- FunctionTailcall function [.NET Framework profiling]
ms.assetid: 66347e03-9a97-41e8-8f9d-89b80803f7b5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 11cf96f5957d41e0647c309a7b0bb08fc9b31c91
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452103"
---
# <a name="functiontailcall-function"></a>FunctionTailcall-Funktion
Benachrichtigt den Profiler an, die gegenwärtig ausgeführte Funktion ist einen Endeaufruf an eine andere Funktion ausführen.  
  
> [!NOTE]
>  Die `FunctionTailcall` -Funktion ist veraltet in .NET Framework, Version 2.0. Es sind weiterhin funktionsfähig, jedoch eine Leistungseinbuße entstehen. Verwenden der [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) stattdessen-Funktion.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __stdcall FunctionTailcall (  
    [in] FunctionID funcID  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `funcID`  
 [in] Der Bezeichner der derzeit ausgeführten Funktion, die einen Endeaufruf durchzuführen.  
  
## <a name="remarks"></a>Hinweise  
 Der Zielfunktion des Endaufrufs verwendet den aktuellen Stapelrahmen und direkt an den Aufrufer der Funktion, die den Endeaufruf vorgenommen zurück. Dies bedeutet, dass eine [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) Rückruf wird nicht für eine Funktion, die das Ziel ein Endeaufruf ist ausgestellt werden.  
  
 Die `FunctionTailcall` Funktion ist ein Rückruf; Sie müssen ihn implementieren. Verwenden Sie die Implementierung muss die `__declspec`(`naked`) Storage-Class-Attribut.  
  
 Das Ausführungsmodul werden keine Register gespeichert, vor dem Aufrufen dieser Funktion.  
  
-   Auf Eintrag müssen Sie alle Register speichern, die Sie, einschließlich die Gleitkommaeinheit (FPU verwenden).  
  
-   Beim Beenden müssen Sie den Stapel wiederherstellen, indem abholen alle Parameter, die durch den Aufrufer weitergegeben wurden.  
  
 Die Implementierung der `FunctionTailcall` sollte nicht blockiert werden, da es die Garbagecollection verzögert. Die Implementierung sollten eine Garbagecollection nicht versuchen, da der Stapel möglicherweise nicht in eine Garbage Collection-freundliche-Status. Wenn eine Garbagecollection versucht wird, wird die Laufzeit blockiert, bis `FunctionTailcall` zurückgegeben.  
  
 Darüber hinaus die `FunctionTailcall` muss nicht Funktionsaufruf in verwaltetem Code oder auch eine verwaltete speicherbelegung.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** 1.1, 1.0  
  
## <a name="see-also"></a>Siehe auch  
 [FunctionEnter2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [FunctionLeave2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [SetEnterLeaveFunctionHooks2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [Profilerstellung für globale statische Funktionen](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
