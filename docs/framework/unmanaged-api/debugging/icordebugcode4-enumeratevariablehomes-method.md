---
title: 'ICorDebugCode4:: enumeratevariablehomes-Methode'
ms.date: 03/30/2017
api_name:
- ICorDebugCode4.EnumerateVariableHomes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode4::EnumerateVariableHomes
helpviewer_keywords:
- EnumerateVariableHomes method [.NET Framework debugging]
- ICorDebugCode4::EnumerateVariableHomes method [.NET Framework debugging]
ms.assetid: 802c01ff-8b80-4733-b6dd-03ab6ff7fa11
topic_type:
- apiref
ms.openlocfilehash: ca452b230e2508f2d69c9aa38f274db506f3a906
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784089"
---
# <a name="icordebugcode4enumeratevariablehomes-method"></a>ICorDebugCode4:: enumeratevariablehomes-Methode
Ruft einen Enumerator für die lokalen Variablen und Argumente in einer Funktion ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumerateVariableHomes(  
    [out] ICorDebugVariableHomeEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `ppEnum`  
 Ein Zeiger auf die Adresse eines [icordebugvariablehomeenum](icordebugvariablehomeenum-interface.md) -Schnittstellen Objekts, das ein Enumerator für die lokalen Variablen und Argumente in einer Funktion ist.  
  
## <a name="remarks"></a>Hinweise  
 Das [icordebugvariablehomeenum](icordebugvariablehomeenum-interface.md) -Schnittstellen Objekt ist ein Standard-Enumerator, der von der Schnittstelle "ICorDebugEnum" abgeleitet ist und die das Auflisten von [icordebugvariablehome](icordebugvariablehome-interface.md) -Objekten ermöglicht. Die Auflistung enthält möglicherweise mehrere [icorentbugvariablehome](icordebugvariablehome-interface.md) -Objekte für denselben Slot-oder Argument Index, wenn Sie an unterschiedlichen Punkten in der Funktion unterschiedliche Haushalte haben.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugCode4-Schnittstelle](icordebugcode4-interface.md)
- [Debuggen von Schnittstellen](debugging-interfaces.md)
