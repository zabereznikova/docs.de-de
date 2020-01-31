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
ms.openlocfilehash: 9e333d71505a055cfe27df2c79a102c939bafc9d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788478"
---
# <a name="icordebuginternalframe2-interface"></a>ICorDebugInternalFrame2-Schnittstelle
Stellt Informationen zu internen Frames bereit, u. a. Stapeladresse und Position in Bezug auf ICorDebugFrame-Objekte.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[GetFrameAddress-Methode](icordebuginternalframe2-getframeaddress-method.md)|Gibt die Stapel Adresse des internen Frames zurück.|  
|[IsCloserToLeaf-Methode](icordebuginternalframe2-isclosertoleaf-method.md)|Überprüft, ob sich der `this` internen Frame näher an dem Blatt als das angegebene ICorDebugFrame-Objekt befindet.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Schnittstelle erweitert die ICorDebug-internalframe-Schnittstelle.  
  
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
