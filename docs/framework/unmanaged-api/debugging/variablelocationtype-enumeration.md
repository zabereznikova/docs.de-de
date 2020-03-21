---
title: VariableLocationType-Enumeration
ms.date: 03/30/2017
api_name:
- VariableLocationType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- VariableLocationType
helpviewer_keywords:
- VariableLocationType enumeration [.NET Framework debugging]
ms.assetid: 8635ee3a-c84b-4626-876c-416bee54f787
topic_type:
- apiref
ms.openlocfilehash: e2fa5d5a998f51e0e90cfde22b40ec12f278307b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178363"
---
# <a name="variablelocationtype-enumeration"></a>VariableLocationType-Enumeration
Gibt den systemeigenen Positionstyp einer Variablen an.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,
    VLT_REGISTER_RELATIVE,
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a>Members  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`VLT_REGISTER`|Die Variable befindet sich in einem Register.|  
|`VLT_REGISTER_RELATIVE`|Die Variable befindet sich an einem registerrelativen Speicherspeicherort.|  
|`VLT_INVALID`|Die Variable wird nicht in einem Register oder einem registerrelativen Speicherspeicherort gespeichert.|  
  
## <a name="remarks"></a>Bemerkungen  
 Ein Member `VariableLocationType` der Enumeration wird von der [ICorDebugVariableHome::GetLocationType-Methode](icordebugvariablehome-getlocationtype-method.md) zurückgegeben.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debuggen von Enumerationen](debugging-enumerations.md)
