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
ms.openlocfilehash: 0fbff178efd4d0dff3593907b3d40e946be2ff6e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121296"
---
# <a name="icordebugheapvalue3getmonitoreventwaitlist-method"></a>ICorDebugHeapValue3::GetMonitorEventWaitList-Methode
Stellt eine geordnete Liste von Threads bereit, die für das-Ereignis in die Warteschlange eingereiht werden, das einer Monitor Sperre zugeordnet ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetMonitorEventWaitList (  
    [out] ICorDebugThreadEnum **ppThreadEnum  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppThreadEnum`  
 vorgenommen Der ICorDebugThreadEnum-Enumerator, der die geordnete Liste der Threads bereitstellt.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Liste ist nicht leer.|  
|S_FALSE|Die Liste ist leer.|  
  
## <a name="exceptions"></a>Ausnahmen  
  
## <a name="remarks"></a>Hinweise  
 Der erste Thread in der Liste ist der erste Thread, der vom nächsten <xref:System.Threading.Monitor.Pulse%28System.Object%29?displayProperty=nameWithType>-Auflistungs-aufgerufen wird. Der nächste Thread in der Liste wird für den folgenden-Befehl freigegeben, usw.  
  
 Wenn die Liste nicht leer ist, gibt diese Methode S_OK zurück. Wenn die Liste leer ist, gibt die Methode S_FALSE zurück. in diesem Fall ist die Enumeration weiterhin gültig, obwohl Sie leer ist.  
  
 In beiden Fällen kann die Enumerationsschnittstelle nur für die Dauer des aktuellen synchronisierten Zustands verwendet werden. Die von ihm ausgegebene Schnittstellen des Threads sind jedoch gültig, bis der Thread beendet wird.  
  
 Wenn `ppThreadEnum` kein gültiger Zeiger ist, ist das Ergebnis nicht definiert.  
  
 Wenn ein Fehler auftritt, sodass nicht bestimmt werden kann, welche Threads ggf. auf den Monitor warten, gibt die Methode ein HRESULT zurück, das einen Fehler anzeigt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
