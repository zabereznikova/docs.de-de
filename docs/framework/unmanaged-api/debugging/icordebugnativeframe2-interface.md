---
title: ICorDebugNativeFrame2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2
helpviewer_keywords:
- ICorDebugNativeFrame2 interface [.NET Framework debugging]
ms.assetid: 52a80838-af36-4399-bc97-d8a4c6d76df2
topic_type:
- apiref
ms.openlocfilehash: ddf5af0bc0a5e5e21d837d8b2f3f76185ed7e2b1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724714"
---
# <a name="icordebugnativeframe2-interface"></a>ICorDebugNativeFrame2-Schnittstelle

Stellt Methoden bereit, die auf Beziehungen zwischen untergeordneten und übergeordneten Frames überprüfen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[IsChild-Methode](icordebugnativeframe2-ischild-method.md)|Bestimmt, ob der aktuelle Frame ein untergeordneter Frame ist.|  
|[IsMatchingParentFrame-Methode](icordebugnativeframe2-ismatchingparentframe-method.md)|Bestimmt, ob der angegebene Frame dem aktuellen Frame übergeordnet ist.|  
|[GetStackParameterSize-Methode](icordebugnativeframe2-getstackparametersize-method.md)|Gibt die kumulierte Größe der Parameter auf dem Stapel unter x86-Betriebssystemen zurück.|  
  
## <a name="remarks"></a>Hinweise  

 Diese Schnittstelle erweitert logisch die ICorDebugNativeFrame-Schnittstelle.  
  
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
