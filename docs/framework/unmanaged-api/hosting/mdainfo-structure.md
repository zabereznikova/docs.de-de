---
title: MDAInfo-Struktur
ms.date: 03/30/2017
api_name:
- MDAInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- MDAInfo
helpviewer_keywords:
- MDAInfo structure [.NET Framework hosting]
ms.assetid: fb8c14f7-d461-43d1-8b47-adb6723b9b93
topic_type:
- apiref
ms.openlocfilehash: 9a2f513d40d722f1b0aad823ac7c0d93bda5615f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123264"
---
# <a name="mdainfo-structure"></a>MDAInfo-Struktur
Stellt Details zum `Event_MDAFired` Ereignis bereit, das die Erstellung eines Assistenten für verwaltetes Debuggen (MDA) auslöst.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef struct _MDAInfo {  
    LPCWSTR  lpMDACaption;  
    LPCWSTR  lpMDAMessage  
} MDAInfo;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`lpMDACaption`|Der Titel des aktuellen MDA. Der Titel beschreibt die Art des Fehlers, der das `Event_MDAFired` Ereignis ausgelöst hat.|  
|`lpMDAMessage`|Die vom aktuellen MDA bereitgestellte Ausgabe Meldung.|  
  
## <a name="remarks"></a>Hinweise  
 Assistenten für verwaltetes Debuggen (MDAs) sind Debugginghilfen, die in Verbindung mit dem Common Language Runtime (CLR) funktionieren, um Aufgaben wie das Identifizieren von ungültigen Bedingungen in der Lauf Zeit Ausführungs-Engine oder das Sichern zusätzlicher Informationen über den Zustand des ge. MDAs generiert XML-Meldungen über Ereignisse, die andernfalls schwierig zu erfassen sind. Sie sind besonders nützlich zum Debuggen von Übergängen zwischen verwaltetem und nicht verwaltetem Code.  
  
 Die Laufzeit führt die folgenden Schritte aus, wenn ein Ereignis ausgelöst wird, das die Erstellung eines MDA auslöst:  
  
- Wenn der Host keine [iaktiononclrevent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) -Instanz durch Aufrufen von [ICLROnEventManager:: registeraktiononevent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) registriert hat, um über ein `Event_MDAFired` Ereignis benachrichtigt zu werden, wird die Laufzeit mit dem standardmäßigen, nicht gehosteten Verhalten fortgesetzt.  
  
- Wenn der Host einen Handler für dieses Ereignis registriert hat, prüft die Laufzeit, ob ein Debugger an den Prozess angefügt ist. Wenn dies der Fall ist, unterbricht die Laufzeit den Debugger. Wenn der Debugger fortgesetzt wird, ruft er den Host auf. Wenn kein Debugger angefügt ist, ruft die Laufzeit `IActionOnCLREvent::OnEvent` auf und übergibt einen Zeiger auf eine `MDAInfo` Instanz als `data` Parameter.  
  
 Der Host kann MDAs aktivieren und benachrichtigt werden, wenn ein MDA aktiviert wird. Dadurch erhält der Host die Möglichkeit, das Standardverhalten zu überschreiben und den verwalteten Thread abzubrechen, der das Ereignis ausgelöst hat, um zu verhindern, dass der Prozessstatus beschädigt wird. Weitere Informationen zur Verwendung von MDAs finden Sie unter [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. idl  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Hosten von Strukturen](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [Diagnosing Errors with Managed Debugging Assistants (Fehlerdiagnose mit den Assistenten für verwaltetes Debugging)](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
