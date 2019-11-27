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
ms.openlocfilehash: 8af2b6834ac8655c64a7738c65550b515a4b6675
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439047"
---
# <a name="icorprofilerinfogetilfunctionbodyallocator-method"></a>ICorProfilerInfo::GetILFunctionBodyAllocator-Methode
Ruft eine-Schnittstelle ab, die eine Methode bereitstellt, um Speicher zuzuweisen, der zum Austauschen des Texts einer Methode im MSIL-Code (Microsoft Intermediate Language) verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetILFunctionBodyAllocator(  
    [in]  ModuleID      moduleId,  
    [out] IMethodMalloc **ppMalloc);  
```  
  
## <a name="parameters"></a>Parameter  
 `moduleId`  
 in Die ID des Moduls, in dem sich die Methode befindet.  
  
 `ppMalloc`  
 vorgenommen Ein Zeiger auf eine [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) -Schnittstelle, die eine Methode zum Zuordnen des Arbeitsspeichers bereitstellt.  
  
## <a name="remarks"></a>Hinweise  
 Ein Methoden Text im MSIL-Code muss sich in Relation zum geladenen Modul als relative virtuelle Adresse (RVA) befinden, was bedeutet, dass er auf das Modul innerhalb von 4 GB folgt. Um einem Tool das Austauschen des Texts einer Methode zu erleichtern, stellt die `GetILFunctionBodyAllocator`-Methode sicher, dass der Arbeitsspeicher innerhalb dieses Bereichs zugeordnet wird.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
