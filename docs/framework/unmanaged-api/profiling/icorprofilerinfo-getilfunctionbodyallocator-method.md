---
title: ICorProfilerInfo::GetILFunctionBodyAllocator-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILFunctionBodyAllocator
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILFunctionBodyAllocator
helpviewer_keywords:
- GetILFunctionBodyAllocator method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBodyAllocator method [.NET Framework profiling]
ms.assetid: 5da1bf3d-dddf-4892-b266-578ee54d570b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 432ebff36f3b4ee0362e01fc5ecd1bfdb35bc493
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57493010"
---
# <a name="icorprofilerinfogetilfunctionbodyallocator-method"></a>ICorProfilerInfo::GetILFunctionBodyAllocator-Methode
Ruft eine Schnittstelle, die eine Methode zum Belegen von Arbeitsspeicher bietet für die Auslagerung des Texts einer Methode in der Microsoft intermediate Language (MSIL)-Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetILFunctionBodyAllocator(  
    [in]  ModuleID      moduleId,  
    [out] IMethodMalloc **ppMalloc);  
```  
  
## <a name="parameters"></a>Parameter  
 `moduleId`  
 [in] Die ID des Moduls, in dem die Methode befindet.  
  
 `ppMalloc`  
 [out] Ein Zeiger auf ein [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) Schnittstelle, die eine Methode, um die speicherbelegung bereitstellt.  
  
## <a name="remarks"></a>Hinweise  
 Methodenkörper in MSIL-Code muss als eine relative virtuelle Adresse (RVA), relativ zu das geladene Modul gefunden werden, was bedeutet, dass sie das Modul innerhalb von 4 GB folgt. Um ein Tool zum Auslagern des Texts einer Methode, erleichtern die `GetILFunctionBodyAllocator` Methode stellt sicher, dass der Speicher wird in diesem Bereich zugeordnet.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
