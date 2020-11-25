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
ms.openlocfilehash: 17eda7470e5f2e4b41d1f2ed164843eaeeedea93
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695868"
---
# <a name="icordebugfunction3-interface"></a>ICorDebugFunction3-Schnittstelle

[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]  
  
 Erweitert die ICorDebugFunction-Schnittstelle logisch, um Zugriff auf Code aus einer ReJIT-Anfrage zu bieten.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetActiveReJitRequestILCode-Methode](icordebugfunction3-getactiverejitrequestilcode-method.md)|Ruft einen Schnittstellen Zeiger auf einen [icordebugilcode](icordebugilcode-interface.md) ab, der die Il aus einer aktiven ReJIT-Anforderung enthält.|  
  
## <a name="remarks"></a>Bemerkungen  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
- [ReJIT: A How-To Guide](/archive/blogs/davbr/rejit-a-how-to-guide)
