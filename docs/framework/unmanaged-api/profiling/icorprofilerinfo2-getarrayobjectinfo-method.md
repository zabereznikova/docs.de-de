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
ms.openlocfilehash: e6e6f4f6bdfba8deecb3661d88a881759da043ae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33456306"
---
# <a name="icorprofilerinfo2getarrayobjectinfo-method"></a>ICorProfilerInfo2::GetArrayObjectInfo-Methode
Ruft ausführliche Informationen zu einem Arrayobjekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetArrayObjectInfo(  
    [in] ObjectID objectId,  
    [in] ULONG32 cDimensions,  
    [out, size_is(cDimensions), length_is(cDimensions)] ULONG32 pDimensionSizes[],  
    [out, size_is(cDimensions), length_is(cDimensions)] int pDimensionLowerBounds[],  
    [out] BYTE **ppData);  
```  
  
#### <a name="parameters"></a>Parameter  
 `objectId`  
 [in] Die ID der ein gültiges Array-Objekt.  
  
 `cDimensions`  
 [in] Der Rang (Anzahl der Dimensionen) des Arrays.  
  
 `pDimensionSizes`  
 [out] Ein Array mit ganzen Zahlen, jede die Größe einer Dimension des Arrays darstellt.  
  
 `pDimensionLowerBounds`  
 [out] Ein Array, das ganze Zahlen enthält, die jeweils der niedrigere darstellen einer Dimension des Arrays gebunden werden.  
  
 `ppData`  
 [out] Ein Zeiger auf die Adresse des den unformatierten Puffer für das Array, das gemäß der C++-Konvention angeordnet ist.  
  
## <a name="remarks"></a>Hinweise  
 Die `pDimensionSizes` und `pDimensionLowerBounds` sind die Elemente, die im gleichen Index in jedem Array Merkmale derselben Entität sind parallele Arrays.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
