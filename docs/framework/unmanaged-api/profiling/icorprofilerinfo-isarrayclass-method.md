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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5e00e7f39bc2f8c14db0676102a52089c7710bd6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772253"
---
# <a name="icorprofilerinfoisarrayclass-method"></a>ICorProfilerInfo::IsArrayClass-Methode
Bestimmt, ob die angegebene Klasse ein Array-Klasse ist.  
  
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
 [in] Die ID der Klasse, die untersucht werden.  
  
 `pBaseElemType`  
 [out] Ein Zeiger auf einen Wert der CorElementType-Enumeration, die den Typ der Elemente des Arrays angibt.  
  
 `pBaseClassId`  
 [out] Ein Zeiger auf die Klassen-ID der Arrayelemente, sofern verfügbar.  
  
 `pcRank`  
 [out] Ein Zeiger auf eine ganze Zahl, die den Rang (d. h. die Anzahl der Dimensionen) des Arrays angibt.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die angegebene Klasse ein Array-Klasse, ist die `IsArrayClass` Methodenrückgabe ein S_OK HRESULT und die Werte für alle nicht-Null Ausgabeparameter. Wird zurückgegeben, andernfalls S_FALSE.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
