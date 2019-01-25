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
ms.openlocfilehash: e4da0e064f507e2330aac27fc5c8bcd56b9d3c1b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54716231"
---
# <a name="createasmnameobjflags-enumeration"></a>CREATE_ASM_NAME_OBJ_FLAGS-Enumeration
Gibt die Attribute einer [IAssemblyName-Schnittstelle](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) -Objekt nach der Erstellung durch die [CreateAssemblyNameObject](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md) Funktion.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
|`CANOF_PARSE_DISPLAY_NAME`|Gibt an, dass der übergebene Parameter eine Text Identität ist.|  
|`CANOF_SET_DEFAULT_VALUES`|Einige Standardwerte festgelegt.|  
|`CANOF_VERIFY_FRIEND_ASSEMBLYNAME`|Überprüft die Friend-Assembly-Regel (nur Name und öffentlicher Schlüssel). Dieser Member ist nur zur internen Verwendung.|  
|`CANOF_PARSE_FRIEND_DISPLAY_NAME`|Eine Kombination aus den `CANOF_PARSE_DISPLAY_NAME` und `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` Flags. Dieser Member ist nur zur internen Verwendung.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Fusion.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [IAssemblyName-Schnittstelle](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [CreateAssemblyNameObject-Funktion](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md)
- [Fusion-Enumerationen](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
