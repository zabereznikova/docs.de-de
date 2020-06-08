---
title: ICorProfilerCallback::JITInlining-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITInlining
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITInlining
helpviewer_keywords:
- JITInlining method [.NET Framework profiling]
- ICorProfilerCallback::JITInlining method [.NET Framework profiling]
ms.assetid: c2f45801-dd38-4b78-b6b7-64397dc73f83
topic_type:
- apiref
ms.openlocfilehash: 13ce44c9c7a04b870278bc8926dd9fe5daf10bc3
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500012"
---
# <a name="icorprofilercallbackjitinlining-method"></a>ICorProfilerCallback::JITInlining-Methode
Benachrichtigt den Profiler, dass der JIT-Compiler (Just-in-Time) eine Funktion in der Zeile mit einer anderen Funktion einfügen soll.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT JITInlining(  
    [in]  FunctionID callerId,  
    [in]  FunctionID calleeId,  
    [out] BOOL      *pfShouldInline);  
```  
  
## <a name="parameters"></a>Parameter  
 `callerId`  
 in Die ID der Funktion, in die die `calleeId` Funktion eingefügt wird.  
  
 `calleeId`  
 in Die ID der Funktion, die eingefügt werden soll.  
  
 `pfShouldInline`  
 [out] `true` , um das Einfügen zuzulassen. andernfalls `false` .  
  
## <a name="remarks"></a>Bemerkungen  
 Der Profiler kann `pfShouldInline` auf festlegen `false` , um zu verhindern, `calleeId` dass die Funktion in die Funktion eingefügt wird `callerId` . Außerdem kann der Profiler die Inline Einfügung mit dem COR_PRF_DISABLE_INLINING Wert der [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) -Enumeration global deaktivieren.  
  
 Inline-Funktionen, die Inline eingefügt werden, machen keine Ereignisse für die Eingabe oder den Abbruch Daher muss der Profiler auf festlegen, um `pfShouldInline` `false` ein genaues CallGraph zu generieren. `pfShouldInline`Wenn Sie auf festlegen `false` , wirkt sich dies auf die Leistung aus, da die Inline Einfügung normalerweise die Geschwindigkeit erhöht und die Anzahl der separaten JIT-Kompilierungs Ereignisse für die  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
