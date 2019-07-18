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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9bbc3379ff9523564f4eae7da96fca2247601fcd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765157"
---
# <a name="icordebugthread4hadunhandledexception-method"></a>ICorDebugThread4::HadUnhandledException-Methode
Gibt an, ob der Thread jemals eine nicht behandelte Ausnahme aufgetreten ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
    );  
```  
  
## <a name="parameters"></a>Parameter  
 `ppBlockingObjectEnum`  
 [out] Ein Zeiger auf die Adresse des eine geordnete Enumeration von [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Strukturen.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Der Thread ist seit seiner Erstellung eine nicht behandelte Ausnahme aufgetreten.|  
|S_FALSE|Der Thread ist nie eine nicht behandelte Ausnahme aufgetreten.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode gibt an, ob der Thread jemals eine nicht behandelte Ausnahme aufgetreten ist. Mit der Zeit wird der Rückruf nicht behandelte Ausnahme ausgelöst oder systemeigenes JIT-attach initiiert wird, diese Methode wird immer S_OK zurück. Es gibt keine Garantie, die die [ICorDebugThread.GetCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md) Methode gibt zurück, die nicht behandelte Ausnahme; allerdings es tritt ein, wenn der Prozess nicht noch fortgesetzt wurde nach dem Abrufen des nicht behandelten Ausnahmerückrufs oder nach systemeigenes JIT-attach. Außerdem ist es möglich (wenn auch unwahrscheinlich), sodass mehr als ein Thread mit einem Ausnahmefehler, die zum Zeitpunkt der nativen JIT-attach wird ausgelöst. In diesem Fall besteht keine Möglichkeit festzustellen, welche Ausnahme ausgelöst, der JIT-attach zur Verfügung.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugThread4-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
