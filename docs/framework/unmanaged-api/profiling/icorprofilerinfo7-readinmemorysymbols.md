---
title: 'Icorprofilerinfo7:: Readinmemorysymbols'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name:
- ICorProfilerInfo7.ReadInMemorySymbols
api_location:
- CorProf.idl
- CorProf.h
- CorGuids.lib
api_type:
- COM
ms.assetid: 1745a0b9-8332-4777-a670-b549bff3b901
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5851f73cc899ef21d8a5dcfd8f03617641a6625a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a>Icorprofilerinfo7:: Readinmemorysymbols
[Unterstützt in [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] und höheren Versionen]  
  
 Liest Bytes aus einem Datenstrom in-Memory-Symbol.  
  
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
  
#### <a name="parameters"></a>Parameter  
 `moduleId`  
 [in] Der Bezeichner des Moduls, das in-Memory-Datenstrom enthält.  
  
 `symbolsReadOffset`  
 [in] Der Offset im in-Memory-Stream an dem mit dem Lesen von Bytes begonnen werden soll.  
  
 `pSymbolBytes`  
 [out] Ein Zeiger auf den Puffer, den die Daten kopiert werden. Der Puffer müssen `countSymbolBytes` des verfügbaren Speicherplatzes.  
  
 `countSymbolBytes`  
 [in] Die Anzahl der zu kopierenden Bytes.  
  
 `pCountSymbolBytesRead`  
 [out] Wenn die Methode zurückkehrt, enthält die tatsächliche Anzahl der gelesenen Bytes.  
  
## <a name="return-value"></a>Rückgabewert  
 `S_OK`, wenn eine nicht-NULL-Anzahl von Bytes gelesen wurden.  
  
 `CORPROF_E_MODULE_IS_DYNAMIC`, wenn es sich bei der Erstellung des Moduls mit <xref:System.Reflection.Emit>.  
  
## <a name="remarks"></a>Hinweise  
 Die `ReadInMemorySymbols` Methode versucht, lesen Sie `countSymbolBytes` Daten ab dem Offset `symbolsReadOffset` im in-Memory-Stream. Die Daten in kopiert `pSymbolBytes`, was erwartet haben `countSymbolBytes` des verfügbaren Speicherplatzes.     `pCountSymbolsBytesRead`enthält die tatsächliche Anzahl von Bytes zu lesen, was u. u. nicht kleiner als `countSymbolBytes` , wenn das Ende des Streams erreicht ist.  
  
> [!NOTE]
>  Die aktuelle Implementierung unterstützt keine "Reflection.Emit". Wenn das Modul mithilfe von "Reflection.Emit" erstellt wurde, gibt die Methode `CORPROF_E_MODULE_IS_DYNAMIC`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerInfo7-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
