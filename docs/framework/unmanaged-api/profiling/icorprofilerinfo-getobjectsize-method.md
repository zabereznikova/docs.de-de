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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d366a0093ca82d2e5b3c40729777a1b6c0766bda
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59092200"
---
# <a name="icorprofilerinfogetobjectsize-method"></a>ICorProfilerInfo::GetObjectSize-Methode
Ruft die Größe eines angegebenen Objekts ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetObjectSize(  
    [in]  ObjectID objectId,  
    [out] ULONG  *pcSize);  
```  
  
## <a name="parameters"></a>Parameter  
 `objectId`  
 [in] Die ID des Objekts.  
  
 `pcSize`  
 [out] Ein Zeiger auf die Größe des Objekts, in Bytes.  
  
## <a name="remarks"></a>Hinweise  
  
> [!IMPORTANT]
>  Diese Methode ist veraltet. Sie gibt COR_E_OVERFLOW für Objekte größer als 4GB auf 64-Bit-Plattformen. Verwenden der [icorprofilerinfo4:: Getobjectsize2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md) Methode stattdessen.  
  
 Verschiedene Objekte der gleichen Typen verfügen häufig über die gleiche Größe. Allerdings möglicherweise einiger Typen wie Arrays bzw. Zeichenfolgen, die eine andere Größe für jedes Objekt.  
  
 Die Größe, die zurückgegeben werden, indem die `GetObjectSize` Methode umfasst keine Ausrichtungszeichenabstände, die angezeigt werden kann, nachdem das Objekt in die Garbage Collection-Heap befindet. Bei Verwendung der `GetObjectSize` Methode aus einem Objekt zu einem anderen Objekt auf dem Garbage Collection-Heap, fahren Sie fort, hinzuzufügen, Ausrichtung, die nach Bedarf manuell auffüllen.  
  
-   Klicken Sie auf 32-Bit-Windows COR_PRF_GC_GEN_0 COR_PRF_GC_GEN_1 und COR_PRF_GC_GEN_2 verwenden 4-Byte-Ausrichtung und COR_PRF_GC_LARGE_OBJECT_HEAP verwendet 8-Byte-Ausrichtung.  
  
-   Auf 64-Bit-Windows ist die Ausrichtung immer 8 Bytes.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
