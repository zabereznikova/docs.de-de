---
title: ICorDebugThread3-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugThread3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3
helpviewer_keywords:
- ICorDebugThread3 interface [.NET Framework debugging]
ms.assetid: eb2860ef-06cb-4968-a6c3-6d048ecda2a4
topic_type:
- apiref
ms.openlocfilehash: dc556dfb59e999ed9b7fc5f35c603dc26c35f314
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378708"
---
# <a name="icordebugthread3-interface"></a>ICorDebugThread3-Schnittstelle
Stellt den Einstiegspunkt für [ICorDebugStackWalk](icordebugstackwalk-interface.md) und die entsprechenden Schnittstellen bereit.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[CreateStackWalk-Methode](icordebugthread3-createstackwalk-method.md)|Erstellt ein [ICorDebugStackWalk](icordebugstackwalk-interface.md) -Objekt für den Thread, dessen Stapel entladen werden soll.|  
|[GetActiveInternalFrames-Methode](icordebugthread3-getactiveinternalframes-method.md)|Gibt ein Array interner Frames ([ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) -Objekte) auf dem Stapel zurück.|  
  
## <a name="remarks"></a>Hinweise  
 `ICorDebugThread3`ist eine logische Erweiterung der ICorDebugThread-Schnittstelle.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
