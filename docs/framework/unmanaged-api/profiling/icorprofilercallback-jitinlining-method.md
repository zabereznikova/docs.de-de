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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 60183291fda551e328ee1def03c02240314a71e4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178268"
---
# <a name="icorprofilercallbackjitinlining-method"></a>ICorProfilerCallback::JITInlining-Methode
Benachrichtigt den Profiler, dass der just-in-Time (JIT)-Compiler zum Einfügen einer Funktion mit einer anderen Funktion.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT JITInlining(  
    [in]  FunctionID callerId,  
    [in]  FunctionID calleeId,  
    [out] BOOL      *pfShouldInline);  
```  
  
## <a name="parameters"></a>Parameter  
 `callerId`  
 [in] Die ID der Funktion, in dem die `calleeId` Funktion eingefügt werden soll.  
  
 `calleeId`  
 [in] Die ID der Funktion eingefügt werden soll.  
  
 `pfShouldInline`  
 [out] `true` können die Einfügung auftritt; andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 Der Profiler kann festlegen `pfShouldInline` zu `false` um zu verhindern, dass die `calleeId` Funktion eingefügt wird, in der `callerId` Funktion. Darüber hinaus der Profiler kann global deaktivieren, Inline-Einfügung COR_PRF_DISABLE_INLINING-Wert, der mit der [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) Enumeration.  
  
 Inlinefunktionen eingefügt lösen keine Ereignisse für wechselt oder diesen verlässt. Aus diesem Grund muss der Profiler festgelegt `pfShouldInline` zu `false` um ein genaues Aufrufdiagramm zu erstellen. Festlegen von `pfShouldInline` zu `false` wird die Leistung beeinträchtigen, da Inline-Einfügung in der Regel die Geschwindigkeit erhöht und die Anzahl der separate Ereignisse der JIT-Kompilierung für die inserted-Methode verringert.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
