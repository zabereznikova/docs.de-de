---
title: ICorProfilerCallback::JITInlining-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.JITInlining
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::JITInlining
helpviewer_keywords:
- JITInlining method [.NET Framework profiling]
- ICorProfilerCallback::JITInlining method [.NET Framework profiling]
ms.assetid: c2f45801-dd38-4b78-b6b7-64397dc73f83
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b1e729a17101bbe9c659be729c685909932b5456
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
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
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
