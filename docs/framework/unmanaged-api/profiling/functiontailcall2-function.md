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
ms.openlocfilehash: 60276327617ae24e9bdcebf958613c21d3808429
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175186"
---
# <a name="functiontailcall2-function"></a>FunctionTailcall2-Funktion
Benachrichtigt den Profiler, dass die aktuell ausgeführte Funktion einen Tail-Aufruf für eine andere Funktion ausführen wird, und stellt Informationen zum Stapelrahmen bereit.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
void __stdcall FunctionTailcall2 (  
    [in] FunctionID         funcId,
    [in] UINT_PTR           clientData,
    [in] COR_PRF_FRAME_INFO func  
);  
```  
  
## <a name="parameters"></a>Parameter

- `funcId`

  \[in] Der Bezeichner der aktuell ausgeführten Funktion, die im Begriff ist, einen Tail-Aufruf zu machen.

- `clientData`

  \[in] Der neu zugeordnete Funktionsbezeichner, den der Profiler zuvor über [FunctionIDMapper](functionidmapper-function.md)angegeben hat, der aktuell ausgeführten Funktion, die gerade einen Endaufruf ausführen soll.
  
- `func`

  \[in] `COR_PRF_FRAME_INFO` Ein Wert, der auf Informationen über den Stapelrahmen verweist.

  Der Profiler sollte dies als undurchsichtiges Handle behandeln, das an das Ausführungsmodul in der [ICorProfilerInfo2::GetFunctionInfo2-Methode](icorprofilerinfo2-getfunctioninfo2-method.md) zurückübergeben werden kann.

## <a name="remarks"></a>Bemerkungen  
 Die Zielfunktion des Tail-Aufrufs verwendet den aktuellen Stapelrahmen und kehrt direkt zum Aufrufer der Funktion zurück, die den Tail-Aufruf gemacht hat. Dies bedeutet, dass ein [FunctionLeave2-Rückruf](functionleave2-function.md) nicht für eine Funktion ausgegeben wird, die das Ziel eines Tail-Aufrufs ist.  
  
 Der Wert `func` des Parameters ist `FunctionTailcall2` ungültig, nachdem die Funktion zurückgegeben wurde, da sich der Wert ändern oder zerstören kann.  
  
 Die `FunctionTailcall2` Funktion ist ein Rückruf; Sie müssen es implementieren. Die Implementierung muss `__declspec``naked`das ( ) Storage-Class-Attribut verwenden.  
  
 Das Ausführungsmodul speichert keine Register, bevor diese Funktion aufgerufen wird.  
  
- Beim Eintrag müssen Sie alle Register speichern, die Sie verwenden, einschließlich der Register in der Gleitkommaeinheit (FPU).  
  
- Beim Beenden müssen Sie den Stapel wiederherstellen, indem Sie alle Parameter deaktivieren, die vom Aufrufer gedrückt wurden.  
  
 Die Implementierung `FunctionTailcall2` von sollte nicht blockiert werden, da die Garbage Collection verzögert wird. Die Implementierung sollte keine Garbage Collection versuchen, da sich der Stapel möglicherweise nicht in einem Garbage Collection-freundlichen Zustand befindet. Wenn versucht wird, eine Garbage Collection zu `FunctionTailcall2` sammeln, wird die Laufzeit blockiert, bis sie zurückgegeben wird.  
  
 Außerdem darf `FunctionTailcall2` die Funktion keinen verwalteten Code aufrufen oder in irgendeiner Weise eine verwaltete Speicherzuweisung verursachen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** CorProf.idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [FunctionEnter2-Funktion](functionenter2-function.md)
- [FunctionLeave2-Funktion](functionleave2-function.md)
- [SetEnterLeaveFunctionHooks2-Methode](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [Profilerstellung für globale statische Funktionen](profiling-global-static-functions.md)
