---
title: ICorDebugInternalFrame2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2
helpviewer_keywords:
- ICorDebugInternalFrame2 interface [.NET Framework debugging]
ms.assetid: d4755569-85b8-4ff4-bf50-0e608e76429f
topic_type:
- apiref
ms.openlocfilehash: a17c46d5ef08963bb0d7fc280ba8b90531e41c5b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719631"
---
# <a name="icordebuginternalframe2-interface"></a>ICorDebugInternalFrame2-Schnittstelle

Stellt Informationen zu internen Frames bereit, u. a. Stapeladresse und Position in Bezug auf ICorDebugFrame-Objekte.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetFrameAddress-Methode](icordebuginternalframe2-getframeaddress-method.md)|Gibt die Stapel Adresse des internen Frames zurück.|  
|[IsCloserToLeaf-Methode](icordebuginternalframe2-isclosertoleaf-method.md)|Überprüft, ob sich der `this` interne Frame näher an dem Blatt als das angegebene ICorDebugFrame-Objekt befindet.|  
  
## <a name="remarks"></a>Hinweise  

 Diese Schnittstelle erweitert die ICorDebug-internalframe-Schnittstelle.  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
