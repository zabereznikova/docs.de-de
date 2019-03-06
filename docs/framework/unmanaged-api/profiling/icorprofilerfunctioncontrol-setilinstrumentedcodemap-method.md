---
title: ICorProfilerFunctionControl::SetILInstrumentedCodeMap-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl.SetILInstrumentedCodeMap
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl::SetILInstrumentedCodeMap
helpviewer_keywords:
- ICorProfilerFunctionControl::SetILInstrumentedCodeMap method [.NET Framework profiling]
- SetIILInstrumentedCodeMap method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: ecf56646-7e5f-46c4-8340-f3a04e88920f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 328702b48de8f3c471783743fb84a271f608a97a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57477126"
---
# <a name="icorprofilerfunctioncontrolsetilinstrumentedcodemap-method"></a>ICorProfilerFunctionControl::SetILInstrumentedCodeMap-Methode
Legt eine Codezuordnung für die angegebene Funktion mit den angegebenen Common Intermediate Language (CIL)-Zuordnungseinträgen fest.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetILInstrumentedCodeMap(  
    [in]   ULONG      cILMapEntries,  
    [in, size_is(cILMapEntries)] COR_IL_MAP rgILMapEntries[]);  
```  
  
## <a name="parameters"></a>Parameter  
 `cILMapEntries`  
 [in] Die Anzahl der Einträge in der Zuordnung.  
  
 `rgILMapEntries`  
 [in] Das vom Aufrufer reserviertes Array von COR_IL_MAP-Einträgen. Die Interpretation dieser Einträge ist dieselbe wie für die [ICorProfilerInfo:: SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) Methode.  
  
## <a name="remarks"></a>Hinweise  
 Festlegen der Zuordnung durch Aufrufen dieser Methode ermöglicht dem Debugger zum Abrufen der Zuordnung durch Aufrufen von [icordebugilcode2:: Getinstrumentedilmap](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md). Er kann die Zuordnung außerdem intern verwenden, wenn IL-Offsets für Stapelüberwachung und variable Lebensdauer berechnet wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
