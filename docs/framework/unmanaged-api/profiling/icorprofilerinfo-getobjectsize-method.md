---
title: ICorProfilerInfo::GetObjectSize-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetObjectSize
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetObjectSize
helpviewer_keywords:
- GetObjectSize method [.NET Framework profiling]
- ICorProfilerInfo::GetObjectSize method [.NET Framework profiling]
ms.assetid: 9f02e763-73f7-42cb-a41c-f78499d9482c
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9425938042485c4330fe3fbc50cdabde6451b427
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetobjectsize-method"></a>ICorProfilerInfo::GetObjectSize-Methode
Ruft die Größe eines angegebenen Objekts ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetObjectSize(  
    [in]  ObjectID objectId,  
    [out] ULONG  *pcSize);  
```  
  
#### <a name="parameters"></a>Parameter  
 `objectId`  
 [in] Die ID des Objekts.  
  
 `pcSize`  
 [out] Ein Zeiger auf die Größe des Objekts, in Bytes.  
  
## <a name="remarks"></a>Hinweise  
  
> [!IMPORTANT]
>  Diese Methode ist veraltet. Sie gibt COR_E_OVERFLOW für Objekte größer als 4GB auf 64-Bit-Plattformen. Verwenden der [icorprofilerinfo4:: Getobjectsize2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md) Methode stattdessen.  
  
 Unterschiedliche Objekte der gleichen Typen werden häufig dieselbe Größe aufweisen. Jedoch möglicherweise einige Typen, z. B. Arrays oder Zeichenfolgen, die eine andere Größe für jedes Objekt.  
  
 Die zurückgegebene Größe der `GetObjectSize` Methode enthält keine Ausrichtungszeichenabstände, die angezeigt werden kann, nachdem das Objekt auf dem Garbage Collection-Heap ist. Bei Verwendung der `GetObjectSize` Methode von Objekt zu Objekt zu gelangen, auf dem Garbage Collection-Heap hinzuzufügen Ausrichtung padding manuell nach Bedarf.  
  
-   Klicken Sie auf 32-Bit-Windows COR_PRF_GC_GEN_0, COR_PRF_GC_GEN_1 und COR_PRF_GC_GEN_2 verwenden 4-Byte-Ausrichtung und COR_PRF_GC_LARGE_OBJECT_HEAP verwendet 8-Byte-Ausrichtung.  
  
-   Auf 64-Bit-Windows ist die Ausrichtung immer 8 Bytes.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
