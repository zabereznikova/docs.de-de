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
ms.openlocfilehash: 46ffa5cb4fac6988240d32cb1939cc25bdf0a412
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686071"
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
  
 pzähl-symbolbytes  
 vorgenommen Ein Zeiger auf einen `DWORD` Wert, der bei Rückgabe der Methode die Länge des Streams in Bytes enthält.  
  
## <a name="return-value"></a>Rückgabewert  

 Die-Methode gibt zurück `S_OK` , wenn die Länge des Speicherdaten Stroms bestimmt werden kann, auch wenn Sie 0 (null) ist.  
  
 Die Methode gibt zurück, `CORPROF_E_MODULE_IS_DYNAMIC` Wenn die Methode mithilfe von erstellt wurde <xref:System.Reflection.Emit?displayProperty=nameWithType> .  
  
## <a name="remarks"></a>Hinweise  

 Wenn das Modul über in-Memory-Symbole verfügt, wird die Länge des Streams in eingefügt `pCountSymbolBytes` . , Wenn das Modul nicht über Speicher interne Symbole verfügt `*pCountSymbolBytes = 0` .  
  
> [!NOTE]
> Die aktuelle Implementierung unterstützt Reflektion. ausgeben nicht. Wenn das Modul mithilfe von Reflection. ausgeben erstellt wurde, gibt die Methode zurück `CORPROF_E_MODULE_IS_DYNAMIC` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorProfilerInfo7-Schnittstelle](icorprofilerinfo7-interface.md)
