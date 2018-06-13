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
ms.openlocfilehash: a395579892ff2410865a4fcdd19cf20449b82b88
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421071"
---
# <a name="icordebugheapvalue3getmonitoreventwaitlist-method"></a>ICorDebugHeapValue3::GetMonitorEventWaitList-Methode
Stellt eine geordnete Liste von Threads in der Warteschlange auf das Ereignis, das einen Monitorsperre zugeordnet ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetMonitorEventWaitList (  
    [out] ICorDebugThreadEnum **ppThreadEnum  
);  
```  
  
#### <a name="parameters"></a>Parameter  
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
 Der erste Thread in der Liste ist der erste Thread, der durch den nächsten Aufruf freigegeben wird <xref:System.Threading.Monitor.Pulse%28System.Object%29?displayProperty=nameWithType>. Der nächste Thread in der Liste wird der folgende Aufruf usw. veröffentlicht.  
  
 Wenn die Liste nicht leer ist, gibt diese Methode S_OK zurück. Wenn die Liste leer ist, gibt die Methode "S_FALSE" zurück. In diesem Fall ist die Enumeration noch gültig sind, obwohl es leer ist.  
  
 In beiden Fällen ist die Enumerationsschnittstelle nur für die Dauer des aktuellen Status "synchronisiert" verwendet werden kann. Verteilten die Thread-Schnittstellen sind jedoch gültig, bis der Thread beendet wird.  
  
 Wenn `ppThreadEnum` ist kein gültiger Zeiger ist, das Ergebnis nicht definiert ist.  
  
 Wenn ein Fehler auftritt, sodass nicht ermittelt werden kann, die ggf. Threads für den Monitor warten gibt die Methode ein HRESULT, das Fehler weist darauf hin.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
