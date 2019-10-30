---
title: 'ICorProfilerInfo7:: Read inmemorysymbols'
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
ms.openlocfilehash: ae51490be96f3eb6524831c93739c3befbc30b37
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132025"
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a>ICorProfilerInfo7:: Read inmemorysymbols
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
 vorgenommen Ein Zeiger auf den Puffer, in den die Daten kopiert werden. Der Puffer sollte `countSymbolBytes` verfügbaren Speicherplatz aufweisen.  
  
 `countSymbolBytes`  
 in Die Anzahl der zu kopierenden Bytes.  
  
 `pCountSymbolBytesRead`  
 vorgenommen Diese Methode gibt die tatsächliche Anzahl von gelesenen Bytes zurück.  
  
## <a name="return-value"></a>Rückgabewert  
 `S_OK`, wenn eine Anzahl von Bytes ungleich 0 (null) gelesen wurde.  
  
 `CORPROF_E_MODULE_IS_DYNAMIC`, wenn das Modul mit <xref:System.Reflection.Emit>erstellt wurde.  
  
## <a name="remarks"></a>Hinweise  
 Die `ReadInMemorySymbols`-Methode versucht, `countSymbolBytes` von Daten zu lesen, beginnend bei Offset `symbolsReadOffset` innerhalb des in-Memory-Streams. Die Daten werden in `pSymbolBytes`kopiert, wobei erwartet wird, dass `countSymbolBytes` Speicherplatz verfügbar ist.     `pCountSymbolsBytesRead` enthält die tatsächliche Anzahl von gelesenen Bytes, die kleiner als `countSymbolBytes` sein kann, wenn das Ende des Streams erreicht ist.  
  
> [!NOTE]
> Die aktuelle Implementierung unterstützt Reflektion. ausgeben nicht. Wenn das Modul mithilfe von Reflection. ausgeben erstellt wurde, gibt die Methode `CORPROF_E_MODULE_IS_DYNAMIC`zurück.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo7-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
