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
ms.openlocfilehash: 738c98a0a37983faa71ea6e5eeaabb20639f604a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503137"
---
# <a name="icorprofilerfunctioncontrolsetilinstrumentedcodemap-method"></a>ICorProfilerFunctionControl::SetILInstrumentedCodeMap-Methode
Legt eine Codezuordnung für die angegebene Funktion mit den angegebenen Common Intermediate Language (CIL)-Zuordnungseinträgen fest.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetILInstrumentedCodeMap(  
    [in]   ULONG      cILMapEntries,  
    [in, size_is(cILMapEntries)] COR_IL_MAP rgILMapEntries[]);  
```  
  
## <a name="parameters"></a>Parameter  
 `cILMapEntries`  
 [in] Die Anzahl der Einträge in der Zuordnung.  
  
 `rgILMapEntries`  
 [in] Die vom Aufrufer reservierte Array mit COR_IL_MAP-Einträgen. Die Interpretation dieser Einträge ist die gleiche wie für die [ICorProfilerInfo:: Setup](icorprofilerinfo-setilinstrumentedcodemap-method.md) -Methode.  
  
## <a name="remarks"></a>Bemerkungen  
 Wenn die Zuordnung durch Aufrufen dieser Methode festgelegt wird, kann der Debugger die Zuordnung durch Aufrufen von [ICorDebugILCode2:: GetInstrumentedILMap](../debugging/icordebugilcode2-getinstrumentedilmap-method.md)abrufen. Er kann die Zuordnung außerdem intern verwenden, wenn IL-Offsets für Stapelüberwachung und variable Lebensdauer berechnet wird.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICorProfilerInfo-Schnittstelle](icorprofilerinfo-interface.md)
