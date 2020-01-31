---
title: ICorDebugFunction3::GetActiveReJitRequestILCode-Methode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugFunction3.GetActiveReJitRequestILCode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 88584574-ade5-45b2-9778-489ed5c4dd7f
topic_type:
- apiref
ms.openlocfilehash: 70a55b833acb7fa946c694a63e1e8b51562938bc
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777732"
---
# <a name="icordebugfunction3getactiverejitrequestilcode-method"></a>ICorDebugFunction3::GetActiveReJitRequestILCode-Methode
[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]  
  
 Ruft einen Schnittstellen Zeiger auf einen [icordebugilcode](icordebugilcode-interface.md) ab, der die Il aus einer aktiven ReJIT-Anforderung enthält.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT GetActiveReJitRequestILCode(  
   ICorDebugILCode **ppReJitedILCode  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `ppReJitedILCode`  
 Ein Zeiger auf die IL einer aktiven ReJIT-Anfrage.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die Methode, die durch dieses `ICorDebugFunction3`-Objekt dargestellt wird, über eine aktive ReJIT-Anfrage verfügt, gibt `ppReJitedILCode` einen Zeiger auf deren IL aus. Wenn keine aktive Anforderung vorhanden ist, was häufig der Fall ist, ist `ppReJitedILCode` **null**.  
  
 Eine ReJIT-Anforderung wird unmittelbar nach der Ausführung des [ICorProfilerCallback4:: getrejitparameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) -Methoden Aufrufes aktiv. Möglicherweise liegt noch keine JIT-Kompilierung vor und Threads werden immer noch in der ursprünglichen Version des Codes ausgeführt. Eine ReJIT-Anforderung wird beim Aufrufen der [ICorProfilerInfo4:: requestrevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md) -Methode des Profilers inaktiv. Selbst wenn die IL zurückgesetzt wurde, kann ein Thread immer noch im erneut JIT-kompilierten (ReJIT) Code ausgeführt werden.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugFunction3-Schnittstelle](icordebugfunction3-interface.md)
- [Debuggen von Schnittstellen](debugging-interfaces.md)
- [ReJIT: Anleitung](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
