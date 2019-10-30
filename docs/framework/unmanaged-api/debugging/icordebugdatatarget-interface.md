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
ms.openlocfilehash: f8b216d370f7278f6d2a4beed5bab88afa666200
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122214"
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
 `ICorDebugDataTarget` und seine Methoden haben die folgenden Merkmale:  
  
- Die Debugdienste aufrufen Methoden für diese Schnittstelle, um auf Arbeitsspeicher und andere Daten im Ziel Prozess zuzugreifen.  
  
- Der Debugger-Client muss diese Schnittstelle entsprechend für das jeweilige Ziel implementieren (z. b. einen Live Prozess oder ein Speicher Abbild).  
  
- Die `ICorDebugDataTarget`-Methoden können nur innerhalb von Methoden aufgerufen werden, die in anderen `ICorDebug*` Schnittstellen implementiert werden. Dadurch wird sichergestellt, dass der Debugger-Client steuern kann, in welchem Thread er aufgerufen wird, und wann.  
  
- Die `ICorDebugDataTarget`-Implementierung muss immer aktuelle Informationen über das Ziel zurückgeben.  
  
 Der Ziel Prozess sollte beendet und in keiner Weise geändert werden, während `ICorDebug*` Schnittstellen (und somit `ICorDebugDataTarget` Methoden) aufgerufen werden. Wenn es sich bei dem Ziel um einen Live Prozess handelt und der Status geändert wird, muss die [ICLRDebugging:: OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) -Methode erneut aufgerufen werden, um eine ICorDebugProcess-Ersetzungs Instanz bereitzustellen.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
