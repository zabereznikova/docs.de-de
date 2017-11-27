---
title: ICorProfilerObjectEnum::Clone-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerObjectEnum.Clone
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerObjectEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerObjectEnum interface [.NET Framework profiling]
- ICorProfilerObjectEnum::Clone method [.NET Framework profiling]
ms.assetid: b0b2facd-5991-4f4c-932d-c4937f45cef9
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e077115863ab3371570463d0bfd9244b69888f9e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerobjectenumclone-method"></a>ICorProfilerObjectEnum::Clone-Methode
Ruft einen Schnittstellenzeiger auf eine Kopie dieser [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) Schnittstelle.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Clone (  
    [out] ICorProfilerObjectEnum   **ppEnum);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ppEnum`  
 [out] Ein Zeiger auf den Schnittstellenzeiger, der wiederum auf die Kopie dieser zeigt `ICorProfilerObjectEnum` Schnittstelle. Die Kopie behält ihren eigenen Enumerationszustand separat von diesem. Allerdings werden die Kopie ursprüngliche Cursorposition identisch mit der aktuellen Cursorposition des Enumerators.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerObjectEnum-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
