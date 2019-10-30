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
ms.openlocfilehash: 861d5daa481132d3d6527e8d5fbccfab6436c5fe
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139121"
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
 Ein Member der `VariableLocationType` Enumeration wird von der [icordebugvariablehome:: getlocationtype](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md) -Methode zurückgegeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Enumerationen](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
