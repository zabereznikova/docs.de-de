---
title: ICorProfilerInfo2::GetStringLayout-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetStringLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetStringLayout
helpviewer_keywords:
- GetStringLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetStringLayout method [.NET Framework profiling]
ms.assetid: 43189651-a535-4803-a1d1-f1c427ace2ca
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8d1bd732a82028afe809f4c2141e1d61668eae1c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454917"
---
# <a name="icorprofilerinfo2getstringlayout-method"></a>ICorProfilerInfo2::GetStringLayout-Methode
Ruft Informationen zum Layout eines Zeichenfolgenobjekts ab. Diese Methode ist veraltet, in der [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], und wird durch die [ICorProfilerInfo3:: Getstringlayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md) Methode.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pBufferLengthOffset`  
 [out] Ein Zeiger auf den Offset des Speicherorts, relativ zu den `ObjectID` Zeiger, der die Länge der Zeichenfolge speichert. Die Länge wird gespeichert, als eine `DWORD`.  
  
> [!NOTE]
>  Dieser Parameter gibt die Länge der Zeichenfolge selbst und nicht die Länge des Puffers zurück. Die Länge des Puffers ist nicht mehr verfügbar.  
  
 `PStringLengthOffset`  
 [out] Ein Zeiger auf den Offset des Speicherorts, relativ zu den `ObjectID` Zeiger, der die Länge der Zeichenfolge selbst speichert. Die Länge wird gespeichert, als eine `DWORD`.  
  
 `pBufferOffset`  
 [out] Ein Zeiger auf den Offset des Puffers, relativ zu den `ObjectID` Zeiger, der die Zeichenfolge mit Breitzeichen speichert.  
  
## <a name="remarks"></a>Hinweise  
 Die `GetStringLayout` Methode ruft die Offsets relativ zu den `ObjectID` Zeiger, der die Speicherorte, in denen die folgenden gespeichert werden:  
  
-   Die Länge des Puffers der Zeichenfolge.  
  
-   Die Länge der Zeichenfolge selbst.  
  
-   Der Puffer, der die tatsächliche Breitzeichen-Zeichenfolge enthält.  
  
 Zeichenfolgen können Null-terminiert sein.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
