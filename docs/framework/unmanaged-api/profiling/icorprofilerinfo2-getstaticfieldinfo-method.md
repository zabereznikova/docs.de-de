---
title: ICorProfilerInfo2::GetStaticFieldInfo-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetStaticFieldInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetStaticFieldInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetStaticFieldInfo method [.NET Framework profiling]
- GetStaticFieldInfo method [.NET Framework profiling]
ms.assetid: fc663e76-e23f-49a8-bdd5-52cdf1a3b2b3
topic_type:
- apiref
ms.openlocfilehash: ff84bdfb8bbd5331fb94eed766f09137adf9e62c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703837"
---
# <a name="icorprofilerinfo2getstaticfieldinfo-method"></a>ICorProfilerInfo2::GetStaticFieldInfo-Methode

Ruft einen Wert ab, der die Art der statischen angibt, die für das angegebene Feld gilt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetStaticFieldInfo (  
    [in] ClassID               classId,  
    [in] mdFieldDef            fieldToken,  
    [out] COR_PRF_STATIC_TYPE  *pFieldInfo);  
```  
  
## <a name="parameters"></a>Parameter  

 `classId`  
 in Die ID der Klasse, in der das statische Feld definiert ist.  
  
 `fieldToken`  
 in Das Metadatentoken für das statische Feld.  
  
 `pFieldInfo`  
 vorgenommen Ein Zeiger auf einen Wert der [COR_PRF_STATIC_TYPE](cor-prf-static-type-enumeration.md) Enumeration, der angibt, ob das angegebene Feld statisch ist, und wenn dies der Fall ist, die Art der statischen, die für das Feld gilt.  
  
## <a name="remarks"></a>Hinweise  

 Diese Informationen können verwendet werden, um zu bestimmen, welche Funktion aufgerufen werden soll, um die Adresse des statischen Felds abzurufen.  
  
 Der Profiler-Code sollte weiterhin die Metadaten für ein statisches Feld überprüfen, um sicherzustellen, dass es tatsächlich über eine Adresse verfügt. Statische Literale (d. h. Konstanten) sind nur in den Metadaten vorhanden und verfügen nicht über eine Adresse.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorProfilerInfo-Schnittstelle](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2-Schnittstelle](icorprofilerinfo2-interface.md)
