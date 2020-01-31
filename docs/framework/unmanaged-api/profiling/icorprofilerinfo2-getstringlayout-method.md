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
ms.openlocfilehash: 537840ac03b4136682b78cb964950ab5670a7d7e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868615"
---
# <a name="icorprofilerinfo2getstringlayout-method"></a>ICorProfilerInfo2::GetStringLayout-Methode
Ruft Informationen zum Layout eines Zeichenfolgenobjekts ab. Diese Methode ist in der .NET Framework 4 veraltet und wird durch die [ICorProfilerInfo3:: GetStringLayout2](icorprofilerinfo3-getstringlayout2-method.md) -Methode abgelöst.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a>Parameters  
 `pBufferLengthOffset`  
 vorgenommen Ein Zeiger auf den Offset der Position relativ zum `ObjectID` Zeiger, der die Länge der Zeichenfolge speichert. Die Länge wird als `DWORD`gespeichert.  
  
> [!NOTE]
> Dieser Parameter gibt die Länge der Zeichenfolge selbst zurück, nicht die Länge des Puffers. Die Länge des Puffers ist nicht mehr verfügbar.  
  
 `PStringLengthOffset`  
 vorgenommen Ein Zeiger auf den Offset der Position relativ zum `ObjectID` Zeiger, der die Länge der Zeichenfolge speichert. Die Länge wird als `DWORD`gespeichert.  
  
 `pBufferOffset`  
 vorgenommen Ein Zeiger auf den Offset des Puffers relativ zum `ObjectID` Zeiger, der die Zeichenfolge von breit Zeichen speichert.  
  
## <a name="remarks"></a>Hinweise  
 Die `GetStringLayout`-Methode ruft die Offsets (relativ zum `ObjectID` Zeiger) der Speicherorte ab, an denen Folgendes gespeichert wird:  
  
- Die Länge des Puffers der Zeichenfolge.  
  
- Die Länge der Zeichenfolge selbst.  
  
- Der Puffer, der die tatsächliche Zeichenfolge von breit Zeichen enthält.  
  
 Zeichen folgen können auf Null enden.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2-Schnittstelle](icorprofilerinfo2-interface.md)
