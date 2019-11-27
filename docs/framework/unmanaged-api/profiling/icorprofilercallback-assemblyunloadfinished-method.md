---
title: ICorProfilerCallback::AssemblyUnloadFinished-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyUnloadFinished
helpviewer_keywords:
- AssemblyUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::AssemblyUnloadFinished method [.NET Framework profiling]
ms.assetid: 53fca564-84b1-44d4-9e21-17a492d2aae7
topic_type:
- apiref
ms.openlocfilehash: 01404d23707be90b6b15cf741632400d49f164de
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445151"
---
# <a name="icorprofilercallbackassemblyunloadfinished-method"></a>ICorProfilerCallback::AssemblyUnloadFinished-Methode
Benachrichtigt den Profiler, dass eine Assembly entladen wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT AssemblyUnloadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a>Parameter  
 `assemblyId`  
 in Identifiziert die Assembly, die entladen wird.  
  
 `hrStatus`  
 in Ein HRESULT, das angibt, ob die Assembly erfolgreich entladen wurde.  
  
## <a name="remarks"></a>Hinweise  
 Der Wert `assemblyId` ist für eine Informationsanforderung nicht gültig, nachdem die [ICorProfilerCallback:: AssemblyUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md) -Methode zurückgegeben wurde.  
  
 Einige Teile des Entladen der Assembly können nach dem `AssemblyUnloadFinished` Rückruf fortgesetzt werden. Ein HRESULT-Fehler in `hrStatus` deutet auf einen Fehler hin. Ein HRESULT-Erfolg in `hrStatus` gibt jedoch nur an, dass der erste Teil des Entladen der Assembly erfolgreich war.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
