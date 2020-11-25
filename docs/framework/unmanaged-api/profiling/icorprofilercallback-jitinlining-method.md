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
ms.openlocfilehash: cf68594620b24f2a5823aa423c5911f2d9d6b328
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725494"
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
  
## <a name="remarks"></a>Hinweise  

 Der Profiler kann `pfShouldInline` auf festlegen `false` , um zu verhindern, `calleeId` dass die Funktion in die Funktion eingefügt wird `callerId` . Außerdem kann der Profiler die Inline Einfügung mit dem COR_PRF_DISABLE_INLINING Wert der [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) -Enumeration global deaktivieren.  
  
 Inline-Funktionen, die Inline eingefügt werden, machen keine Ereignisse für die Eingabe oder den Abbruch Daher muss der Profiler auf festlegen, um `pfShouldInline` `false` ein genaues CallGraph zu generieren. `pfShouldInline`Wenn Sie auf festlegen `false` , wirkt sich dies auf die Leistung aus, da die Inline Einfügung normalerweise die Geschwindigkeit erhöht und die Anzahl der separaten JIT-Kompilierungs Ereignisse für die  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
