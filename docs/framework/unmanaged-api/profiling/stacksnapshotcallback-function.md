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
ms.openlocfilehash: a0f5316900dedc6c8983f9e670f60767ed783a40
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493993"
---
# <a name="stacksnapshotcallback-function"></a>StackSnapshotCallback-Funktion
Stellt dem Profiler Informationen über jeden verwalteten Frame und jede ausführen nicht verwalteter Frames auf dem Stapel während eines Stackwalk bereit, der von der [ICorProfilerInfo2::D ostacksnapshot](icorprofilerinfo2-dostacksnapshot-method.md) -Methode initiiert wird.  
  
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
 in Wenn dieser Wert 0 (null) ist, ist dieser Rückruf für die Durchführung nicht verwalteter Frames vorgesehen. andernfalls handelt es sich um den Bezeichner einer verwalteten Funktion, und dieser Rückruf gilt für einen verwalteten Frame.  
  
 `ip`  
 in Der Wert des systemeigenen Code Anweisungs Zeigers im Frame.  
  
 `frameInfo`  
 in Ein- `COR_PRF_FRAME_INFO` Wert, der auf Informationen über den Stapel Rahmen verweist. Dieser Wert kann nur während dieses Rückrufs verwendet werden.  
  
 `contextSize`  
 in Die Größe der- `CONTEXT` Struktur, auf die vom-Parameter verwiesen wird `context` .  
  
 `context`  
 in Ein Zeiger auf eine Win32-- `CONTEXT` Struktur, die den Zustand der CPU für diesen Frame darstellt.  
  
 Der- `context` Parameter ist nur gültig, wenn das COR_PRF_SNAPSHOT_CONTEXT-Flag übergeben wurde `ICorProfilerInfo2::DoStackSnapshot` .  
  
 `clientData`  
 in Ein Zeiger auf die Client Daten, der direkt von der übermittelt wird `ICorProfilerInfo2::DoStackSnapshot` .  
  
## <a name="remarks"></a>Bemerkungen  
 Die- `StackSnapshotCallback` Funktion wird vom Profiler-Writer implementiert. Sie müssen die Komplexität der in durchgeführten Arbeit einschränken `StackSnapshotCallback` . Wenn Sie beispielsweise `ICorProfilerInfo2::DoStackSnapshot` asynchron verwenden, kann der Zielthread Sperren aufrechterhalten. Wenn Code in `StackSnapshotCallback` die gleichen Sperren erfordert, könnte ein Deadlock entstehen.  
  
 Die- `ICorProfilerInfo2::DoStackSnapshot` Methode ruft die- `StackSnapshotCallback` Funktion einmal pro verwaltetem Frame oder einmal pro ausführen nicht verwalteter Frames auf. Wenn `StackSnapshotCallback` für eine Ausführung nicht verwalteter Frames aufgerufen wird, kann der Profiler den Registrierungs Kontext (auf den der- `context` Parameter verweist) verwenden, um einen eigenen nicht verwalteten Stackwalk auszuführen. In diesem Fall stellt die Win32- `CONTEXT` Struktur den CPU-Status für den zuletzt über drückten Rahmen während der Durchführung nicht verwalteter Frames dar. Obwohl die Win32- `CONTEXT` Struktur Werte für alle Register enthält, sollten Sie sich nur auf die Werte der Stapelzeiger Register, das Frame Zeiger Register, das Anweisungs Zeiger Register und die nicht flüchtigen (d. h. beibehaltenen) ganzzahligen Register verlassen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Corprof. idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [DoStackSnapshot-Methode](icorprofilerinfo2-dostacksnapshot-method.md)
- [Profilerstellung für globale statische Funktionen](profiling-global-static-functions.md)
