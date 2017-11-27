---
title: FunctionTailcall2-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FunctionTailcall2
api_location: mscorwks.dll
api_type: COM
f1_keywords: FunctionTailcall2
helpviewer_keywords: FunctionTailcall2 function [.NET Framework profiling]
ms.assetid: 249f9892-b5a9-41e1-b329-28a925904df6
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c1f9b0f6a83b774f6b308f7d4daa068eadebcce4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="functiontailcall2-function"></a>FunctionTailcall2-Funktion
Benachrichtigt den Profiler an, die gegenwärtig ausgeführte Funktion ist einen Endeaufruf an eine andere Funktion ausführen und enthält Informationen über den Stapelrahmen.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __stdcall FunctionTailcall2 (  
    [in] FunctionID         funcId,   
    [in] UINT_PTR           clientData,   
    [in] COR_PRF_FRAME_INFO func  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `funcId`  
 [in] Der Bezeichner der derzeit ausgeführten Funktion, die einen Endeaufruf durchzuführen.  
  
 `clientData`  
 [in] Der Funktionsbezeichner, die der Profiler zuvor über angegeben [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md), der derzeit ausgeführten Funktion, die einen Endeaufruf durchzuführen.  
  
 `func`  
 [in] Ein `COR_PRF_FRAME_INFO` Wert, der auf Informationen über den Stapelrahmen verweist.  
  
 Der Profiler sollte dies als ein nicht transparentes Handle, das an das Ausführungsmodul in zurückgegeben werden kann behandeln die [ICorProfilerInfo2:: Getfunctioninfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) Methode.  
  
## <a name="remarks"></a>Hinweise  
 Der Zielfunktion des Endaufrufs verwendet den aktuellen Stapelrahmen und direkt an den Aufrufer der Funktion, die den Endeaufruf vorgenommen zurück. Dies bedeutet, dass eine [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) Rückruf wird nicht für eine Funktion, die das Ziel ein Endeaufruf ist ausgestellt werden.  
  
 Der Wert von der `func` -Parameter ist ungültig, nachdem die `FunctionTailcall2` zurückgegeben, da der Wert möglicherweise geändert oder gelöscht werden.  
  
 Die `FunctionTailcall2` Funktion ist ein Rückruf; Sie müssen ihn implementieren. Verwenden Sie die Implementierung muss die `__declspec`(`naked`) Storage-Class-Attribut.  
  
 Das Ausführungsmodul werden keine Register gespeichert, vor dem Aufrufen dieser Funktion.  
  
-   Auf Eintrag müssen Sie alle Register speichern, die Sie, einschließlich die Gleitkommaeinheit (FPU verwenden).  
  
-   Beim Beenden müssen Sie den Stapel wiederherstellen, indem abholen alle Parameter, die durch den Aufrufer weitergegeben wurden.  
  
 Die Implementierung der `FunctionTailcall2` sollte nicht blockiert werden, da es die Garbagecollection verzögert. Die Implementierung sollten eine Garbagecollection nicht versuchen, da der Stapel möglicherweise nicht in eine Garbage Collection-freundliche-Status. Wenn eine Garbagecollection versucht wird, wird die Laufzeit blockiert, bis `FunctionTailcall2` zurückgegeben.  
  
 Darüber hinaus die `FunctionTailcall2` muss nicht Funktionsaufruf in verwaltetem Code oder auch eine verwaltete speicherbelegung.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [FunctionEnter2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [FunctionLeave2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [SetEnterLeaveFunctionHooks2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [Profilerstellung für globale statische Funktionen](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
