---
title: ICorDebugCode4-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugCode4
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode4
helpviewer_keywords:
- ICorDebugCode4 interface [.NET Framework debugging]
ms.assetid: a3fdf523-274a-449c-920b-9fcb0aed1d97
topic_type:
- apiref
ms.openlocfilehash: 8a373afdf41590ec44a7cbac7360719a12faa82e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720723"
---
# <a name="icordebugcode4-interface"></a>ICorDebugCode4-Schnittstelle

Stellt eine Methode bereit, die einem Debugger das Auflisten der lokalen Variablen und Argumente in einer Funktion ermöglicht.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[EnumerateVariableHomes-Methode](icordebugcode4-enumeratevariablehomes-method.md)|Ruft einen Enumerator für die lokalen Variablen und Argumente in einer Funktion ab.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugCode3-Schnittstelle](icordebugcode3-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
