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
ms.openlocfilehash: 0c6a8ee1bcc65e640ef871e57acdeef21acd7896
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69930826"
---
# <a name="icordebugdatatarget-interface"></a>ICorDebugDataTarget-Schnittstelle
Stellt eine Rückrufschnittstelle bereit, die Zugriff auf einen bestimmten Zielprozess bietet.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetPlatform-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md)|Bietet Informationen zur-Plattform, einschließlich Prozessorarchitektur und Betriebssystem, auf denen der Ziel Prozess ausgeführt wird.|  
|[ReadVirtual-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-readvirtual-method.md)|Ruft einen Block von zusammenhängenden Arbeitsspeicher ab, der bei der angegebenen Adresse beginnt, und gibt ihn im angegebenen Puffer zurück.|  
|[GetThreadContext-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getthreadcontext-method.md)|Fordert den aktuellen Thread Kontext für den angegebenen Thread an.|  
  
## <a name="remarks"></a>Hinweise  
 `ICorDebugDataTarget`und die zugehörigen Methoden haben die folgenden Merkmale:  
  
- Die Debugdienste aufrufen Methoden für diese Schnittstelle, um auf Arbeitsspeicher und andere Daten im Ziel Prozess zuzugreifen.  
  
- Der Debugger-Client muss diese Schnittstelle entsprechend für das jeweilige Ziel implementieren (z. b. einen Live Prozess oder ein Speicher Abbild).  
  
- Die `ICorDebugDataTarget` Methoden können nur innerhalb von Methoden aufgerufen werden, die in `ICorDebug*` anderen Schnittstellen implementiert sind. Dadurch wird sichergestellt, dass der Debugger-Client steuern kann, in welchem Thread er aufgerufen wird, und wann.  
  
- Die `ICorDebugDataTarget` -Implementierung muss immer aktuelle Informationen über das Ziel zurückgeben.  
  
 Der Ziel Prozess sollte beendet und in keiner Weise geändert werden, während `ICorDebug*` Schnittstellen (und `ICorDebugDataTarget` somit Methoden) aufgerufen werden. Wenn es sich bei dem Ziel um einen Live Prozess handelt und der Status geändert wird, muss die [ICLRDebugging:: OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) -Methode erneut aufgerufen werden, um eine ICorDebugProcess-Ersetzungs Instanz bereitzustellen.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cordebug. idl, Cordebug. h  
  
 **Fern** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
