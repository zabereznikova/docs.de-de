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
ms.openlocfilehash: 6140ecda1d12c26e1936daee4eaad11cbd9b6ba4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781222"
---
# <a name="stacksnapshotcallback-function"></a>StackSnapshotCallback-Funktion
Stellt Informationen über jeden verwalteten Frame und die Ausführung von nicht verwalteten Frames im Stapel während eines Stackwalks, der von initiiert wird der Profiler die [ICorProfilerInfo2:: DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) Methode.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT __stdcall StackSnapshotCallback (  
    [in] FunctionID funcId,  
    [in] UINT_PTR ip,  
    [in] COR_PRF_FRAME_INFO frameInfo,  
    [in] ULONG32 contextSize,  
    [in] BYTE context[],  
    [in] void *clientData  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `funcId`  
 [in] Dieser Wert 0 (null) ist, ist dieser Rückruf für eine Ausführung von nicht verwalteten Frames; Andernfalls ist der Bezeichner einer verwalteten Funktion aus, und dieser Rückruf ist für einen verwalteten Frame.  
  
 `ip`  
 [in] Der Wert des Anweisungszeigers systemeigenem Code im Frame.  
  
 `frameInfo`  
 [in] Ein `COR_PRF_FRAME_INFO` -Wert, der Informationen über den Stapelrahmen verweist. Dieser Wert ist nur während dieses Rückrufs für die Verwendung gültig.  
  
 `contextSize`  
 [in] Die Größe des der `CONTEXT` -Struktur, die verweist die `context` Parameter.  
  
 `context`  
 [in] Ein Zeiger auf eine Win32- `CONTEXT` -Struktur, die den Zustand der CPU für diesen Frame darstellt.  
  
 Die `context` Parameter ist nur gültig, wenn das Flag COR_PRF_SNAPSHOT_CONTEXT übergebene `ICorProfilerInfo2::DoStackSnapshot`.  
  
 `clientData`  
 [in] Ein Zeiger auf die Clientdaten, das direkt vom übergeben wird `ICorProfilerInfo2::DoStackSnapshot`.  
  
## <a name="remarks"></a>Hinweise  
 Die `StackSnapshotCallback` Funktion wird von der Profilerwriter implementiert. Sie müssen die Komplexität der Arbeit in begrenzen `StackSnapshotCallback`. Beispielsweise wird bei Verwendung `ICorProfilerInfo2::DoStackSnapshot` auf asynchrone Weise, der Zielthread belegt sperren. Wenn code in `StackSnapshotCallback` erfordert die Sperren, kann ein Deadlock zur Folge haben.  
  
 Die `ICorProfilerInfo2::DoStackSnapshot` Methodenaufrufe der `StackSnapshotCallback` Funktion einmal pro verwalteten Frame oder einmal pro Ausführung nicht verwalteter Frames. Wenn `StackSnapshotCallback` wird aufgerufen, für eine Ausführung von nicht verwalteten Frames, kann der Profiler den Registerkontext verwenden (Verweis durch die `context` Parameter), einen eigenen nicht verwalteten Stapeldurchlauf durchführen. In diesem Fall die Win32 `CONTEXT` Struktur darstellt, die CPU-Status für den zuletzt abgelegte Frame in der Ausführung von nicht verwalteten Frames. Obwohl die Win32 `CONTEXT` Struktur enthält Werte für alle Register, sollten Sie eine verlassen nur auf die Werte der Stapelzeigerregister, Framezeigerregister, Anweisungszeigerregister und die permanenten (der beibehalten wird) Ganzzahl-Register.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [DoStackSnapshot-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)
- [Profilerstellung für globale statische Funktionen](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
