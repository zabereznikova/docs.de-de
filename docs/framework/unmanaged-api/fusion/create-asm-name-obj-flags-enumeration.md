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
ms.openlocfilehash: ee856dbd398d0fa5e3eee7d9b2b2cfc7c7a57ecf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176590"
---
# <a name="create_asm_name_obj_flags-enumeration"></a>CREATE_ASM_NAME_OBJ_FLAGS-Enumeration
Gibt die Attribute eines [IAssemblyName](iassemblyname-interface.md) Interface-Objekts an, wenn es von der [Funktion CreateAssemblyNameObject](createassemblynameobject-function.md) erstellt wird.  
  
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
  
## <a name="members"></a>Members  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`CANOF_PARSE_DISPLAY_NAME`|Gibt an, dass es sich bei dem übergebenen Parameter um eine Textidentität handelt.|  
|`CANOF_SET_DEFAULT_VALUES`|Legt einige Standardwerte fest.|  
|`CANOF_VERIFY_FRIEND_ASSEMBLYNAME`|Überprüft die Friend-Assemblyregel (nur Name und öffentlicher Schlüssel). Dieses Mitglied ist nur für den internen Gebrauch vorgesehen.|  
|`CANOF_PARSE_FRIEND_DISPLAY_NAME`|Eine Kombination `CANOF_PARSE_DISPLAY_NAME` aus `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` und Flags. Dieses Mitglied ist nur für den internen Gebrauch vorgesehen.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Kopfzeile:** Fusion.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IAssemblyName-Schnittstelle](iassemblyname-interface.md)
- [CreateAssemblyNameObject-Funktion](createassemblynameobject-function.md)
- [Fusionsenumerationen](fusion-enumerations.md)
