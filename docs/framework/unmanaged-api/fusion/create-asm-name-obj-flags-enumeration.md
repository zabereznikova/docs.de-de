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
ms.openlocfilehash: 52d5ad3a18c102422e90621c7d1e23b2692c0000
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683230"
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
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`CANOF_PARSE_DISPLAY_NAME`|Gibt an, dass der übergebenen Parameter eine Text Identität ist.|  
|`CANOF_SET_DEFAULT_VALUES`|Legt einige Standardwerte fest.|  
|`CANOF_VERIFY_FRIEND_ASSEMBLYNAME`|Überprüft die Friend-Assemblyregel (nur Name und öffentlicher Schlüssel). Dieser Member ist nur für die interne Verwendung vorgesehen.|  
|`CANOF_PARSE_FRIEND_DISPLAY_NAME`|Eine Kombination der `CANOF_PARSE_DISPLAY_NAME` -und- `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` Flags. Dieser Member ist nur für die interne Verwendung vorgesehen.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Fusion. h  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IAssemblyName-Schnittstelle](iassemblyname-interface.md)
- [CreateAssemblyNameObject-Funktion](createassemblynameobject-function.md)
- [Fusionsenumerationen](fusion-enumerations.md)
