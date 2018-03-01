---
title: ICorDebugThread4::HadUnhandledException-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5a79d06f0a65facfbaa821d3dd6af547fd3d0305
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthread4hadunhandledexception-method"></a>ICorDebugThread4::HadUnhandledException-Methode
Gibt an, ob der Thread jemals eine nicht behandelte Ausnahme aufgetreten ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
    );  
```  
  
#### <a name="parameters"></a>Parameter  
 `ppBlockingObjectEnum`  
 [out] Ein Zeiger auf die Adresse des eine geordnete Enumeration von [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Strukturen.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Der Thread ist seit seiner Erstellung eine nicht behandelte Ausnahme aufgetreten.|  
|S_FALSE|Der Thread ist nie eine nicht behandelte Ausnahme aufgetreten.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode gibt an, ob der Thread jemals eine nicht behandelte Ausnahme aufgetreten ist. Nach der Zeit wird der Rückruf für nicht behandelte Ausnahme ausgelöst oder systemeigenes JIT-attach initiiert wird, diese Methode wird sichergestellt, dass S_OK zurückgegeben. Es gibt keine Garantie, die die [ICorDebugThread.GetCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md) Methode gibt zurück, die nicht behandelte Ausnahme; allerdings es tritt ein, wenn der Prozess nicht noch nach Eingang des Ausnahmefehler Rückrufs oder nach fortgesetzt wurde systemeigenes JIT-attach. Außerdem ist es möglich (wenn auch unwahrscheinlich), haben mehrere Threads durch eine nicht behandelte Ausnahme, die zum Zeitpunkt der systemeigenen JIT-attach ausgelöst wird. In einem solchen Fall besteht keine Möglichkeit zu bestimmen, welche Ausnahme ausgelöst, die JIT-attach zur Verfügung.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorDebugThread4-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)  
 [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
