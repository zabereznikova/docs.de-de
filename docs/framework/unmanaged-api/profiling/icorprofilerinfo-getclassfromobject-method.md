---
title: ICorProfilerInfo::GetClassFromObject-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassFromObject
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassFromObject
helpviewer_keywords:
- GetClassFromObject method [.NET Framework profiling]
- ICorProfilerInfo::GetClassFromObject method [.NET Framework profiling]
ms.assetid: b97493fb-713e-49d5-a73e-5688b2ad0700
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 104dfcaa4120d72f3aa758b66134050f178fef75
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453420"
---
# <a name="icorprofilerinfogetclassfromobject-method"></a>ICorProfilerInfo::GetClassFromObject-Methode
Ruft die `ClassID` eines Objekts, mit dessen `ObjectID`.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetClassFromObject(  
    [in]  ObjectID objectId,  
    [out] ClassID *pClassId);  
```  
  
#### <a name="parameters"></a>Parameter  
 `objectId`  
 [in] Die ID des Objekts, für das Abrufen der `ClassID`.  
  
 `pClassId`  
 [out] Ein Zeiger auf das zurückgegebene `ClassID`.  
  
## <a name="remarks"></a>Hinweise  
 Ein NULL-Wert `pClassId` gibt an, dass `objectId` hat einen Typ, der entladen wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
