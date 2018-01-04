---
title: ICorProfilerFunctionEnum::Next-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerFunctionEnum.Next Method
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerFunctionEnum::Next
helpviewer_keywords:
- ICorProfilerFunctionEnum::Next method [.NET Framework profiling]
- Next method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 5ed4aa83-ce56-4b9f-9237-5da7587787fe
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fd9c01e014ee19c5e30fdc293d39787638e8b1d9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerfunctionenumnext-method"></a>ICorProfilerFunctionEnum::Next-Methode
Ruft die angegebene Anzahl von zusammenhängenden Funktionen aus einer sequenziellen Auflistung von Funktionen ab und beginnt damit an der aktuellen Position des Enumerators in der Sequenz.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Next([in]  ULONG      celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                    COR_PRF_FUNCTION ids[],  
             [out] ULONG *   pceltFetched);  
```  
  
#### <a name="parameters"></a>Parameter  
 `celt`  
 [in] Die Anzahl von abzurufenden Funktionen.  
  
 `ids`  
 [out] Ein Array von `COR_PRF_FUNCTION`-Werten, von denen jeder eine abgerufene Funktion darstellt.  
  
 `pceltFetched`  
 [out] Ein Zeiger auf die Anzahl von Funktionen, die tatsächlich im `ids`-Array zurückgegeben werden.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`celt` Elemente wurden zurückgegeben.|  
|S_FALSE|Es wurden weniger als `celt`-Elemente zurückgegeben, wodurch angegeben ist, dass die Enumeration abgeschlossen ist.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerFunctionEnum-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
