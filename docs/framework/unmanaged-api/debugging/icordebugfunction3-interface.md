---
title: ICorDebugFunction3-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugFunction3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: b22717b9-ead5-4eea-887e-789b52d613dc
topic_type:
- apiref
ms.openlocfilehash: 7ef983c2f0785cb97baf8ba1ad3483b46c08af9a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788656"
---
# <a name="icordebugfunction3-interface"></a>ICorDebugFunction3-Schnittstelle
[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]  
  
 Erweitert die ICorDebugFunction-Schnittstelle logisch, um Zugriff auf Code aus einer ReJIT-Anfrage zu bieten.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[GetActiveReJitRequestILCode-Methode](icordebugfunction3-getactiverejitrequestilcode-method.md)|Ruft einen Schnittstellen Zeiger auf einen [icordebugilcode](icordebugilcode-interface.md) ab, der die Il aus einer aktiven ReJIT-Anforderung enthält.|  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
- [ReJIT: Anleitung](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
