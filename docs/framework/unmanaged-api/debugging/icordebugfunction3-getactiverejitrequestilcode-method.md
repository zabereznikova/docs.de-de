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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: af101e8d842c20394816a3408c74709da941bcd4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416181"
---
# <a name="icordebugfunction3getactiverejitrequestilcode-method"></a>ICorDebugFunction3::GetActiveReJitRequestILCode-Methode
[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]  
  
 Ruft einen Schnittstellenzeiger auf eine [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) , der die IL aus einer aktiven ReJIT-Anfrage enthält.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT GetActiveReJitRequestILCode(  
   ICorDebugILCode **ppReJitedILCode  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ppReJitedILCode`  
 Ein Zeiger auf die IL einer aktiven ReJIT-Anfrage.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die Methode, die durch dieses `ICorDebugFunction3`-Objekt dargestellt wird, über eine aktive ReJIT-Anfrage verfügt, gibt `ppReJitedILCode` einen Zeiger auf deren IL aus. Wenn es besteht keine aktive Anforderung, die häufig vorkommt, dann ist `ppReJitedILCode` ist **null**.  
  
 Eine ReJIT-Anfrage wird aktiv, unmittelbar nach der Ausführung von gibt die [icorprofilercallback4:: Getrejitparameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) -Methodenaufruf. Möglicherweise liegt noch keine JIT-Kompilierung vor und Threads werden immer noch in der ursprünglichen Version des Codes ausgeführt. Eine ReJIT-Anfrage wird inaktiv, während der Profiler-Aufruf an die [icorprofilerinfo4:: Requestrevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md) Methode. Selbst wenn die IL zurückgesetzt wurde, kann ein Thread immer noch im erneut JIT-kompilierten (ReJIT) Code ausgeführt werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorDebugFunction3-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-interface.md)  
 [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [ReJIT: Eine Anleitung](http://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
