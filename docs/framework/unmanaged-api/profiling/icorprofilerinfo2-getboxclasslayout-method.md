---
title: ICorProfilerInfo2::GetBoxClassLayout-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetBoxClassLayout
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetBoxClassLayout
helpviewer_keywords:
- GetBoxClassLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetBoxClassLayout method [.NET Framework profiling]
ms.assetid: 624672b5-1189-488a-85d2-3e12b49617c1
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c11013781a4fc8f627dac97894ff9ef02bfda51c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getboxclasslayout-method"></a>ICorProfilerInfo2::GetBoxClassLayout-Methode
Ruft Informationen darüber, in denen der angegebene Werttyp befindet, wenn er mittels Boxing konvertiert wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetBoxClassLayout(  
    [in] ClassID classId,  
    [out] ULONG32 *pBufferOffset);  
```  
  
#### <a name="parameters"></a>Parameter  
 `classId`  
 [in] Die ID der Klasse, die den Werttyp beschreibt, der mittels Boxing konvertiert wird.  
  
 `pBufferOffset`  
 [out] Eine ganze Zahl, die der Offset relativ zu den geschachteltes Objekt-ID-Zeiger des Werttyps ist.  
  
## <a name="remarks"></a>Hinweise  
 Die `pBufferOffset` Wert ist der Speicherort des Werttyps innerhalb eines Felds. Nach dem `pBufferOffset` wird angewendet, in ein geschachteltes Objekt den Werttyp Klassenlayout verwendet werden kann, um den Wert des Objekts zu interpretieren.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
