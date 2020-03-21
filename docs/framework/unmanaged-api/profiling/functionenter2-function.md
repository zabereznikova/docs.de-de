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
ms.openlocfilehash: 9aeb7a294beb10f9c2968e6161c72fdc362c4991
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177058"
---
# <a name="functionenter2-function"></a>FunctionEnter2-Funktion
Benachrichtigt den Profiler, dass das Steuerelement an eine Funktion übergeben wird, und stellt Informationen über den Stapelrahmen und die Funktionsargumente bereit. Diese Funktion ersetzt die [FunctionEnter-Funktion.](functionenter-function.md)  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
void __stdcall FunctionEnter2 (  
    [in]  FunctionID                       funcId,
    [in]  UINT_PTR                         clientData,
    [in]  COR_PRF_FRAME_INFO               func,
    [in]  COR_PRF_FUNCTION_ARGUMENT_INFO  *argumentInfo  
);  
```  
  
## <a name="parameters"></a>Parameter

- `funcId`

  \[in] Der Bezeichner der Funktion, an die das Steuerelement übergeben wird.

- `clientData`

  \[in] Der neu zugeordnete Funktionsbezeichner, den der Profiler zuvor mithilfe der [Funktion FunctionIDMapper](functionidmapper-function.md) angegeben hat.
  
- `func`

  \[in] `COR_PRF_FRAME_INFO` Ein Wert, der auf Informationen über den Stapelrahmen verweist.
  
  Der Profiler sollte dies als undurchsichtiges Handle behandeln, das an das Ausführungsmodul in der [ICorProfilerInfo2::GetFunctionInfo2-Methode](icorprofilerinfo2-getfunctioninfo2-method.md) zurückübergeben werden kann.  
  
- `argumentInfo`

  \[in] Ein Zeiger auf eine [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) Struktur, die die Positionen im Speicher der Argumente der Funktion angibt.

  Um auf Argumentinformationen zugreifen `COR_PRF_ENABLE_FUNCTION_ARGS` zu können, muss das Flag gesetzt werden. Der Profiler kann die [ICorProfilerInfo::SetEventMask-Methode](icorprofilerinfo-seteventmask-method.md) verwenden, um die Ereignisflags festzulegen.

## <a name="remarks"></a>Bemerkungen  
 Die Werte `func` der `argumentInfo` und Parameter sind `FunctionEnter2` ungültig, nachdem die Funktion zurückgegeben wurde, da sich die Werte ändern oder zerstört werden können.  
  
 Die `FunctionEnter2` Funktion ist ein Rückruf; Sie müssen es implementieren. Die Implementierung muss `__declspec``naked`das ( ) Storage-Class-Attribut verwenden.  
  
 Das Ausführungsmodul speichert keine Register, bevor diese Funktion aufgerufen wird.  
  
- Beim Eintrag müssen Sie alle Register speichern, die Sie verwenden, einschließlich der Register in der Gleitkommaeinheit (FPU).  
  
- Beim Beenden müssen Sie den Stapel wiederherstellen, indem Sie alle Parameter deaktivieren, die vom Aufrufer gedrückt wurden.  
  
 Die Implementierung `FunctionEnter2` von sollte nicht blockiert werden, da die Garbage Collection verzögert wird. Die Implementierung sollte keine Garbage Collection versuchen, da sich der Stapel möglicherweise nicht in einem Garbage Collection-freundlichen Zustand befindet. Wenn versucht wird, eine Garbage Collection zu `FunctionEnter2` sammeln, wird die Laufzeit blockiert, bis sie zurückgegeben wird.  
  
 Außerdem darf `FunctionEnter2` die Funktion keinen verwalteten Code aufrufen oder in irgendeiner Weise eine verwaltete Speicherzuweisung verursachen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** CorProf.idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [FunctionLeave2-Funktion](functionleave2-function.md)
- [FunctionTailcall2-Funktion](functiontailcall2-function.md)
- [SetEnterLeaveFunctionHooks2-Methode](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [Profilerstellung für globale statische Funktionen](profiling-global-static-functions.md)
