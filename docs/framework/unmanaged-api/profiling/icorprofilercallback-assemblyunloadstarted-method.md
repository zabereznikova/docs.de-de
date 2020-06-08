---
title: ICorProfilerCallback::AssemblyUnloadStarted-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyUnloadStarted
helpviewer_keywords:
- ICorProfilerCallback::AssemblyUnloadStarted method [.NET Framework profiling]
- AssemblyUnloadStarted method [.NET Framework profiling]
ms.assetid: 6e47b7e5-0335-4dd3-8c42-d3c07d62b102
topic_type:
- apiref
ms.openlocfilehash: 80054a8292c69b957664cb3573b0a8694c7f9fd2
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500402"
---
# <a name="icorprofilercallbackassemblyunloadstarted-method"></a>ICorProfilerCallback::AssemblyUnloadStarted-Methode
Benachrichtigt den Profiler, dass eine Assembly entladen wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT AssemblyUnloadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a>Parameter

- `assemblyId`

  \[in] identifiziert die Assembly, die entladen wird.

## <a name="remarks"></a>Bemerkungen  
 Der Wert von `assemblyId` ist für eine Informationsanforderung nach dem `AssemblyUnloadStarted` zurückkehren der Methode ungültig – Dies ist die letzte Möglichkeit des Profilers, Informationen zu dieser Assembly zu erhalten.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
- [AssemblyUnloadFinished-Methode](icorprofilercallback-assemblyunloadfinished-method.md)
