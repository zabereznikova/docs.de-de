---
title: ICorProfilerInfo3::GetStringLayout2-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetStringLayout2 Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetStringLayout2
helpviewer_keywords:
- ICorProfilerInfo3::GetStringLayout2 method [.NET Framework profiling]
- GetStringLayout2 method [.NET Framework profiling]
ms.assetid: 1a268496-ee51-4d84-8700-ee56fd0c499d
topic_type:
- apiref
ms.openlocfilehash: dc4df7e7cb93f137013d0a0e4d805c7563d4fe1a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697895"
---
# <a name="icorprofilerinfo3getstringlayout2-method"></a>ICorProfilerInfo3::GetStringLayout2-Methode

Ruft Informationen zum Layout eines Zeichenfolgenobjekts ab. Diese Methode ersetzt die [ICorProfilerInfo2:: GetStringLayout](icorprofilerinfo2-getstringlayout-method.md) -Methode.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetStringLayout2(  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a>Parameter  

 `pStringLengthOffset`  
 vorgenommen Ein Zeiger auf den Offset der Position relativ zum `ObjectID` Zeiger, der die Länge der Zeichenfolge selbst speichert. Die Länge wird als gespeichert `DWORD` .  
  
 `pBufferOffset`  
 vorgenommen Ein Zeiger auf den Offset des Puffers relativ zum `ObjectID` Zeiger, der die Zeichenfolge von breit Zeichen speichert.  
  
## <a name="remarks"></a>Hinweise  

 Zeichen folgen können NULL-terminierte Zeichen folgen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorProfilerInfo3-Schnittstelle](icorprofilerinfo3-interface.md)
- [Profilerstellungsschnittstellen](profiling-interfaces.md)
