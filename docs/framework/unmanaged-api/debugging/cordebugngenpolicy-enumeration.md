---
title: CorDebugNGenPolicy-Enumeration
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugNGenPolicy
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugNGenPolicy
helpviewer_keywords:
- CorDebugNgenPolicy enumeration [.NET Framework debugging]
ms.assetid: edb4e4d2-3166-44d4-8b17-bf302f7ea093
topic_type:
- apiref
ms.openlocfilehash: b64de0fa2ecbddd2decf69a4099d9897ec42a563
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696426"
---
# <a name="cordebugngenpolicy-enumeration"></a>CorDebugNGenPolicy-Enumeration

Stellt einen Wert bereit, der bestimmt, ob ein Debugger systemeigene Abbilder (NGen) aus dem Cache für systemeigene Abbilder lädt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
enum CorDebugNGENPolicy {  
    DISABLE_LOCAL_NIC = 1  
} CorDebugNGENPolicy;  
```  
  
## <a name="members"></a>Member  
  
|Membername|BESCHREIBUNG|  
|-----------------|-----------------|  
|`DISABLE_LOCAL_NIC`|In einer Windows 8. x Store-App wird die Verwendung von Images aus dem lokalen Cache für Native Images deaktiviert. In einer Desktop-App hat diese Einstellung keine Auswirkungen.|  
  
## <a name="remarks"></a>Hinweise  

 Die- `CorDebugNGENPolicy` Enumeration wird von der [ICorDebugProcess5:: enablengenpolicy](icordebugprocess5-enablengenpolicy-method.md) -Methode verwendet. Das Deaktivieren der Verwendung von Bildern aus dem lokalen Cache für systemeigene Images sorgt für ein konsistentes Debuggen, indem sichergestellt wird, dass der Debugger Debugfähige JIT-kompilierte Images anstelle von optimierten systemeigenen Images lädt.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugenumerationen](debugging-enumerations.md)
