---
title: ICorDebugExceptionObjectValue-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectValue
helpviewer_keywords:
- ICorDebugExceptionObjectValue interface [.NET Framework debugging]
ms.assetid: 43416dd5-8892-4106-9f59-f9143b19ddb4
topic_type:
- apiref
ms.openlocfilehash: 6a0c33799b2b2aaa48e3b18b7b4bb37643508bd4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678882"
---
# <a name="icordebugexceptionobjectvalue-interface"></a>ICorDebugExceptionObjectValue-Schnittstelle

Erweitert die ICorDebugObjectValue-Schnittstelle, um Stapel Verfolgungs Informationen von einem verwalteten Ausnahme Objekt bereitzustellen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[EnumerateExceptionCallStack-Methode](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md)|Ruft einen Enumerator für die in einem Ausnahme Objekt eingebettete-Aufzählung ab.|  
  
## <a name="remarks"></a>Hinweise  

 Der-Befehl `QueryInterface` wird für verwaltete Objekte, die von abgeleitet werden, erfolgreich ausgeführt <xref:System.Exception?displayProperty=nameWithType> .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
