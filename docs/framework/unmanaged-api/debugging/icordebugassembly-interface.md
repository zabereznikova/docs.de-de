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
ms.openlocfilehash: d9e2236b944137de82bb056820f81014febfcc5f
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894900"
---
# <a name="icordebugassembly-interface"></a>ICorDebugAssembly-Schnittstelle

Stellt eine Assembly dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[EnumerateModules-Methode](icordebugassembly-enumeratemodules-method.md)|Ruft einen Enumerator für die Module ab, die in der Assembly enthalten sind.|  
|[GetAppDomain-Methode](icordebugassembly-getappdomain-method.md)|Ruft einen Schnittstellen Zeiger auf die Anwendungsdomäne ab, die `ICorDebugAssembly` diese Instanz enthält.|  
|[GetCodeBase-Methode](icordebugassembly-getcodebase-method.md)|Nicht in der aktuellen Version des .NET Framework implementiert.|  
|[GetName-Methode](icordebugassembly-getname-method.md)|Ruft den Namen der Assembly ab.|  
|[GetProcess-Methode](icordebugassembly-getprocess-method.md)|Ruft die ICorDebugProcess-Instanz ab, in der die Assembly ausgeführt wird.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugschnittstellen](debugging-interfaces.md)
