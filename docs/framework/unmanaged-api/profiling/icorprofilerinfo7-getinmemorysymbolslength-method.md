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
ms.openlocfilehash: 422fdfef6bea40e0f4bcc7447df8dba1eab2896e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59146093"
---
# <a name="icorprofilerinfo7getinmemorysymbolslength-method"></a>Icorprofilerinfo7:: Getinmemorysymbolslength-Methode
[Wird nur in .NET Framework 4.6.1 und höheren Versionen unterstützt]  
  
 Gibt die Länge einer in-Memory symbolstream zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetInMemorySymbolsLength(  
        [in] ModuleID moduleId,  
        [out] DWORD* pCountSymbolBytes  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `moduleId`  
 [in] Der Bezeichner des Moduls mit den in-Memory-Datenstrom.  
  
 pCountSymbolBytes  
 [out] Ein Zeiger auf eine `DWORD` Wert, der beim Beenden der Methode, die Länge des Streams in Bytes enthält.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt die Methode zurück `S_OK` Wenn die Länge des Streams, der Arbeitsspeicher bestimmt werden kann, auch wenn es sich um 0 (null) ist.  
  
 Gibt die Methode zurück `CORPROF_E_MODULE_IS_DYNAMIC` wurde mit die Methode erstellt <xref:System.Reflection.Emit?displayProperty=nameWithType>.  
  
## <a name="remarks"></a>Hinweise  
 Wenn das Modul in-Memory-Symbole wurden, befindet sich die Länge des Streams `pCountSymbolBytes`. Wenn das Modul in-Memory-Symbole, haben keine `*pCountSymbolBytes = 0`.  
  
> [!NOTE]
>  Die aktuelle Implementierung unterstützt keine Reflection.Emit. Wenn das Modul mithilfe von "Reflection.Emit" erstellt wurde, gibt die Methode `CORPROF_E_MODULE_IS_DYNAMIC`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo7-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
