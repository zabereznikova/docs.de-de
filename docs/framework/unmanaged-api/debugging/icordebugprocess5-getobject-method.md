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
ms.openlocfilehash: 540ca78c5548d4fbdd3338671ea02314736f15cd
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792367"
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
  
## <a name="parameters"></a>Parameters  
 `addr`  
 in Die Objekt Adresse.  
  
 `ppObject`  
 vorgenommen Ein Zeiger auf die Adresse eines ICorDebugObjectValue-Objekts.  
  
## <a name="remarks"></a>Hinweise  
 Wenn `addr` nicht auf ein gültiges verwaltetes Objekt zeigt, gibt die `GetObject`-Methode `E_FAIL`zurück.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugProcess5-Schnittstelle](icordebugprocess5-interface.md)
- [Debuggen von Schnittstellen](debugging-interfaces.md)
