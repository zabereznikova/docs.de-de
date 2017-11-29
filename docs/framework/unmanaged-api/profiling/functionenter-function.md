---
title: FunctionEnter-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FunctionEnter
api_location: mscorwks.dll
api_type: COM
f1_keywords: FunctionEnter
helpviewer_keywords: FunctionEnter function [.NET Framework profiling]
ms.assetid: bf4ffa50-4506-4dd4-aa13-a0457b47ca74
topic_type: apiref
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0cd98e6db0f400d022fe0af4e96336616cbb7183
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="functionenter-function"></a>FunctionEnter-Funktion
Benachrichtigt den Profiler, dass Steuerelement an eine Funktion übergeben wird.  
  
> [!NOTE]
>  Die `FunctionEnter` -Funktion ist veraltet in .NET Framework, Version 2.0, und ihre Verwendung verursacht eine Leistungseinbuße. Verwenden der [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) stattdessen-Funktion.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __stdcall FunctionEnter (  
    [in]  FunctionID funcID  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `funcID`  
 [in] Der Bezeichner der Funktion an der Steuerelement übergeben wird.  
  
## <a name="remarks"></a>Hinweise  
 Die `FunctionEnter` Funktion ist ein Rückruf; Sie müssen ihn implementieren. Verwenden Sie die Implementierung muss die `__declspec`(`naked`) Storage-Class-Attribut.  
  
 Das Ausführungsmodul werden keine Register gespeichert, vor dem Aufrufen dieser Funktion.  
  
-   Auf Eintrag müssen Sie alle Register speichern, die Sie, einschließlich die Gleitkommaeinheit (FPU verwenden).  
  
-   Beim Beenden müssen Sie den Stapel wiederherstellen, indem abholen alle Parameter, die durch den Aufrufer weitergegeben wurden.  
  
 Die Implementierung der `FunctionEnter` sollte nicht blockiert werden, da es die Garbagecollection verzögert. Die Implementierung sollten eine Garbagecollection nicht versuchen, da der Stapel möglicherweise nicht in eine Garbage Collection-freundliche-Status. Wenn eine Garbagecollection versucht wird, wird die Laufzeit blockiert, bis `FunctionEnter` zurückgegeben.  
  
 Darüber hinaus die `FunctionEnter` muss nicht Funktionsaufruf in verwaltetem Code oder auch eine verwaltete speicherbelegung.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** 1.1, 1.0  
  
## <a name="see-also"></a>Siehe auch  
 [FunctionEnter2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [FunctionLeave2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [FunctionTailcall2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 [SetEnterLeaveFunctionHooks2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [Profilerstellung für globale statische Funktionen](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
