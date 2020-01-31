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
ms.openlocfilehash: 9029d53872108bc1953fd22c584b6e01a6f3c7ab
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788869"
---
# <a name="icordebugdatatarget-interface"></a>ICorDebugDataTarget-Schnittstelle
Stellt eine Rückrufschnittstelle bereit, die Zugriff auf einen bestimmten Zielprozess bietet.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[GetPlatform-Methode](icordebugdatatarget-getplatform-method.md)|Bietet Informationen zur-Plattform, einschließlich Prozessorarchitektur und Betriebssystem, auf denen der Ziel Prozess ausgeführt wird.|  
|[ReadVirtual-Methode](icordebugdatatarget-readvirtual-method.md)|Ruft einen Block von zusammenhängenden Arbeitsspeicher ab, der bei der angegebenen Adresse beginnt, und gibt ihn im angegebenen Puffer zurück.|  
|[GetThreadContext-Methode](icordebugdatatarget-getthreadcontext-method.md)|Fordert den aktuellen Thread Kontext für den angegebenen Thread an.|  
  
## <a name="remarks"></a>Hinweise  
 `ICorDebugDataTarget` und seine Methoden haben die folgenden Merkmale:  
  
- Die Debugdienste aufrufen Methoden für diese Schnittstelle, um auf Arbeitsspeicher und andere Daten im Ziel Prozess zuzugreifen.  
  
- Der Debugger-Client muss diese Schnittstelle entsprechend für das jeweilige Ziel implementieren (z. b. einen Live Prozess oder ein Speicher Abbild).  
  
- Die `ICorDebugDataTarget`-Methoden können nur innerhalb von Methoden aufgerufen werden, die in anderen `ICorDebug*` Schnittstellen implementiert werden. Dadurch wird sichergestellt, dass der Debugger-Client steuern kann, in welchem Thread er aufgerufen wird, und wann.  
  
- Die `ICorDebugDataTarget`-Implementierung muss immer aktuelle Informationen über das Ziel zurückgeben.  
  
 Der Ziel Prozess sollte beendet und in keiner Weise geändert werden, während `ICorDebug*` Schnittstellen (und somit `ICorDebugDataTarget` Methoden) aufgerufen werden. Wenn es sich bei dem Ziel um einen Live Prozess handelt und der Status geändert wird, muss die [ICLRDebugging:: OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) -Methode erneut aufgerufen werden, um eine ICorDebugProcess-Ersetzungs Instanz bereitzustellen.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
