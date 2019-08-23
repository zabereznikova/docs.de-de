---
title: ICorProfilerInfo7::ReadInMemorySymbols
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo7.ReadInMemorySymbols
api_location:
- CorProf.idl
- CorProf.h
- CorGuids.lib
api_type:
- COM
ms.assetid: 1745a0b9-8332-4777-a670-b549bff3b901
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 95b463b23c230d620d746e48da49d75238ef2cb7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955377"
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a>ICorProfilerInfo7::ReadInMemorySymbols
[Wird nur in .NET Framework 4.6.1 und höheren Versionen unterstützt]  
  
 Liest Bytes aus einem in-Memory-symbolstream.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ReadInMemorySymbols(  
        [in] ModuleID moduleId,  
        [in] DWORD symbolsReadOffset,  
        [out] BYTE* pSymbolBytes,  
        [in] DWORD countSymbolBytes,  
        [out] DWORD* pCountSymbolBytesRead  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `moduleId`  
 in Der Bezeichner des Moduls, das den in-Memory-Datenstrom enthält.  
  
 `symbolsReadOffset`  
 in Der Offset innerhalb des in-Memory-Streams, an dem mit dem Lesen von Bytes begonnen werden soll.  
  
 `pSymbolBytes`  
 vorgenommen Ein Zeiger auf den Puffer, in den die Daten kopiert werden. Für den Puffer muss `countSymbolBytes` Speicherplatz verfügbar sein.  
  
 `countSymbolBytes`  
 in Die Anzahl der zu kopierenden Bytes.  
  
 `pCountSymbolBytesRead`  
 vorgenommen Diese Methode gibt die tatsächliche Anzahl von gelesenen Bytes zurück.  
  
## <a name="return-value"></a>Rückgabewert  
 `S_OK`, wenn eine Anzahl von Bytes ungleich 0 (null) gelesen wurde.  
  
 `CORPROF_E_MODULE_IS_DYNAMIC`, wenn das Modul mithilfe <xref:System.Reflection.Emit>von erstellt wurde.  
  
## <a name="remarks"></a>Hinweise  
 Die `ReadInMemorySymbols` -Methode versucht, `countSymbolBytes` die Daten zu lesen, `symbolsReadOffset` beginnend beim Offset innerhalb des in-Memory-Streams. Die Daten werden in `pSymbolBytes`kopiert, und es wird erwartet `countSymbolBytes` , dass genügend Speicherplatz verfügbar ist.     `pCountSymbolsBytesRead`enthält die tatsächliche Anzahl von gelesenen Bytes, die kleiner als `countSymbolBytes` sein kann, wenn das Ende des Streams erreicht ist.  
  
> [!NOTE]
> Die aktuelle Implementierung unterstützt Reflektion. ausgeben nicht. Wenn das Modul mithilfe von Reflection. ausgeben erstellt wurde, gibt die Methode `CORPROF_E_MODULE_IS_DYNAMIC`zurück.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Corprof. idl, Corprof. h  
  
 **Fern** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo7-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
