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
ms.openlocfilehash: 62035d623d56f7521e0a599a13bc20778e3f18d1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449901"
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
 [out] `true`, damit die Einfügung erfolgen kann. Andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 Der Profiler kann `pfShouldInline` auf `false` festlegen, um zu verhindern, dass die `calleeId` Funktion in die `callerId` Funktion eingefügt wird. Außerdem kann der Profiler die Inline Einfügung mit dem COR_PRF_DISABLE_INLINING Wert der [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) -Enumeration global deaktivieren.  
  
 Inline-Funktionen, die Inline eingefügt werden, machen keine Ereignisse für die Eingabe oder den Abbruch Daher muss der Profiler `pfShouldInline` auf `false` festlegen, um ein genaues CallGraph zu generieren. Wenn Sie `pfShouldInline` auf `false` festlegen, wirkt sich dies auf die Leistung aus, da die Inline Einfügung in der Regel die Geschwindigkeit erhöht und die Anzahl der separaten JIT-Kompilierungs Ereignisse für die  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
