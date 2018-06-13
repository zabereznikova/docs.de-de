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
ms.openlocfilehash: 844ac2a8aad4ce2cc6f70de2d5a53c7c0b6f4f6c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453143"
---
# <a name="icorprofilercallbackjitinlining-method"></a>ICorProfilerCallback::JITInlining-Methode
Benachrichtigt den Profiler, dass der Just-in-Time (JIT)-Compiler umgehend eine Funktion mit einer anderen Funktion einfügen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT JITInlining(  
    [in]  FunctionID callerId,  
    [in]  FunctionID calleeId,  
    [out] BOOL      *pfShouldInline);  
```  
  
#### <a name="parameters"></a>Parameter  
 `callerId`  
 [in] Die ID der Funktion, in dem die `calleeId` Funktion eingefügt werden.  
  
 `calleeId`  
 [in] Die ID der Funktion, die eingefügt werden.  
  
 `pfShouldInline`  
 [out] `true` ermöglichen das Einfügen erfolgen; anderenfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 Der Profiler kann festlegen, `pfShouldInline` auf `false` um zu verhindern, dass die `calleeId` Funktion eingefügt wird, in der `callerId` Funktion. Darüber hinaus der Profiler kann global Inline-Einfügung mit deaktivieren COR_PRF_DISABLE_INLINING-Wert, der die [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) Enumeration.  
  
 Inline eingefügte Funktionen lösen keine Ereignisse für die Eingabe oder verlassen. Aus diesem Grund muss der Profiler festgelegt `pfShouldInline` auf `false` ein genaues Aufrufdiagramm zu erstellen. Festlegen von `pfShouldInline` auf `false` beeinflusst die Leistung, da die Inline-Einfügung in der Regel wird die Geschwindigkeit erhöht und reduziert die Anzahl der separate Ereignisse der JIT-Kompilierung für die inserted-Methode.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
