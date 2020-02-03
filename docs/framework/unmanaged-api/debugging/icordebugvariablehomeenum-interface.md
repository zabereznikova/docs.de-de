---
title: ICorDebugVariableHomeEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHomeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHomeEnum
helpviewer_keywords:
- ICorDebugVariableHomeEnum interface [.NET Framework debugging]
ms.assetid: c312ae6d-c8dc-48d6-9f1e-ead515c88fdf
topic_type:
- apiref
ms.openlocfilehash: 74b3c7bed54f3735efbd5d2c56962d427518f71a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790946"
---
# <a name="icordebugvariablehomeenum-interface"></a>ICorDebugVariableHomeEnum-Schnittstelle
Stellt einen Enumerator für die lokalen Variablen und Argumente in einer Funktion bereit.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[Next-Methode](icordebugvariablehomeenum-next-method.md)|Ruft die angegebene Anzahl von [icordebugvariablehome](icordebugvariablehome-interface.md) -Instanzen ab, die Informationen zu den lokalen Variablen und Argumenten in einer Funktion enthalten.|  
  
## <a name="remarks"></a>Hinweise  
 Die `ICorDebugVariableHomeEnum`-Schnittstelle implementiert die ICorDebugEnum-Schnittstelle.  
  
 Eine `ICorDebugVariableHomeEnum` Instanz wird mit [icordebugvariablehome](icordebugvariablehome-interface.md) -Instanzen aufgefüllt, indem die [ICorDebugCode4:: enumeratevariablehomes](icordebugcode4-enumeratevariablehomes-method.md) -Methode aufgerufen wird. Jede [icorentbugvariablehome](icordebugvariablehome-interface.md) -Instanz in der Auflistung stellt eine lokale Variable oder ein Argument in einer Funktion dar. Die [icordebugvariablehome](icordebugvariablehome-interface.md) -Objekte in der Auflistung können durch Aufrufen der [icordebugvariablehomedenum:: Next](icordebugvariablehomeenum-next-method.md) -Methode aufgelistet werden.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugVariableHome-Schnittstelle](icordebugvariablehome-interface.md)
- [Debuggen von Schnittstellen](debugging-interfaces.md)
