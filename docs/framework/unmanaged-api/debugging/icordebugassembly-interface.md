---
title: '[ICorDebugAssembly Schnittstelle1'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAssembly
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAssembly
helpviewer_keywords: ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: 9d657a28-6984-4c5e-8a54-89d20080baff
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6331c00c2be0805afb56028e9e1a13cd11168cf1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugassembly-interface1"></a>[ICorDebugAssembly Schnittstelle1
Stellt eine Assembly dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[EnumerateModules-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-enumeratemodules-method.md)|Ruft einen Enumerator für die Module in der Assembly enthalten sind.|  
|[GetAppDomain-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getappdomain-method.md)|Ruft einen Schnittstellenzeiger auf die Anwendungsdomäne, die dieses enthält `ICorDebugAssembly` Instanz.|  
|[GetCodeBase-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getcodebase-method.md)|In der aktuellen Version von .NET Framework implementiert nicht.|  
|[GetName-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getname-method.md)|Ruft den Namen der Assembly ab.|  
|[GetProcess-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getprocess-method.md)|Ruft die ICorDebugProcess-Instanz, die in der Assembly ausgeführt wird.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
