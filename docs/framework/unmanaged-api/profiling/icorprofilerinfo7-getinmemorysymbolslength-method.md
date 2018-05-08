---
title: 'Icorprofilerinfo7:: Getinmemorysymbolslength-Methode'
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo7.GetInMemorySymbolsLength
api_location:
- mscorwks.dll
- icorprof.idl
api_type:
- COM
ms.assetid: d62c4a4c-8a62-45aa-8f01-a8387cf36159
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5e662270fc8db3fb85e058e8d4f3346f58f79bb8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilerinfo7getinmemorysymbolslength-method"></a>Icorprofilerinfo7:: Getinmemorysymbolslength-Methode
[Wird nur in .NET Framework 4.6.1 und höheren Versionen unterstützt]  
  
 Gibt die Länge eines Datenstroms in-Memory-Symbols zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetInMemorySymbolsLength(  
        [in] ModuleID moduleId,  
        [out] DWORD* pCountSymbolBytes  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `moduleId`  
 [in] Der Bezeichner des Moduls, das in-Memory-Datenstrom enthält.  
  
 pCountSymbolBytes  
 [out] Ein Zeiger auf eine `DWORD` Wert, der, wenn der Rückgabewert dieser Methode die Länge des Streams in Bytes enthält.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt die Methode `S_OK` , wenn die Länge des Streams Arbeitsspeicher bestimmt werden kann, auch wenn es auf 0 (null) ist.  
  
 Gibt die Methode `CORPROF_E_MODULE_IS_DYNAMIC` , wenn die Methode erstellt wurde mit <xref:System.Reflection.Emit?displayProperty=nameWithType>.  
  
## <a name="remarks"></a>Hinweise  
 Wenn in-Memory-Symbole für das Modul ist, wird die Länge des Streams platziert `pCountSymbolBytes`. Wenn das Modul in-Memory-Symbole, keine `*pCountSymbolBytes = 0`.  
  
> [!NOTE]
>  Die aktuelle Implementierung unterstützt keine "Reflection.Emit". Wenn das Modul mithilfe von "Reflection.Emit" erstellt wurde, gibt die Methode `CORPROF_E_MODULE_IS_DYNAMIC`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerInfo7-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
