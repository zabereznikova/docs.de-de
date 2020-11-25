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
ms.openlocfilehash: 960f8f1fe2315e068d599aa5a31e03f521b235a8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733866"
---
# <a name="icorprofilerinfo4getobjectsize2-method"></a>ICorProfilerInfo4::GetObjectSize2-Methode

Gibt die Größe eines angegebenen-Objekts zurück. Ersetzt die [ICorProfilerInfo:: GetObjectSize](icorprofilerinfo-getobjectsize-method.md) -Methode durch berichtsgrößen von Objekten, die größer sind als die, die in einem-Objekt angegeben werden können `ULONG` .  
  
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
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorProfilerInfo4-Schnittstelle](icorprofilerinfo4-interface.md)
