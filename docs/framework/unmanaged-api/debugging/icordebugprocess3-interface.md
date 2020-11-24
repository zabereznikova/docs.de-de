---
title: ICorDebugProcess3-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugProcess3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess3
helpviewer_keywords:
- ICorDebugProcess3 interface [.NET Framework debugging]
ms.assetid: ced9c82e-d7b0-4806-a151-98b6611d3097
topic_type:
- apiref
ms.openlocfilehash: ef8dbd5253c02355f85fba626fa7e68ed62df4bd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686442"
---
# <a name="icordebugprocess3-interface"></a>ICorDebugProcess3-Schnittstelle

Steuert benutzerdefinierte Debuggerbenachrichtigungen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[SetEnableCustomNotification-Methode](icordebugprocess3-setenablecustomnotification-method.md)|Aktiviert und deaktiviert benutzerdefinierte Debugger-Benachrichtigungen vom angegebenen Typ.|  
  
## <a name="remarks"></a>Hinweise  

 Diese Schnittstelle erweitert logisch die ICorDebugProcess-und ICorDebugProcess2-Schnittstellen.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
