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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d7f000b6e944be7bd2e38f97e40176952cb19605
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450631"
---
# <a name="icorprofilercallbackassemblyloadfinished-method"></a>ICorProfilerCallback::AssemblyLoadFinished-Methode
Benachrichtigt den Profiler, dass eine Assembly geladen wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT AssemblyLoadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
#### <a name="parameters"></a>Parameter  
 `assemblyId`  
 [in] Identifiziert die Assembly, die geladen wurde.  
  
 `hrStatus`  
 [in] Ein HRESULT, das angibt, ob die Assembly vollständig erfolgreich geladen.  
  
## <a name="remarks"></a>Hinweise  
 Der Wert der `assemblyId` gilt nicht für eine Anforderung Informationen, bis die `AssemblyLoadFinished` Methode wird aufgerufen.  
  
 Einige Teile der beim Laden der Assembly möglicherweise weiterhin nach dem `AssemblyLoadFinished` Rückruf. Fehler-HRESULT in `hrStatus` gibt einen Fehler. Allerdings ein Erfolgs-HRESULT in `hrStatus` bedeutet nur, dass der erste Teil, das Laden der Assembly erfolgreich war.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
