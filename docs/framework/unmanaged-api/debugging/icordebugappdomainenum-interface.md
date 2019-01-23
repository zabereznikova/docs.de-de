---
title: ICorDebugAppDomainEnum-Schnittstelle1
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomainEnum
helpviewer_keywords:
- ICorDebugAppDomainEnum interface [.NET Framework debugging]
ms.assetid: e9226e6e-ca2c-428e-bb38-0c099210f507
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3759be77cd6e6265eb8328669c88225067b99bfd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54509713"
---
# <a name="icordebugappdomainenum-interface1"></a>ICorDebugAppDomainEnum-Schnittstelle1
Stellt die `Next` Methode, die eine angegebene Anzahl von zurückgibt `ICorDebugAppDomainEnum` Werte, die mit der nächsten Position in der Enumeration beginnen. Diese Schnittstelle ist eine Unterklasse von "ICorDebugEnum".  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Next-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-next-method.md)|Ruft die angegebene Anzahl von Anwendungsdomänen aus der Auflistung, beginnend ab der aktuellen Cursorposition ab.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorDebug-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
