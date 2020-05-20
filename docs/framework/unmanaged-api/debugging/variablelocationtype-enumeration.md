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
ms.openlocfilehash: 455fd06dbdbfd5d9753f3d7270647a742751d804
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420655"
---
# <a name="variablelocationtype-enumeration"></a>VariableLocationType-Enumeration
Gibt den Typ des systemeigenen Standorts einer Variablen an.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,
    VLT_REGISTER_RELATIVE,
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`VLT_REGISTER`|Die Variable befindet sich in einem Register.|  
|`VLT_REGISTER_RELATIVE`|Die Variable befindet sich in einer Register-relativen Speicheradresse.|  
|`VLT_INVALID`|Die Variable wird nicht in einer Register-oder Register-relativen Speicheradresse gespeichert.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Member der- `VariableLocationType` Enumeration wird von der [icordebugvariablehome:: getlocationtype](icordebugvariablehome-getlocationtype-method.md) -Methode zurückgegeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debugenumerationen](debugging-enumerations.md)
