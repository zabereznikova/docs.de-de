---
title: ICorDebugThread4::HadUnhandledException-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.HadUnhandledException Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::HadUnhandledException
helpviewer_keywords:
- ICorDebugThread4::HadUnhandledException method [.NET Framework debugging]
- HadUnhandledException method [.NET Framework debugging]
ms.assetid: 05558daa-39e2-4c38-aeaf-e2aec4a09468
topic_type:
- apiref
ms.openlocfilehash: d9f0eff35dbe0058398d2d1c851ef85effa9cd28
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122420"
---
# <a name="icordebugthread4hadunhandledexception-method"></a>ICorDebugThread4::HadUnhandledException-Methode
Gibt an, ob für den Thread jemals eine nicht behandelte Ausnahme aufgetreten ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
    );  
```  
  
## <a name="parameters"></a>Parameter  
 `ppBlockingObjectEnum`  
 vorgenommen Ein Zeiger auf die Adresse einer geordneten Enumeration von [Cordebug-blockingobject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) -Strukturen.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Der Thread weist seit seiner Erstellung eine nicht behandelte Ausnahme auf.|  
|S_FALSE|Der Thread weist nie eine nicht behandelte Ausnahme auf.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode gibt an, ob für den Thread jemals eine nicht behandelte Ausnahme aufgetreten ist. Zum Zeitpunkt der Auslösung des nicht behandelten Ausnahme Rückrufs oder zum Initiieren des systemeigenen JIT-Anfügens wird von dieser Methode garantiert S_OK zurückgegeben. Es gibt keine Garantie dafür, dass die [ICorDebugThread. geteption TException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md) -Methode die nicht behandelte Ausnahme zurückgibt. Dies ist jedoch der Fall, wenn der Prozess noch nicht fortgesetzt wurde, nachdem der Rückruf für nicht behandelte Ausnahmen oder das systemeigene JIT-Anfügen erhalten wurde. Darüber hinaus ist es möglich (auch wenn unwahrscheinlich), dass zum Zeitpunkt der Auslösung des nativen JIT-Anfügens mehr als ein Thread mit einer nicht behandelten Ausnahme vorhanden ist. In einem solchen Fall gibt es keine Möglichkeit, zu bestimmen, welche Ausnahme das JIT-attach ausgelöst hat.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugThread4-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
