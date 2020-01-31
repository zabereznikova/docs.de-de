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
ms.openlocfilehash: 839cd574e5352b74b47cd6242d5706bc6405d439
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862918"
---
# <a name="icorprofilerinfo2getarrayobjectinfo-method"></a>ICorProfilerInfo2::GetArrayObjectInfo-Methode
Ruft ausführliche Informationen zu einem Array Objekt ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetArrayObjectInfo(  
    [in] ObjectID objectId,  
    [in] ULONG32 cDimensions,  
    [out, size_is(cDimensions), length_is(cDimensions)] ULONG32 pDimensionSizes[],  
    [out, size_is(cDimensions), length_is(cDimensions)] int pDimensionLowerBounds[],  
    [out] BYTE **ppData);  
```  
  
## <a name="parameters"></a>Parameters  
 `objectId`  
 in Die ID eines gültigen Array Objekts.  
  
 `cDimensions`  
 in Der Rang (Anzahl der Dimensionen) des Arrays.  
  
 `pDimensionSizes`  
 vorgenommen Ein Array, das ganze Zahlen enthält, die jeweils die Größe einer Dimension des Arrays darstellen.  
  
 `pDimensionLowerBounds`  
 vorgenommen Ein Array, das ganze Zahlen enthält, die jeweils die untere Grenze einer Dimension des Arrays darstellen.  
  
 `ppData`  
 vorgenommen Ein Zeiger auf die Adresse des Rohdaten Puffers für das Array, das entsprechend der C++ Konvention angeordnet ist.  
  
## <a name="remarks"></a>Hinweise  
 Die `pDimensionSizes` und `pDimensionLowerBounds` sind parallele Arrays, sodass die Elemente, die sich am selben Index in jedem Array befinden, Merkmale derselben Entität sind.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2-Schnittstelle](icorprofilerinfo2-interface.md)
