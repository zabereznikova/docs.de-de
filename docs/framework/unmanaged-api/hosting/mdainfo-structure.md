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
ms.openlocfilehash: 2d48c3d701b0369ab00150625c26d94f4111b2d9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54607211"
---
# <a name="mdainfo-structure"></a>MDAInfo-Struktur
Enthält Informationen über die `Event_MDAFired` -Ereignis, das die Erstellung einer-Assistent für verwaltetes Debuggen (MDA) ausgelöst.  
  
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
 Verwaltetes Debuggen (MDA) Debugginghilfen, die in Verbindung mit der common Language Runtime (CLR) zum Ausführen von Aufgaben wie das Identifizieren von ungültiger Bedingungen funktionieren in der Common Language Runtime-ausführungs-Engine oder zusätzliche Informationen über den Status der Ausgabe der -Engine. MDAs generieren XML-Nachrichten über Ereignisse, die andernfalls nur schwer abgefangen werden. Sie sind besonders nützlich für das Debuggen von Übergängen zwischen verwaltetem und nicht verwaltetem Code.  
  
 Die Common Language Runtime verwendet die folgenden Schritte aus, wenn ein Ereignis, das die Erstellung eines MDA wird ausgelöst, die ausgelöst wird:  
  
-   Wenn der Host nicht registriert wurde ein [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) Instanz durch den Aufruf [ICLROnEventManager:: RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) benachrichtigt werden sollen ein `Event_MDAFired` Ereignis die Laufzeit fortgesetzt wird, mit der standardmäßig nicht gehosteten Verhalten.  
  
-   Wenn der Host einen Handler für dieses Ereignis registriert hat, überprüft die Laufzeit, um festzustellen, ob ein Debugger an den Prozess angefügt ist. Wenn es sich handelt, unterbricht die Runtime den Debugger. Wenn der Debugger weiterhin auftritt, wird mit dem Host. Wenn kein Debugger angefügt ist, ruft die Runtime `IActionOnCLREvent::OnEvent` und übergibt einen Zeiger auf ein `MDAInfo` -Instanz als die `data` Parameter.  
  
 Der Host kann auswählen, um MDAs zu aktivieren und benachrichtigt werden, wenn ein MDA aktiviert wird. Dies ermöglicht dem Host ein Standardverhalten außer Kraft setzen und den verwalteten Thread abzubrechen, der das Ereignis, um zu verhindern, dass sie den Verarbeitungsstatus beschädigen ausgelöst hat. Weitere Informationen zum Verwenden von MDAs finden Sie unter [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.idl  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Hosten von Strukturen](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
