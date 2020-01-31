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
ms.openlocfilehash: 53c01d2db44f4d0adf1ba5b9cc225ab49581aa5d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868342"
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
  
## <a name="parameters"></a>Parameters  
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
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo7-Schnittstelle](icorprofilerinfo7-interface.md)
