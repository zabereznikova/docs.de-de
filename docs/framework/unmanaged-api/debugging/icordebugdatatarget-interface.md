---
title: ICorDebugDataTarget-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugDataTarget
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugDataTarget
helpviewer_keywords: ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: df5f05be-bed7-4f3c-bc89-dbb435d79a0b
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 030ad5e61d215bd840da5b16a56e4b8f8b7791ff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdatatarget-interface"></a>ICorDebugDataTarget-Schnittstelle
Stellt eine Rückrufschnittstelle bereit, die Zugriff auf einen bestimmten Zielprozess bietet.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetPlatform-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md)|Enthält Informationen über die Plattform, einschließlich der Prozessorarchitektur und Betriebssystem, auf denen der Zielprozess ausgeführt wird.|  
|[ReadVirtual-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-readvirtual-method.md)|Ruft einen Block zusammenhängender Arbeitsspeicher ab der angegebenen Adresse, und wird in der bereitgestellte Puffer zurückgegeben.|  
|[GetThreadContext-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getthreadcontext-method.md)|Fordert den aktuellen Kontext des Threads für den angegebenen Thread.|  
  
## <a name="remarks"></a>Hinweise  
 `ICorDebugDataTarget`und seine Methoden besitzen die folgenden Eigenschaften:  
  
-   Die Debugdienste rufen Methoden für diese Schnittstelle den Zugriff auf Speicher und andere Daten im Zielprozess.  
  
-   Der Debuggerclient muss diese Schnittstelle für das bestimmte Ziel (z. B. ein Liveprozess oder ein Speicherabbild) geeigneten Form implementieren.  
  
-   Die `ICorDebugDataTarget` Methoden können nur aus aufgerufen werden, innerhalb von Methoden, die in anderen implementiert `ICorDebug*` Schnittstellen. Dadurch wird sichergestellt, dass der Debuggerclient steuern kann, über welchen Thread auf und wann Aufrufversuch stattfindet.  
  
-   Die `ICorDebugDataTarget` Implementierung muss stets aktuelle Informationen zu dem Ziel.  
  
 Der Zielprozess beendet und in keiner Weise beim nicht geändert werden `ICorDebug*` Schnittstellen (und daher `ICorDebugDataTarget` Methoden) aufgerufen werden. Wenn das Ziel ein Liveprozess und dessen Zustand ändert, ist die [ICLRDebugging:: OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) -Methode erneut aufgerufen, um ein Ersatz-ICorDebugProcess-Instanz bereitstellen muss.  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debugschnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
