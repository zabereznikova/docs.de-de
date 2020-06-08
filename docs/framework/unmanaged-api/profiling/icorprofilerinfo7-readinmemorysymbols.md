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
ms.openlocfilehash: 6732457220d795bbf8ae54277ef9f5c07cf96359
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495358"
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
 vorgenommen Ein Zeiger auf den Puffer, in den die Daten kopiert werden. Für den Puffer muss `countSymbolBytes` Speicherplatz verfügbar sein.  
  
 `countSymbolBytes`  
 in Die Anzahl der zu kopierenden Bytes.  
  
 `pCountSymbolBytesRead`  
 vorgenommen Diese Methode gibt die tatsächliche Anzahl von gelesenen Bytes zurück.  
  
## <a name="return-value"></a>Rückgabewert  
 `S_OK`, wenn eine Anzahl von Bytes ungleich 0 (null) gelesen wurde.  
  
 `CORPROF_E_MODULE_IS_DYNAMIC`, wenn das Modul mithilfe von erstellt wurde <xref:System.Reflection.Emit> .  
  
## <a name="remarks"></a>Bemerkungen  
 Die- `ReadInMemorySymbols` Methode versucht, die Daten zu lesen, `countSymbolBytes` beginnend beim Offset `symbolsReadOffset` innerhalb des in-Memory-Streams. Die Daten werden in kopiert `pSymbolBytes` , und es wird erwartet, dass genügend `countSymbolBytes` Speicherplatz verfügbar ist.     `pCountSymbolsBytesRead`enthält die tatsächliche Anzahl von gelesenen Bytes, die kleiner als sein kann, `countSymbolBytes` Wenn das Ende des Streams erreicht ist.  
  
> [!NOTE]
> Die aktuelle Implementierung unterstützt Reflektion. ausgeben nicht. Wenn das Modul mithilfe von Reflection. ausgeben erstellt wurde, gibt die Methode zurück `CORPROF_E_MODULE_IS_DYNAMIC` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICorProfilerInfo7-Schnittstelle](icorprofilerinfo7-interface.md)
