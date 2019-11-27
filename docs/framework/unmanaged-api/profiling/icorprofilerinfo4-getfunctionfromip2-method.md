---
title: ICorProfilerInfo4::GetFunctionFromIP2-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetFunctionFromIP2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetFunctionFromIP2
helpviewer_keywords:
- ICorProfilerInfo4::GetFunctionFromIP2 method [.NET Framework profiling]
- GetFunctionFromIP2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 46ff70f4-13e9-40a0-802a-0a40abcfc6a0
topic_type:
- apiref
ms.openlocfilehash: 5153a25ef87d9c06bb46b74945c8eb68eb041682
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443143"
---
# <a name="icorprofilerinfo4getfunctionfromip2-method"></a>ICorProfilerInfo4::GetFunctionFromIP2-Methode
Ordnet einen Anweisungs Zeiger für verwalteten Code der JIT-neu kompilierten Version einer Funktion zu.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetFunctionFromIP2(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId,  
    [out] ReJITID *pReJitId);  
```  
  
## <a name="parameters"></a>Parameter  
 `ip`  
 in Der Anweisungs Zeiger in verwaltetem Code.  
  
 `pFunctionId`  
 vorgenommen Die Funktions-ID.  
  
 `pReJitId`  
 vorgenommen Die Identität der neu kompilierten JIT-Version der Funktion.  
  
## <a name="remarks"></a>Hinweise  
 `GetFunctionFromIP2` ähnelt `GetFunctionFromIP`, mit dem Unterschied, dass die JIT-kompilierte ID anstelle der Funktions-ID der Funktion, die die angegebene IP-Adresse enthält, abgerufen wird.  
  
> [!NOTE]
> `GetFunctionFromIP2` können eine Garbage Collection auslöst, während `GetFunctionFromIP` nicht.  Weitere Informationen finden Sie unter [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
