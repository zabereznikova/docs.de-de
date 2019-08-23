---
title: 'ICorProfilerInfo7:: getinmemorysymbolslength-Methode'
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
ms.openlocfilehash: 157b0e215f8afa58cccb3d54a65baa9c307ba966
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955427"
---
# <a name="icorprofilerinfo7getinmemorysymbolslength-method"></a>ICorProfilerInfo7:: getinmemorysymbolslength-Methode
[Wird nur in .NET Framework 4.6.1 und höheren Versionen unterstützt]  
  
 Gibt die Länge eines in-Memory-Symbol Datenstroms zurück.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetInMemorySymbolsLength(  
        [in] ModuleID moduleId,  
        [out] DWORD* pCountSymbolBytes  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `moduleId`  
 in Der Bezeichner des Moduls, das den in-Memory-Datenstrom enthält.  
  
 pCountSymbolBytes  
 vorgenommen Ein Zeiger auf einen `DWORD` Wert, der bei Rückgabe der Methode die Länge des Streams in Bytes enthält.  
  
## <a name="return-value"></a>Rückgabewert  
 Die-Methode `S_OK` gibt zurück, wenn die Länge des Speicherdaten Stroms bestimmt werden kann, auch wenn Sie 0 (null) ist.  
  
 Die Methode gibt `CORPROF_E_MODULE_IS_DYNAMIC` zurück, wenn die Methode mithilfe <xref:System.Reflection.Emit?displayProperty=nameWithType>von erstellt wurde.  
  
## <a name="remarks"></a>Hinweise  
 Wenn das Modul über in-Memory-Symbole verfügt, wird die Länge des Streams in `pCountSymbolBytes`eingefügt. , `*pCountSymbolBytes = 0`Wenn das Modul nicht über Speicher interne Symbole verfügt.  
  
> [!NOTE]
> Die aktuelle Implementierung unterstützt Reflektion. ausgeben nicht. Wenn das Modul mithilfe von Reflection. ausgeben erstellt wurde, gibt die Methode `CORPROF_E_MODULE_IS_DYNAMIC`zurück.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Corprof. idl, Corprof. h  
  
 **Fern** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo7-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
