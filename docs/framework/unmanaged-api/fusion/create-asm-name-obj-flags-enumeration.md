---
title: CREATE_ASM_NAME_OBJ_FLAGS-Enumeration
ms.date: 03/30/2017
api_name:
- CREATE_ASM_NAME_OBJ_FLAGS
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- CREATE_ASM_NAME_OBJ_FLAGS
helpviewer_keywords:
- CREATE_ASM_NAME_OBJ_FLAGS enumeration [.NET Framework fusion]
ms.assetid: a5ed2fd0-c7d2-4603-aaca-5d0caad92675
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9897e396424b9076da8f30c61b5a14cfa9539690
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795418"
---
# <a name="create_asm_name_obj_flags-enumeration"></a>CREATE_ASM_NAME_OBJ_FLAGS-Enumeration
Gibt die Attribute eines [IAssemblyName-Schnittstellen](iassemblyname-interface.md) Objekts an, wenn es von der Funktion " [kreateassemblynameobject](createassemblynameobject-function.md) " erstellt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum {  
  
    CANOF_PARSE_DISPLAY_NAME            = 0x1,  
    CANOF_SET_DEFAULT_VALUES            = 0x2,  
    CANOF_VERIFY_FRIEND_ASSEMBLYNAME    = 0x4,  
    CANOF_PARSE_FRIEND_DISPLAY_NAME     =   
        CANOF_PARSE_DISPLAY_NAME | CANOF_VERIFY_FRIEND_ASSEMBLYNAME  
  
} CREATE_ASM_NAME_OBJ_FLAGS;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`CANOF_PARSE_DISPLAY_NAME`|Gibt an, dass der übergebenen Parameter eine Text Identität ist.|  
|`CANOF_SET_DEFAULT_VALUES`|Legt einige Standardwerte fest.|  
|`CANOF_VERIFY_FRIEND_ASSEMBLYNAME`|Überprüft die Friend-Assemblyregel (nur Name und öffentlicher Schlüssel). Dieser Member ist nur für die interne Verwendung vorgesehen.|  
|`CANOF_PARSE_FRIEND_DISPLAY_NAME`|Eine Kombination der `CANOF_PARSE_DISPLAY_NAME` - `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` und-Flags. Dieser Member ist nur für die interne Verwendung vorgesehen.|  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Fusion. h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IAssemblyName-Schnittstelle](iassemblyname-interface.md)
- [CreateAssemblyNameObject-Funktion](createassemblynameobject-function.md)
- [Fusion-Enumerationen](fusion-enumerations.md)
