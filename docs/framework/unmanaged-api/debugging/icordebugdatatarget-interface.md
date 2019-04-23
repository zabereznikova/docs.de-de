---
title: ICorDebugDataTarget-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget
helpviewer_keywords:
- ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: df5f05be-bed7-4f3c-bc89-dbb435d79a0b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 480fc27bd41f7ca559ceee379b7f6f81c94da0ba
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59188707"
---
# <a name="icordebugdatatarget-interface"></a>ICorDebugDataTarget-Schnittstelle
Stellt eine Rückrufschnittstelle bereit, die Zugriff auf einen bestimmten Zielprozess bietet.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetPlatform-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md)|Enthält Informationen über die Plattform, einschließlich der Prozessorarchitektur und Betriebssystem, auf dem der Zielprozess ausgeführt wird.|  
|[ReadVirtual-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-readvirtual-method.md)|Ruft einen Block zusammenhängender Arbeitsspeicher, die beginnend ab der angegebenen Adresse, und der angegebene Puffer zurückgegeben.|  
|[GetThreadContext-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getthreadcontext-method.md)|Fordert den Kontext des aktuellen Threads für den angegebenen Thread an.|  
  
## <a name="remarks"></a>Hinweise  
 `ICorDebugDataTarget` und seine Methoden weisen folgende Merkmale auf:  
  
-   Die Debuggen von Diensten rufen Methoden für diese Schnittstelle zum Zugriff auf Speicher und andere Daten in den Zielprozess.  
  
-   Der Debuggerclient muss diese Schnittstelle nach Bedarf für die betreffende Zielframework (z. B. einen aktiven Prozess oder ein Speicherabbild) implementieren.  
  
-   Die `ICorDebugDataTarget` Methoden können nur aus aufgerufen werden, innerhalb von Methoden, die in anderen implementiert `ICorDebug*` Schnittstellen. Dadurch wird sichergestellt, dass der Debuggerclient steuern kann, über welchem Thread sie auf und wann aufgerufen wird.  
  
-   Die `ICorDebugDataTarget` Implementierung muss immer auf dem neuesten Stand Informationen über das Ziel zurück.  
  
 Der Zielprozess beendet und in keiner Weise bei der nicht geändert werden sollten `ICorDebug*` Schnittstellen (und somit auch `ICorDebugDataTarget` Methoden) aufgerufen werden. Wenn das Ziel ein, und dessen Zustand ändert, ist die [ICLRDebugging:: OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) Methode muss erneut aufgerufen, um ein Ersatz-ICorDebugProcess-Instanz bereitstellen.  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
