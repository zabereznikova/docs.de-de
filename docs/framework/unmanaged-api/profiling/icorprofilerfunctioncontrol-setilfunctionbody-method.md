---
title: ICorProfilerFunctionControl::SetILFunctionBody-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl.SetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl::SetILFunctionBody
helpviewer_keywords:
- ICorProfilerFunctionControl::SetILFunctionBody method [.NET Framework profiling]
- SetILFunctionBody method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: 2c33f0f7-75b2-4c19-b2c7-c94b54997576
topic_type:
- apiref
ms.openlocfilehash: f6e2cfe47bdd212e39549544b06bf5b11033a956
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74429887"
---
# <a name="icorprofilerfunctioncontrolsetilfunctionbody-method"></a>ICorProfilerFunctionControl::SetILFunctionBody-Methode
Ersetzt den CIL-Text (Common Intermediate Language) der Methode.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetILFunctionBody(  
    [in]  ULONG   cbNewILMethodHeader,  
    [in, size_is(cbNewILMethodHeader)] LPCBYTE pbNewILMethodHeader);  
```  
  
## <a name="parameters"></a>Parameter  
 `cbNewILMethodHeader`  
 [in] Die Gesamtgröße der neuen CIL, einschließlich des Headers und aller Strukturen, die nach dem Text folgen.  
  
 `pbNewILMethodHeader`  
 [in] Ein Zeiger auf den neuen CIL-Header.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs zurück.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Ersetzung war erfolgreich.|  
  
## <a name="remarks"></a>Hinweise  
 Unlike the [ICorProfilerInfo::SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) method, the `SetILFunctionBody` method manages the memory required for the new CIL body. This means that the CIL body provided by the profiler does not have to be allocated by using the [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) interface or allocated within a particular range. Er kann auf jedem Heap zugeordnet werden. The profiler can free the memory used for its CIL body after `SetILFunctionBody` returns.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerFunctionControl-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)
