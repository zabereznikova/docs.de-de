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
ms.openlocfilehash: afc0929b8f1b12f4e0b4551d826b8a1d59990154
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952885"
---
# <a name="functiontailcall-function"></a>FunctionTailcall-Funktion
Benachrichtigt den Profiler, dass die gerade ausgeführte Funktion gerade einen Endaufruf einer anderen Funktion ausführt.  
  
> [!NOTE]
> Die `FunctionTailcall` -Funktion ist in der .NET Framework Version 2,0 veraltet. Es wird weiterhin funktionieren, führt jedoch zu einer Leistungs Einbuße. Verwenden Sie stattdessen die [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) -Funktion.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __stdcall FunctionTailcall (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `funcID`  
 in Der Bezeichner der aktuell ausgeführten Funktion, die einen Tail-Aufruf durchführen soll.  
  
## <a name="remarks"></a>Hinweise  
 Die Zielfunktion des Tail-Aufrufs verwendet den aktuellen Stapel Rahmen und kehrt direkt zum Aufrufer der Funktion zurück, die den Tail-Aufruf durchgeführt hat. Dies bedeutet, dass ein [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) -Rückruf nicht für eine Funktion ausgegeben wird, die das Ziel eines Tail-Aufrufs ist.  
  
 Die `FunctionTailcall` Funktion ist ein Rückruf. Sie müssen Sie implementieren. Die-Implementierung muss das `__declspec`Speicher`naked`Klassen Attribut () verwenden.  
  
 Die Ausführungs-Engine speichert vor dem Aufrufen dieser Funktion keine Register.  
  
- Beim Eintrag müssen Sie alle von Ihnen verwendeten Register speichern, einschließlich der in der Gleit Komma Einheit (Gleit Komma Einheit).  
  
- Beim Beenden müssen Sie den Stapel wiederherstellen, indem Sie alle Parameter, die vom Aufrufer per Pushvorgang übermittelt wurden, per Ping löschen.  
  
 Die Implementierung von `FunctionTailcall` sollte nicht blockiert werden, da Sie Garbage Collection verzögert. Die-Implementierung sollte keine Garbage Collection versuchen, weil der Stapel möglicherweise nicht in einem Garbage Collection freundlichen Zustand ist. Wenn versucht wird, eine Garbage Collection auszuführen, wird die Laufzeit `FunctionTailcall` blockiert, bis von zurückgegeben wird.  
  
 Außerdem darf die `FunctionTailcall` Funktion keinen verwalteten Code aufruft oder eine verwaltete Speicher Belegung verursachen.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl  
  
 **Fern** CorGuids.lib  
  
 **.NET Framework Versionen:** 1,1, 1,0  
  
## <a name="see-also"></a>Siehe auch

- [FunctionEnter2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [FunctionLeave2-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [SetEnterLeaveFunctionHooks2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [Profilerstellung für globale statische Funktionen](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
