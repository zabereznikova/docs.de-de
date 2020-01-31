---
title: ICorDebugBreakpoint-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpoint
helpviewer_keywords:
- ICorDebugBreakpoint interface [.NET Framework debugging]
ms.assetid: aa5ad3d7-e1bb-42af-99bc-471224e3bcaa
topic_type:
- apiref
ms.openlocfilehash: 53d8d219a13f2dade16a338efccf0837f8de0158
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784373"
---
# <a name="icordebugbreakpoint-interface"></a>ICorDebugBreakpoint-Schnittstelle

Stellt einen Haltepunkt in einer Funktion oder einen Überwachungs Punkt auf einem Wert dar.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[Activate-Methode](icordebugbreakpoint-activate-method.md)|Legt den aktiven Zustand dieses `ICorDebugBreakpoint`fest.|  
|[IsActive-Methode](icordebugbreakpoint-isactive-method.md)|Ruft einen Wert ab, der angibt, ob dieses `ICorDebugBreakpoint` aktiv ist.|  
  
## <a name="remarks"></a>Hinweise  
 Haltepunkte unterstützen bedingte Ausdrücke nicht direkt. Wenn eine solche Funktionalität gewünscht ist, muss Sie von einem Debugger zusätzlich zu `ICorDebugBreakpoint`implementiert werden.  
  
 Die ICorDebugFunctionBreakpoint-Schnittstelle erweitert `ICorDebugBreakpoint`, um Breakpoints innerhalb von Funktionen zu unterstützen.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](debugging-interfaces.md)
