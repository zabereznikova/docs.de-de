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
ms.openlocfilehash: c3df5324e23ebeded38f3aa9843f81701f7fd333
ms.sourcegitcommit: 26f4a7697c32978f6a328c89dc4ea87034065989
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/28/2019
ms.locfileid: "66251050"
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a>ICorProfilerInfo7::ReadInMemorySymbols
[Wird nur in .NET Framework 4.6.1 und höheren Versionen unterstützt]  
  
 Liest Bytes aus einem in-Memory symbolstream.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
 [in] Der Bezeichner des Moduls mit den in-Memory-Datenstrom.  
  
 `symbolsReadOffset`  
 [in] Der Offset in den Datenstrom im Arbeitsspeicher, an dem mit dem Lesen von Bytes begonnen werden soll.  
  
 `pSymbolBytes`  
 [out] Ein Zeiger auf den Puffer, den die Daten kopiert werden. Der Puffer müssen `countSymbolBytes` des verfügbaren Speicherplatzes.  
  
 `countSymbolBytes`  
 [in] Die Anzahl der zu kopierenden Bytes an.  
  
 `pCountSymbolBytesRead`  
 [out] Wenn die Methode zurückgibt, enthält die tatsächliche Anzahl der gelesenen Bytes.  
  
## <a name="return-value"></a>Rückgabewert  
 `S_OK`, wenn eine gewisse Anzahl von Bytes gelesen wurden.  
  
 `CORPROF_E_MODULE_IS_DYNAMIC`, wenn es sich bei der Erstellung des Moduls mit <xref:System.Reflection.Emit>.  
  
## <a name="remarks"></a>Hinweise  
 Die `ReadInMemorySymbols` Methode versucht, lesen Sie `countSymbolBytes` von Daten, die beginnend am Offset `symbolsReadOffset` im in-Memory-Stream. Die Daten werden kopiert, um `pSymbolBytes`, das wird erwartet, damit `countSymbolBytes` des verfügbaren Speicherplatzes.     `pCountSymbolsBytesRead` enthält die tatsächliche Anzahl der gelesenen Bytes an, die möglicherweise kleiner als `countSymbolBytes` , wenn das Ende des Streams erreicht ist.  
  
> [!NOTE]
>  Die aktuelle Implementierung unterstützt keine Reflection.Emit. Wenn das Modul mithilfe von "Reflection.Emit" erstellt wurde, gibt die Methode `CORPROF_E_MODULE_IS_DYNAMIC`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo7-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
