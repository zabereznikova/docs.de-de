---
title: ICorProfilerCallback::AssemblyLoadFinished-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyLoadFinished
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadFinished method [.NET Framework profiling]
- AssemblyLoadFinished method [.NET Framework profiling]
ms.assetid: 86d98f39-52e6-4c61-a625-9760f695ff12
topic_type:
- apiref
ms.openlocfilehash: fd41463af0acac1bbe1a3d4515350905b6784f79
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685330"
---
# <a name="icorprofilercallbackassemblyloadfinished-method"></a>ICorProfilerCallback::AssemblyLoadFinished-Methode

Benachrichtigt den Profiler, dass eine Assembly den Ladevorgang abgeschlossen hat.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT AssemblyLoadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a>Parameter

- `assemblyId`

  \[in] identifiziert die Assembly, die geladen wurde.

- `hrStatus`

  \[in] ein HRESULT, das angibt, ob die Assembly erfolgreich geladen wurde.

## <a name="remarks"></a>Hinweise  

 Der Wert von `assemblyId` ist für eine Informationsanforderung erst gültig, wenn die- `AssemblyLoadFinished` Methode aufgerufen wird.  
  
 Einige Teile des Ladens der Assembly können nach dem Rückruf fortgesetzt werden `AssemblyLoadFinished` . Ein Fehler HRESULT in `hrStatus` weist auf einen Fehler hin. Ein HRESULT-Erfolg in `hrStatus` gibt jedoch nur an, dass der erste Teil des Ladens der Assembly erfolgreich war.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
