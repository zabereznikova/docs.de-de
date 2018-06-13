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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5164e85ecc97de99dcc493c2ba5efa8fc3468471
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443179"
---
# <a name="mdainfo-structure"></a>MDAInfo-Struktur
Enthält Informationen über die `Event_MDAFired` -Ereignis, das die Erstellung von ein Assistent für verwaltetes Debuggen (MDA) ausgelöst.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct _MDAInfo {  
    LPCWSTR  lpMDACaption;  
    LPCWSTR  lpMDAMessage  
} MDAInfo;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`lpMDACaption`|Der Titel des aktuellen MDA. Der Titel beschreibt die Art des Fehlers, der ausgelöst der `Event_MDAFired` Ereignis.|  
|`lpMDAMessage`|Die Ausgabenachricht, die von der aktuellen MDA bereitgestellt wird.|  
  
## <a name="remarks"></a>Hinweise  
 Assistenten für verwaltetes Debuggen (MDAs) sind in Verbindung mit der common Language Runtime (CLR), um Aufgaben wie das Identifizieren von ungültiger Bedingungen arbeiten im Ausführungsmodul Laufzeit debughilfen oder Dump-zusätzliche Informationen über den Status der Sicherungen der Modul. MDAs generieren XML-Meldungen über Ereignisse, die andernfalls schwer abfangen. Sie sind besonders nützlich zum Debuggen von Übergängen zwischen verwaltetem und nicht verwaltetem Code.  
  
 Die Common Language Runtime verwendet die folgenden Schritte aus, wenn ein Ereignis, das die Erstellung eines MDA-Trigger ausgelöst wird:  
  
-   Wenn der Host nicht registriert wurde ein [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) Instanz durch Aufrufen [ICLROnEventManager:: RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) benachrichtigt zu werden ein `Event_MDAFired` -Ereignis die Laufzeit fortgesetzt wird, mit dessen Standardverhalten nicht gehostet.  
  
-   Wenn der Host einen Handler für dieses Ereignis registriert hat, überprüft die Common Language Runtime, ob ein Debugger an den Prozess angefügt ist. Wenn dies der Fall, wird die Common Language Runtime im Debugger unterbrochen. Wenn der Debugger weiterhin auftritt, ruft er auf den Host. Wenn kein Debugger angefügt ist, ruft die Runtime `IActionOnCLREvent::OnEvent` und übergibt einen Zeiger auf eine `MDAInfo` -Instanz als der `data` Parameter.  
  
 Der Host kann auswählen, um MDAs zu aktivieren und benachrichtigt, wenn ein MDA aktiviert wird. Dies ermöglicht dem Host ein Standardverhalten überschreiben und den verwalteten Thread abgebrochen, der das Ereignis, um zu verhindern, dass es den Prozessstatus beschädigen ausgelöst hat. Weitere Informationen zum Verwenden von MDAs finden Sie unter [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.idl  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Hosten von Strukturen](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
