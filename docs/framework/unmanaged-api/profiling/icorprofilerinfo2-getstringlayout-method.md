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
ms.openlocfilehash: 6a3d26a99844d00609b28eaef08ff0874a6701fb
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64664962"
---
# <a name="icorprofilerinfo2getstringlayout-method"></a>ICorProfilerInfo2::GetStringLayout-Methode
Ruft Informationen zum Layout eines Zeichenfolgenobjekts ab. Diese Methode ist veraltet, der [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], und wird durch die [ICorProfilerInfo3:: Getstringlayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md) Methode.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a>Parameter  
 `pBufferLengthOffset`  
 [out] Ein Zeiger auf den Offset der Position, relativ zu den `ObjectID` Zeiger, der die Länge der Zeichenfolge speichert. Die Dauer, gespeichert als eine `DWORD`.  
  
> [!NOTE]
>  Dieser Parameter gibt die Länge der Zeichenfolge selbst, nicht die Länge des Puffers zurück. Die Länge des Puffers ist nicht mehr verfügbar.  
  
 `PStringLengthOffset`  
 [out] Ein Zeiger auf den Offset der Position, relativ zu den `ObjectID` Zeiger, der die Länge der Zeichenfolge selbst speichert. Die Dauer, gespeichert als eine `DWORD`.  
  
 `pBufferOffset`  
 [out] Ein Zeiger auf den Offset des Puffers, relativ zu den `ObjectID` Zeiger, der die Zeichenfolge mit Breitzeichen speichert.  
  
## <a name="remarks"></a>Hinweise  
 Die `GetStringLayout` Methode ruft die Offsets, relativ zu den `ObjectID` -Zeiger ist, der Standorte in der folgenden gespeichert werden:  
  
- Die Länge des Puffers der Zeichenfolge.  
  
- Die Länge der Zeichenfolge selbst.  
  
- Der Puffer, der die tatsächliche Zeichenfolge mit breiten Zeichen enthält.  
  
 Zeichenfolgen können Null-terminiert sein.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
