---
title: FunctionEnter-Funktion
ms.date: 03/30/2017
api_name:
- FunctionEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter
helpviewer_keywords:
- FunctionEnter function [.NET Framework profiling]
ms.assetid: bf4ffa50-4506-4dd4-aa13-a0457b47ca74
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9279e50630ea074b70955ca8ed218cd39a613b58
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781290"
---
# <a name="functionenter-function"></a>FunctionEnter-Funktion
Benachrichtigt den Profiler, dass das Steuerelement an eine Funktion übergeben wird.  
  
> [!NOTE]
>  Die `FunctionEnter` Funktion ist in .NET Framework, Version 2.0, veraltet und dessen Verwendung fallen die Leistungseinbußen. Verwenden der [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) stattdessen funktionieren.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
void __stdcall FunctionEnter (  
    [in]  FunctionID funcID  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `funcID`  
 [in] Der Bezeichner der Funktion an der Steuerelement übergeben wird.  
  
## <a name="remarks"></a>Hinweise  
 Die `FunctionEnter` Funktion ist ein Rückruf, müssen Sie sie implementieren. Verwenden Sie die Implementierung muss die `__declspec`(`naked`) Storage-Class-Attribut.  
  
 Die ausführungs-Engine werden keine Register gespeichert, vor dem Aufrufen dieser Funktion.  
  
- Auf den Eintrag müssen Sie alle Register speichern, die Sie, einschließlich derer in die Gleitkommaeinheit (FPU verwenden).  
  
- Beim Beenden müssen Sie im Stapel wiederherstellen, indem Sie alle Parameter, die durch den Aufrufer weitergegeben wurden entfernt.  
  
 Die Implementierung der `FunctionEnter` sollten nicht blockiert werden, da die Garbagecollection verzögert wird. Die Implementierung sollten eine Garbagecollection nicht versuchen, da der Stapel möglicherweise nicht in eine Garbage Collection geeigneten Zustand. Wenn eine Garbagecollection versucht wird, wird die Laufzeit blockiert, bis `FunctionEnter` zurückgibt.  
  
 Darüber hinaus die `FunctionEnter` Funktion darf keinen Aufrufen in verwaltetem Code oder auch eine verwaltete speicherbelegung.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** 1.1, 1.0  
  
## <a name="see-also"></a>Siehe auch

- [FunctionEnter2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [FunctionLeave2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [FunctionTailcall2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [SetEnterLeaveFunctionHooks2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [Profilerstellung für globale statische Funktionen](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
