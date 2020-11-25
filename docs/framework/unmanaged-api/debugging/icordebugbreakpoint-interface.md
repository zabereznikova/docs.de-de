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
ms.openlocfilehash: 0c84a91c7da553d0c84a4995b4744576d861dcb9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730200"
---
# <a name="icordebugbreakpoint-interface"></a>ICorDebugBreakpoint-Schnittstelle

Stellt einen Haltepunkt in einer Funktion oder einen Überwachungs Punkt auf einem Wert dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[Activate-Methode](icordebugbreakpoint-activate-method.md)|Legt den aktiven Zustand dieses fest `ICorDebugBreakpoint` .|  
|[IsActive-Methode](icordebugbreakpoint-isactive-method.md)|Ruft einen Wert ab, der angibt, ob diese `ICorDebugBreakpoint` aktiv ist.|  
  
## <a name="remarks"></a>Hinweise  

 Haltepunkte unterstützen bedingte Ausdrücke nicht direkt. Wenn eine solche Funktionalität gewünscht ist, muss Sie von einem Debugger zusätzlich zu implementiert werden `ICorDebugBreakpoint` .  
  
 Die ICorDebugFunctionBreakpoint-Schnittstelle erweitert `ICorDebugBreakpoint` , um Breakpoints innerhalb von Funktionen zu unterstützen.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugschnittstellen](debugging-interfaces.md)
