---
title: ICorProfilerInfo4::GetObjectSize2-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetObjectSize2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetObjectSize2
helpviewer_keywords:
- GetObjectSize2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetObjectSize2 method [.NET Framework profiling]
ms.assetid: 4a3e43ed-3ee3-4395-ab14-f78b903be13e
topic_type:
- apiref
ms.openlocfilehash: fdfba34f35e40b2a50dbc4edc5b6b6c45f17194f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442867"
---
# <a name="icorprofilerinfo4getobjectsize2-method"></a>ICorProfilerInfo4::GetObjectSize2-Methode
Gibt die Größe eines angegebenen-Objekts zurück. Ersetzt die [ICorProfilerInfo:: GetObjectSize](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getobjectsize-method.md) -Methode durch berichtsgrößen von Objekten, die größer sind als in einer `ULONG`ausgedrückt werden können.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetObjectSize2(  
    [in]  ObjectID objectId,  
    [out] SIZE_T *pcSize);  
```  
  
## <a name="parameters"></a>Parameter  
 `objectId`  
 in Die ID des Objekts.  
  
 `pcSize`  
 vorgenommen Ein Zeiger auf die Größe des-Objekts in Bytes.  
  
## <a name="remarks"></a>Hinweise  
 Unterschiedliche Objekte der gleichen Typen haben oft dieselbe Größe. Einige Typen, z. b. Arrays oder Zeichen folgen, können jedoch für jedes Objekt eine andere Größe aufweisen.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo4-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
