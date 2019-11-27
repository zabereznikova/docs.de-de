---
title: ICorProfilerInfo::GetFunctionFromToken-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetFunctionFromToken
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetFunctionFromToken
helpviewer_keywords:
- ICorProfilerInfo::GetFunctionFromToken method [.NET Framework profiling]
- GetFunctionFromToken method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 0eed759f-cce8-405d-88dc-9ee293a38928
topic_type:
- apiref
ms.openlocfilehash: 72531dc4fa7a8afc3bd719d73389fac94e3363bb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439144"
---
# <a name="icorprofilerinfogetfunctionfromtoken-method"></a>ICorProfilerInfo::GetFunctionFromToken-Methode
Ruft die ID einer Funktion ab. Diese Methode ist in der .NET Framework Version 2,0 veraltet. Verwenden Sie stattdessen die [ICorProfilerInfo2:: getfunctionfromdekenandtypeargs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) -Methode.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetFunctionFromToken(  
    [in]  ModuleID   moduleId,  
    [in]  mdToken    token,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="remarks"></a>Hinweise  
 Die `GetFunctionFromToken`-Methode funktioniert nicht für generische Funktionen oder Funktionen in generischen Typen. Es ist mittlerweile veraltet. Verwenden Sie `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` für alle Funktionen.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** 1,1, 1,0  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
