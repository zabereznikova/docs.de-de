---
title: ICorDebugProcess5::GetTypeLayout-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeLayout
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeLayout
helpviewer_keywords:
- ICorDebugProcess5::GetTypeLayout method [.NET Framework debugging]
- GetTypeLayout method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: bd62f5d1-e874-41f1-81e5-a29a7572c15d
topic_type:
- apiref
ms.openlocfilehash: 32277e8adcd4bb08c8d0480eb3b4e7e4b5949479
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723128"
---
# <a name="icordebugprocess5gettypelayout-method"></a>ICorDebugProcess5::GetTypeLayout-Methode

Ruft Informationen über das Layout eines Objekts im Arbeitsspeicher auf Grundlage des Typbezeichners ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetTypeLayout(    [in] COR_TYPEID id,     [out] COR_TYPE_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a>Parameter  

 `id`  
 in Ein [COR_TYPEID](cor-typeid-structure.md) Token, das den Typ angibt, dessen Layout gewünscht ist.  
  
 `pLayout`  
 vorgenommen Ein Zeiger auf eine [COR_TYPE_LAYOUT](cor-type-layout-structure.md) -Struktur, die Informationen über das Layout des-Objekts im Arbeitsspeicher enthält.  
  
## <a name="remarks"></a>Hinweise  

 Die- `ICorDebugProcess5::GetTypeLayout` Methode stellt Informationen zu einem-Objekt auf der Grundlage des [COR_TYPEID](cor-typeid-structure.md)bereit, das von einer Reihe anderer [ICorDebugProcess5](icordebugprocess5-interface.md) -Methoden zurückgegeben wird. Die Informationen werden von einer [COR_TYPE_LAYOUT](cor-type-layout-structure.md) Struktur bereitgestellt, die von der-Methode aufgefüllt wird.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [COR_TYPE_LAYOUT-Struktur](cor-type-layout-structure.md)
- [ICorDebugProcess5-Schnittstelle](icordebugprocess5-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
