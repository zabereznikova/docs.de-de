---
title: ICorDebugProcess5::GetObject-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetObject
helpviewer_keywords:
- GetObject method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetObject method [.NET Framework debugging]
ms.assetid: c8111502-5a20-447f-9dc2-76e8acd7ed5a
topic_type:
- apiref
ms.openlocfilehash: ff2913399e1dbeb33bbfb697058db3caf2a8d1fb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713105"
---
# <a name="icordebugprocess5getobject-method"></a>ICorDebugProcess5::GetObject-Methode

Konvertiert eine Objekt Adresse in ein ICorDebugObjectValue-Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetObject(  
    [in] CORDB_ADDRESS addr,
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `addr`  
 in Die Objekt Adresse.  
  
 `ppObject`  
 vorgenommen Ein Zeiger auf die Adresse eines ICorDebugObjectValue-Objekts.  
  
## <a name="remarks"></a>Hinweise  

 Wenn `addr` nicht auf ein gültiges verwaltetes Objekt zeigt, `GetObject` gibt die Methode zurück `E_FAIL` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugProcess5-Schnittstelle](icordebugprocess5-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
