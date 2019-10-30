---
title: ICorDebugAssembly-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly
helpviewer_keywords:
- ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: 9d657a28-6984-4c5e-8a54-89d20080baff
topic_type:
- apiref
ms.openlocfilehash: dea3231e3bbb361b56254756c6d99b115f73e792
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133974"
---
# <a name="icordebugassembly-interface"></a>ICorDebugAssembly-Schnittstelle

Stellt eine Assembly dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[EnumerateModules-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-enumeratemodules-method.md)|Ruft einen Enumerator für die Module ab, die in der Assembly enthalten sind.|  
|[GetAppDomain-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getappdomain-method.md)|Ruft einen Schnittstellen Zeiger auf die Anwendungsdomäne ab, die diese `ICorDebugAssembly` Instanz enthält.|  
|[GetCodeBase-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getcodebase-method.md)|Nicht in der aktuellen Version des .NET Framework implementiert.|  
|[GetName-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getname-method.md)|Ruft den Namen der Assembly ab.|  
|[GetProcess-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getprocess-method.md)|Ruft die ICorDebugProcess-Instanz ab, in der die Assembly ausgeführt wird.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
