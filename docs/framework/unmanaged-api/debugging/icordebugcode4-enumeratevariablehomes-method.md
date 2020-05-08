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
ms.openlocfilehash: 5f731b1459542c3f5378790b21f2ea576e89ad97
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893344"
---
# <a name="icordebugcode4enumeratevariablehomes-method"></a>ICorDebugCode4:: enumeratevariablehomes-Methode
Ruft einen Enumerator für die lokalen Variablen und Argumente in einer Funktion ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumerateVariableHomes(  
    [out] ICorDebugVariableHomeEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppEnum`  
 Ein Zeiger auf die Adresse eines [icordebugvariablehomeenum](icordebugvariablehomeenum-interface.md) -Schnittstellen Objekts, das ein Enumerator für die lokalen Variablen und Argumente in einer Funktion ist.  
  
## <a name="remarks"></a>Hinweise  
 Das [icordebugvariablehomeenum](icordebugvariablehomeenum-interface.md) -Schnittstellen Objekt ist ein Standard-Enumerator, der von der Schnittstelle "ICorDebugEnum" abgeleitet ist und die das Auflisten von [icordebugvariablehome](icordebugvariablehome-interface.md) -Objekten ermöglicht. Die Auflistung enthält möglicherweise mehrere [icorentbugvariablehome](icordebugvariablehome-interface.md) -Objekte für denselben Slot-oder Argument Index, wenn Sie an unterschiedlichen Punkten in der Funktion unterschiedliche Haushalte haben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugCode4-Schnittstelle](icordebugcode4-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
