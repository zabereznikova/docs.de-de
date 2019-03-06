---
title: ICorProfilerInfo2::GetArrayObjectInfo-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetArrayObjectInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetArrayObjectInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetArrayObjectInfo method [.NET Framework profiling]
- GetArrayObjectInfo method [.NET Framework profiling]
ms.assetid: bda75017-739f-4ce5-9000-f3b526e8473c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7fe86fbe7ee51e5f53eeea74d7d5a56046de5e00
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484393"
---
# <a name="icorprofilerinfo2getarrayobjectinfo-method"></a>ICorProfilerInfo2::GetArrayObjectInfo-Methode
Ruft detaillierte Informationen zu einem Arrayobjekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetArrayObjectInfo(  
    [in] ObjectID objectId,  
    [in] ULONG32 cDimensions,  
    [out, size_is(cDimensions), length_is(cDimensions)] ULONG32 pDimensionSizes[],  
    [out, size_is(cDimensions), length_is(cDimensions)] int pDimensionLowerBounds[],  
    [out] BYTE **ppData);  
```  
  
## <a name="parameters"></a>Parameter  
 `objectId`  
 [in] Die ID der ein gültiges Array-Objekt.  
  
 `cDimensions`  
 [in] Der Rang (Anzahl der Dimensionen) des Arrays.  
  
 `pDimensionSizes`  
 [out] Ein Array mit ganzen Zahlen, jede die Größe einer Dimension des Arrays darstellt.  
  
 `pDimensionLowerBounds`  
 [out] Ein Array mit ganzen Zahlen, die jeweils die untere darstellen einer Dimension des Arrays gebunden werden.  
  
 `ppData`  
 [out] Ein Zeiger auf die Adresse des den unformatierten Puffer für das Array, das gemäß der Konvention C++ angeordnet ist.  
  
## <a name="remarks"></a>Hinweise  
 Die `pDimensionSizes` und `pDimensionLowerBounds` sind parallele Arrays, also die Elemente im gleichen Index in jedem Array Merkmale der gleichen Entität.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
