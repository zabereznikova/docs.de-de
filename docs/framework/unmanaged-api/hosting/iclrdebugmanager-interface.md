---
title: ICLRDebugManager-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRDebugManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager
helpviewer_keywords:
- ICLRDebugManager interface [.NET Framework hosting]
ms.assetid: e835062c-c7d6-4945-8a44-2de7ebf3928e
topic_type:
- apiref
ms.openlocfilehash: 653c8d1d3edd38e646b4e90c0e48dbe15bed102a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504263"
---
# <a name="iclrdebugmanager-interface"></a>ICLRDebugManager-Schnittstelle
Stellt Methoden bereit, mit denen ein Host eine Reihe von Aufgaben einem Bezeichner und einem anzeigen Amen zuordnen kann.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[BeginConnection-Methode](iclrdebugmanager-beginconnection-method.md)|Stellt eine neue Verbindung zwischen dem Host und dem Debugger her, um Aufgaben einem Bezeichner und einem anzeigen Amen zuzuordnen.|  
|[EndConnection-Methode](iclrdebugmanager-endconnection-method.md)|Entfernt die Zuordnung zwischen einer Liste von Aufgaben und einem Bezeichner und einem anzeigen Amen.|  
|[GetDacl-Methode](iclrdebugmanager-getdacl-method.md)|Diese Methode ist nicht implementiert.|  
|[IsDebuggerAttached-Methode](iclrdebugmanager-isdebuggerattached-method.md)|Ruft einen Wert ab, der angibt, ob ein Debugger an den Prozess angefügt ist.|  
|[SetConnectionTasks-Methode](iclrdebugmanager-setconnectiontasks-method.md)|Ordnet eine Liste von [ICLRTask](iclrtask-interface.md) -Instanzen einem Bezeichner und einem anzeigen Amen zu.|  
|[SetDacl-Methode](iclrdebugmanager-setdacl-method.md)|Diese Methode ist nicht implementiert.|  
|[SetSymbolReadingPolicy-Methode](iclrdebugmanager-setsymbolreadingpolicy-method.md)|Legt die Richtlinie zum Lesen von Programm Datenbankdateien (PDB) fest. Die Richtlinie bestimmt, ob Informationen über Zeilennummern und Dateien in Aufruf Listen eingeschlossen werden.|  
  
## <a name="remarks"></a>Bemerkungen  
 In Debugszenarien kann ein Host Aufgaben entsprechend seiner eigenen Programmierlogik gruppieren. Beispielsweise kann ein Entwickler mit einer Gruppierung nur die Aufgaben anzeigen, die für die Entwickler-APIs erforderlich sind, anstatt jede Aufgabe zu sehen, die im Prozess ausgeführt wird. `ICLRDebugManager`ermöglicht es dem Host, diese Art von Gruppierung zu implementieren.  
  
> [!IMPORTANT]
> `ICLRDebugManager`Die drei Methoden `BeginConnection` , `SetConnectionTasks` und `EndConnection` sind voneinander abhängig. Sie müssen in der angegebenen Reihenfolge aufgerufen werden, damit Sie erwartungsgemäß funktioniert.  
  
 Die Gruppierung und die Bezeichner und anzeigen Amen, die der Host der Gruppierung zuweist, haben keine Bedeutung für die Common Language Runtime (CLR). Die CLR übergibt die Informationen lediglich an den Debugger.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [Hosten von Schnittstellen](hosting-interfaces.md)
