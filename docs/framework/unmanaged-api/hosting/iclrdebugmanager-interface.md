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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 22c3a480e2b68377e300df1083b3178ee4e2d2a9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59198841"
---
# <a name="iclrdebugmanager-interface"></a>ICLRDebugManager-Schnittstelle
Bietet Methoden, mit die einen Host eine Reihe von Aufgaben mit einem Bezeichner sowie einen Anzeigenamen zuordnen können.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[BeginConnection-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)|Stellt eine neue Verbindung zwischen dem Host und den Debugger, einen Bezeichner und einen benutzerfreundlichen Namen Aufgaben zugeordnet werden soll.|  
|[EndConnection-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)|Entfernt die Zuordnung zwischen einer Liste von Aufgaben und einen Bezeichner und einen Anzeigenamen ein.|  
|[GetDacl-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-getdacl-method.md)|Diese Methode ist nicht implementiert.|  
|[IsDebuggerAttached-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-isdebuggerattached-method.md)|Ruft einen Wert ab, der angibt, ob ein Debugger an den Prozess angefügt ist.|  
|[SetConnectionTasks-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)|Ordnet einer Liste von [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) -Instanzen mit einem Bezeichner und einen Anzeigenamen ein.|  
|[SetDacl-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setdacl-method.md)|Diese Methode ist nicht implementiert.|  
|[SetSymbolReadingPolicy-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md)|Legt die Richtlinie für das Lesen von Programmdatenbankdateien (PDB). Die Richtlinie wird bestimmt, ob Informationen zu Zeilennummern und Dateien in Aufruflisten enthalten ist.|  
  
## <a name="remarks"></a>Hinweise  
 In Debugszenarien, kann ein Host zum Gruppieren von Aufgaben entsprechend der eigenen Programmierlogik möchte. Eine Gruppierung können z. B. ein Entwickler, die nur die Aufgaben der Entwickler-APIs, anstatt alle Aufgaben, die im Prozess ausgeführt wird, finden Sie unter. `ICLRDebugManager` ermöglicht dem Host, um diese Art der Gruppierung zu implementieren.  
  
> [!IMPORTANT]
>  Drei `ICLRDebugManager` Methoden `BeginConnection`, `SetConnectionTasks` und `EndConnection`, voneinander abhängig sind. Sie müssen in der angegebenen Reihenfolge erwartungsgemäß aufgerufen werden.  
  
 Haben die Gruppierung, und die Bezeichner und den Anzeigenamen, die zur Gruppierung, der Host weist keine Bedeutung für die common Language Runtime (CLR). Die CLR übergibt lediglich die Informationen an dem Debugger.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
