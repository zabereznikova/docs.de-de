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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 36cb8d5865cdc4c1c8e34671010ede25d531bacf
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782258"
---
# <a name="icorprofilerinfo2getstaticfieldinfo-method"></a>ICorProfilerInfo2::GetStaticFieldInfo-Methode
Ruft einen Wert, der die Art der statischen angibt, die für das angegebene Feld gilt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetStaticFieldInfo (  
    [in] ClassID               classId,  
    [in] mdFieldDef            fieldToken,  
    [out] COR_PRF_STATIC_TYPE  *pFieldInfo);  
```  
  
## <a name="parameters"></a>Parameter  
 `classId`  
 [in] Die ID der Klasse, in der das statische Feld definiert wird.  
  
 `fieldToken`  
 [in] Das Metadatentoken für das statische Feld.  
  
 `pFieldInfo`  
 [out] Ein Zeiger auf den Wert der [COR_PRF_STATIC_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-static-type-enumeration.md) Enumeration, der angibt, ob das angegebene Feld statisch ist, und daher die Art der statischen, die auf das Feld gilt.  
  
## <a name="remarks"></a>Hinweise  
 Diese Informationen kann verwendet werden, um zu bestimmen, welche Funktion aufgerufen wird, um die Adresse des statischen Felds abzurufen.  
  
 Der Profilercode sollten überprüfen, die Metadaten für ein statisches Feld, um sicherzustellen, dass es sich tatsächlich um eine Adresse hat. Statische Literale (d. h. Konstanten) nur in den Metadaten vorhanden sein und müssen sich nicht auf eine Adresse.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
