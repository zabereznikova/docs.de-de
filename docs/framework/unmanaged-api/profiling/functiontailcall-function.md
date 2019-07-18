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
ms.openlocfilehash: 4686710c105ef002fe30f8b6e167d760088913ce
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64586999"
---
# <a name="functiontailcall-function"></a>FunctionTailcall-Funktion
Benachrichtigt den Profiler an, die gegenwärtig ausgeführte Funktion ist einen Endeaufruf an eine andere Funktion ausführen.  
  
> [!NOTE]
>  Die `FunctionTailcall` Funktion ist in .NET Framework, Version 2.0 veraltet. Diese Funktion bleibt weiterhin funktioniert, jedoch eine Leistungseinbuße fallen. Verwenden der [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) stattdessen funktionieren.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __stdcall FunctionTailcall (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `funcID`  
 [in] Der Bezeichner der derzeit ausgeführten Funktion, die einen Endeaufruf durchzuführen.  
  
## <a name="remarks"></a>Hinweise  
 Die Zielfunktion des Endaufrufs verwendet den aktuellen Stapelrahmen, und es ergibt sich direkt an den Aufrufer der Funktion, die den Endeaufruf ausgeführt hat. Dies bedeutet, dass eine [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) Rückruf wird nicht für eine Funktion, die das Ziel ein Endeaufruf ausgegeben.  
  
 Die `FunctionTailcall` Funktion ist ein Rückruf, müssen Sie sie implementieren. Verwenden Sie die Implementierung muss die `__declspec`(`naked`) Storage-Class-Attribut.  
  
 Die ausführungs-Engine werden keine Register gespeichert, vor dem Aufrufen dieser Funktion.  
  
- Auf den Eintrag müssen Sie alle Register speichern, die Sie, einschließlich derer in die Gleitkommaeinheit (FPU verwenden).  
  
- Beim Beenden müssen Sie im Stapel wiederherstellen, indem Sie alle Parameter, die durch den Aufrufer weitergegeben wurden entfernt.  
  
 Die Implementierung der `FunctionTailcall` sollten nicht blockiert werden, da die Garbagecollection verzögert wird. Die Implementierung sollten eine Garbagecollection nicht versuchen, da der Stapel möglicherweise nicht in eine Garbage Collection geeigneten Zustand. Wenn eine Garbagecollection versucht wird, wird die Laufzeit blockiert, bis `FunctionTailcall` zurückgibt.  
  
 Darüber hinaus die `FunctionTailcall` Funktion darf keinen Aufrufen in verwaltetem Code oder auch eine verwaltete speicherbelegung.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** 1.1, 1.0  
  
## <a name="see-also"></a>Siehe auch

- [FunctionEnter2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [FunctionLeave2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [SetEnterLeaveFunctionHooks2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [Profilerstellung für globale statische Funktionen](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
