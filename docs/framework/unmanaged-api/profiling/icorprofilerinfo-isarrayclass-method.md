---
title: ICorProfilerInfo::IsArrayClass-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.IsArrayClass
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::IsArrayClass
helpviewer_keywords:
- IsArrayClass method [.NET Framework profiling]
- ICorProfilerInfo::IsArrayClass method [.NET Framework profiling]
ms.assetid: 7f230961-23a6-4d56-ad2d-7a876d65705f
topic_type:
- apiref
ms.openlocfilehash: 57515ac4670b9b7e25bb496851347a62e1b246df
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438724"
---
# <a name="icorprofilerinfoisarrayclass-method"></a>ICorProfilerInfo::IsArrayClass-Methode
Bestimmt, ob die angegebene Klasse eine Array Klasse ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT IsArrayClass(  
    [in]  ClassID        classId,  
    [out] CorElementType *pBaseElemType,  
    [out] ClassID        *pBaseClassId,  
    [out] ULONG          *pcRank);  
```  
  
## <a name="parameters"></a>Parameter  
 `classId`  
 in Die ID der zu überprüfenden Klasse.  
  
 `pBaseElemType`  
 vorgenommen Ein Zeiger auf einen Wert der CorElementType-Enumeration, der den Typ der Array Elemente angibt.  
  
 `pBaseClassId`  
 vorgenommen Ein Zeiger auf die Klassen-ID der Array Elemente (falls verfügbar).  
  
 `pcRank`  
 vorgenommen Ein Zeiger auf eine ganze Zahl, die den Rang (d. h. die Anzahl der Dimensionen) des Arrays angibt.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die angegebene Klasse eine Array Klasse ist, gibt die `IsArrayClass` Methode eine S_OK HRESULT und Werte für alle Ausgabeparameter ungleich NULL zurück. Andernfalls wird S_FALSE zurückgegeben.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
