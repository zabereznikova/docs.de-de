---
title: ICorProfilerInfo::GetObjectSize-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetObjectSize
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetObjectSize
helpviewer_keywords:
- GetObjectSize method [.NET Framework profiling]
- ICorProfilerInfo::GetObjectSize method [.NET Framework profiling]
ms.assetid: 9f02e763-73f7-42cb-a41c-f78499d9482c
topic_type:
- apiref
ms.openlocfilehash: de6d46897f3d3266bf708528efd712ca7db8ea4a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438830"
---
# <a name="icorprofilerinfogetobjectsize-method"></a>ICorProfilerInfo::GetObjectSize-Methode
Ruft die Größe eines angegebenen-Objekts ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetObjectSize(  
    [in]  ObjectID objectId,  
    [out] ULONG  *pcSize);  
```  
  
## <a name="parameters"></a>Parameter  
 `objectId`  
 in Die ID des Objekts.  
  
 `pcSize`  
 vorgenommen Ein Zeiger auf die Größe des-Objekts in Bytes.  
  
## <a name="remarks"></a>Hinweise  
  
> [!IMPORTANT]
> Diese Methode ist veraltet. Er gibt COR_E_OVERFLOW für Objekte zurück, die größer als 4 GB auf 64-Bit-Plattformen sind. Verwenden Sie stattdessen die [ICorProfilerInfo4:: GetObjectSize2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md) -Methode.  
  
 Unterschiedliche Objekte der gleichen Typen haben oft dieselbe Größe. Einige Typen, z. b. Arrays oder Zeichen folgen, können jedoch für jedes Objekt eine andere Größe aufweisen.  
  
 Die von der `GetObjectSize`-Methode zurückgegebene Größe schließt keine Ausrichtungs Auffüll Zeichen ein, die möglicherweise angezeigt werden, nachdem sich das Objekt im Garbage Collection Heap befindet. Wenn Sie die `GetObjectSize`-Methode verwenden, um vom Objekt auf das Objekt im Garbage Collection Heap zu verschieben, fügen Sie ggf. manuell die Ausrichtung der Ausrichtungs Abstände hinzu.  
  
- Bei 32-Bit-Fenstern verwenden COR_PRF_GC_GEN_0, COR_PRF_GC_GEN_1 und COR_PRF_GC_GEN_2 4-Byte-Ausrichtung, und COR_PRF_GC_LARGE_OBJECT_HEAP verwendet 8-Byte-Ausrichtung.  
  
- Bei 64-Bit-Fenstern ist die Ausrichtung immer 8 Bytes.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
