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
ms.openlocfilehash: a675cc301d2dd32f87e3864a3123e2044761ef91
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868355"
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
  
## <a name="parameters"></a>Parameters  
 `moduleId`  
 in Der Bezeichner des Moduls, das den in-Memory-Datenstrom enthält.  
  
 pCountSymbolBytes  
 vorgenommen Ein Zeiger auf einen `DWORD` Wert, der bei Rückgabe der Methode die Länge des Streams in Bytes enthält.  
  
## <a name="return-value"></a>Rückgabewert  
 Die Methode gibt `S_OK` zurück, wenn die Länge des Arbeitsspeicherstreams bestimmt werden kann, auch wenn Sie 0 (null) ist.  
  
 Die Methode gibt `CORPROF_E_MODULE_IS_DYNAMIC` zurück, wenn die Methode mit <xref:System.Reflection.Emit?displayProperty=nameWithType>erstellt wurde.  
  
## <a name="remarks"></a>Hinweise  
 Wenn das Modul über in-Memory-Symbole verfügt, wird die Länge des Streams in `pCountSymbolBytes`platziert. Wenn das Modul keine in-Memory-Symbole enthält, `*pCountSymbolBytes = 0`.  
  
> [!NOTE]
> Die aktuelle Implementierung unterstützt Reflektion. ausgeben nicht. Wenn das Modul mithilfe von Reflection. ausgeben erstellt wurde, gibt die Methode `CORPROF_E_MODULE_IS_DYNAMIC`zurück.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo7-Schnittstelle](icorprofilerinfo7-interface.md)
