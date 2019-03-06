---
title: ICorDebugHeapValue3::GetMonitorEventWaitList-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue3.GetMonitorEventWaitList
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue3::GetMonitorEventWaitList
helpviewer_keywords:
- ICorDebugHeapValue3::GetMonitorEventWaitList method [.NET Framework debugging]
- GetMonitorEventWaitList method [.NET Framework debugging]
ms.assetid: 035a9035-ac66-4953-b48a-99652b42b7fe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 06e88e7b3f8e4541c8c7058e27cddb41c78076bc
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57477841"
---
# <a name="icordebugheapvalue3getmonitoreventwaitlist-method"></a>ICorDebugHeapValue3::GetMonitorEventWaitList-Methode
Enthält eine geordnete Liste von Threads, die in die Warteschlange eingereiht werden auf das Ereignis, das eine Sperre für die Überwachung zugeordnet ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetMonitorEventWaitList (  
    [out] ICorDebugThreadEnum **ppThreadEnum  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppThreadEnum`  
 [out] Der ICorDebugThreadEnum-Enumerator, der die geordnete Liste der Threads bereitstellt.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Liste ist nicht leer.|  
|S_FALSE|Die Liste ist leer.|  
  
## <a name="exceptions"></a>Ausnahmen  
  
## <a name="remarks"></a>Hinweise  
 Der erste Thread in der Liste ist der erste Thread, der durch den nächsten Aufruf von freigegeben wird <xref:System.Threading.Monitor.Pulse%28System.Object%29?displayProperty=nameWithType>. Der nächste Thread in der Liste wird auf dem folgenden Aufruf, und So weiter freigegeben.  
  
 Wenn die Liste nicht leer ist, gibt diese Methode S_OK zurück. Die Methode gibt S_FALSE zurück, wenn die Liste leer ist, In diesem Fall ist die Enumeration noch gültig ist, auch wenn es leer ist.  
  
 In beiden Fällen kann die Enumerationsschnittstelle nur für die Dauer des aktuellen Status "synchronisiert" verwendet werden. Verteilten des Threads Schnittstellen sind jedoch gültig, bis der Thread beendet wird.  
  
 Wenn `ppThreadEnum` ist kein gültiger Zeiger ist, das Ergebnis nicht definiert ist.  
  
 Wenn ein Fehler auftritt, sodass nicht bestimmt werden kann, die ggf. Threads für den Monitor, warten gibt die Methode ein HRESULT, der Fehler weist darauf hin.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
