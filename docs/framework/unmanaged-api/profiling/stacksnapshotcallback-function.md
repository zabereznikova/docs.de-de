---
title: StackSnapshotCallback-Funktion
ms.date: 03/30/2017
api_name:
- StackSnapshotCallback
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- StackSnapshotCallback
helpviewer_keywords:
- StackSnapshotCallback function [.NET Framework profiling]
ms.assetid: d0f235b2-91fe-4f82-b7d5-e5c64186eea8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 78fdcb69e73bc7238972d1a6ffb37b5ba91c7953
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="stacksnapshotcallback-function"></a>StackSnapshotCallback-Funktion
Stellt Informationen über jeden verwalteten Frame und jeder Ausführung von nicht verwalteten Frames auf dem Stapel während ein Stackwalk, die von initiiert wird der Profiler die [ICorProfilerInfo2:: DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) Methode.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT __stdcall StackSnapshotCallback (  
    [in] FunctionID funcId,  
    [in] UINT_PTR ip,  
    [in] COR_PRF_FRAME_INFO frameInfo,  
    [in] ULONG32 contextSize,  
    [in] BYTE context[],  
    [in] void *clientData  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `funcId`  
 [in] Wenn dieser Wert 0 (null) ist, ist dieser Rückruf zur Ausführung eines nicht verwalteten Frames. Andernfalls ist der Bezeichner einer verwalteten Funktion, und dieser Rückruf wird für einen verwalteten Frame.  
  
 `ip`  
 [in] Der Wert des Anweisungszeigers systemeigenem Code im Frame.  
  
 `frameInfo`  
 [in] Ein `COR_PRF_FRAME_INFO` Wert, der Informationen über den Stapelrahmen verweist. Dieser Wert ist nur während dieses Rückrufs für die Verwendung gültig.  
  
 `contextSize`  
 [in] Die Größe des der `CONTEXT` -Struktur, die verweist die `context` Parameter.  
  
 `context`  
 [in] Ein Zeiger auf eine Win32- `CONTEXT` -Struktur, die den Zustand der CPU für dieses Rahmens darstellt.  
  
 Die `context` Parameter ist nur gültig, wenn das COR_PRF_SNAPSHOT_CONTEXT-Flag übergeben wurde `ICorProfilerInfo2::DoStackSnapshot`.  
  
 `clientData`  
 [in] Ein Zeiger auf die Clientdaten, die gerade von übergeben werden `ICorProfilerInfo2::DoStackSnapshot`.  
  
## <a name="remarks"></a>Hinweise  
 Die `StackSnapshotCallback` Funktion wird vom Profilerwriter implementiert. Sie müssen die Komplexität der Arbeit in begrenzen `StackSnapshotCallback`. Beispielsweise, wenn mit `ICorProfilerInfo2::DoStackSnapshot` auf asynchrone Weise kann der Zielthread Sperren enthalten. Wenn code in `StackSnapshotCallback` erfordert die Sperren, kann ein Deadlock folgen.  
  
 Die `ICorProfilerInfo2::DoStackSnapshot` Methodenaufrufe der `StackSnapshotCallback` Funktion einmal pro verwalteten Frame oder einmal pro Ausführung von nicht verwalteten Frames. Wenn `StackSnapshotCallback` aufgerufen wird zur Ausführung eines nicht verwalteten Frames, kann der Profiler die Registerkontext verwenden (referenziert von der `context` Parameter) einen eigenen nicht verwalteten Stackwalk durchführen. In diesem Fall wird die Win32 `CONTEXT` Struktur darstellt, die CPU-Status für den zuletzt abgelegte Frame innerhalb der Ausführung von nicht verwalteten Frames. Obwohl die Win32 `CONTEXT` Struktur enthält die Werte für alle Register, Sie sollten sich nur auf die Werte der Stapelzeigerregister, Framezeigerregister, Anweisungszeigerregister und die nicht veränderlich (die beibehalten wird,) verlassen Ganzzahl-Register.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [DoStackSnapshot-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)  
 [Profilerstellung für globale statische Funktionen](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
