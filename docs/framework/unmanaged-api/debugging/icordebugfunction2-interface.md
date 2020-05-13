---
title: ICorDebugFunction2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2
helpviewer_keywords:
- ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 2b936bef-9b75-48bf-859f-42e419c65f1c
topic_type:
- apiref
ms.openlocfilehash: 611091d39da6d7f646457457f20ce1eaf37db361
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213204"
---
# <a name="icordebugfunction2-interface"></a>ICorDebugFunction2-Schnittstelle

Erweitert die ICorDebugFunction-Schnittstelle logisch, um Unterstützung für nur eigenen Code schrittweise Debuggen bereitzustellen, die Nichtbenutzer Code überspringt.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[EnumerateNativeCode-Methode](icordebugfunction2-enumeratenativecode-method.md)|(Noch nicht implementiert.) Ruft einen Schnittstellen Zeiger auf eine ICorDebugCodeEnum ab, die die systemeigenen Code Anweisungen in der Funktion enthält, auf die von diesem ICorDebugFunction2-Objekt verwiesen wird.|  
|[GetJMCStatus-Methode](icordebugfunction2-getjmcstatus-method.md)|Ruft einen Wert ab, der angibt, ob diese Funktion als Benutzercode gekennzeichnet ist.|  
|[GetVersionNumber-Methode](icordebugfunction2-getversionnumber-method.md)|Ruft die Edit-und continue-Version dieser Funktion ab.|  
|[SetJMCStatus-Methode](icordebugfunction2-setjmcstatus-method.md)|Markiert diese Funktion für nur eigenen Code Schritt-für-Schritt.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debugschnittstellen](debugging-interfaces.md)
