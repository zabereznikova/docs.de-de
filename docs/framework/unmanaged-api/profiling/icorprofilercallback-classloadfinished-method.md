---
title: ICorProfilerCallback::ClassLoadFinished-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassLoadFinished
helpviewer_keywords:
- ClassLoadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ClassLoadFinished method [.NET Framework profiling]
ms.assetid: 3dd80fbe-d62d-4d4d-acf8-5b7d0efe607e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6508c989b143780090d582fd4175fe20bedeb770
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745435"
---
# <a name="icorprofilercallbackclassloadfinished-method"></a>ICorProfilerCallback::ClassLoadFinished-Methode
Benachrichtigt den Profiler, dass eine Klasse vollständig geladen wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ClassLoadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a>Parameter  
 `classId`  
 [in] Identifiziert die Klasse, die geladen wurde.  
  
 `hrStatus`  
 [in] Ein HRESULT, der angibt, ob die Klasse wurde erfolgreich geladen.  
  
## <a name="remarks"></a>Hinweise  
 Der Wert des `classId` gilt nicht für eine Anforderung von Informationen bis der `ClassLoadFinished` Methode wird aufgerufen.  
  
 Laden Sie die Klasse möglicherweise weiterhin nach den `ClassLoadFinished` Rückruf. Fehler-HRESULT in `hrStatus` gibt einen Fehler. Allerdings einen HRESULT-Erfolg in `hrStatus` gibt nur an, dass der erste Teil, das Laden der Klasse erfolgreich war.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [ClassLoadStarted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)
