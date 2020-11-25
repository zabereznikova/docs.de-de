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
ms.openlocfilehash: 8e88d90e3291d21888fae7aa162f84b6377658c5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730018"
---
# <a name="mdainfo-structure"></a>MDAInfo-Struktur

Stellt Details zum- `Event_MDAFired` Ereignis bereit, das die Erstellung eines Assistenten für verwaltetes Debuggen (MDA) auslöst.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef struct _MDAInfo {  
    LPCWSTR  lpMDACaption;  
    LPCWSTR  lpMDAMessage  
} MDAInfo;  
```  
  
## <a name="members"></a>Member  
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`lpMDACaption`|Der Titel des aktuellen MDA. Der Titel beschreibt die Art des Fehlers, der das `Event_MDAFired` Ereignis ausgelöst hat.|  
|`lpMDAMessage`|Die vom aktuellen MDA bereitgestellte Ausgabe Meldung.|  
  
## <a name="remarks"></a>Hinweise  

 Assistenten für verwaltetes Debuggen (MDAs) sind Debugginghilfen, die zusammen mit dem Common Language Runtime (CLR) ausgeführt werden, um Aufgaben wie das Identifizieren von ungültigen Bedingungen in der Lauf Zeit Ausführungs-Engine oder das Sichern zusätzlicher Informationen über den Zustand der Engine auszuführen. MDAs generiert XML-Meldungen über Ereignisse, die andernfalls schwierig zu erfassen sind. Sie sind besonders nützlich zum Debuggen von Übergängen zwischen verwaltetem und nicht verwaltetem Code.  
  
 Die Laufzeit führt die folgenden Schritte aus, wenn ein Ereignis ausgelöst wird, das die Erstellung eines MDA auslöst:  
  
- Wenn der Host keine [iaktiononclrevent](iactiononclrevent-interface.md) -Instanz durch Aufrufen von [ICLROnEventManager:: registeraktiononevent](iclroneventmanager-registeractiononevent-method.md) registriert hat, um über ein Ereignis benachrichtigt zu werden `Event_MDAFired` , wird die Laufzeit mit dem standardmäßigen nicht gehosteten Verhalten fortgesetzt.  
  
- Wenn der Host einen Handler für dieses Ereignis registriert hat, prüft die Laufzeit, ob ein Debugger an den Prozess angefügt ist. Wenn dies der Fall ist, unterbricht die Laufzeit den Debugger. Wenn der Debugger fortgesetzt wird, ruft er den Host auf. Wenn kein Debugger angefügt ist, ruft die Laufzeit `IActionOnCLREvent::OnEvent` auf und übergibt einen Zeiger auf eine- `MDAInfo` Instanz als- `data` Parameter.  
  
 Der Host kann MDAs aktivieren und benachrichtigt werden, wenn ein MDA aktiviert wird. Dadurch erhält der Host die Möglichkeit, das Standardverhalten zu überschreiben und den verwalteten Thread abzubrechen, der das Ereignis ausgelöst hat, um zu verhindern, dass der Prozessstatus beschädigt wird. Weitere Informationen zur Verwendung von MDAs finden Sie unter [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. idl  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Hosten von Strukturen](hosting-structures.md)
- [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
