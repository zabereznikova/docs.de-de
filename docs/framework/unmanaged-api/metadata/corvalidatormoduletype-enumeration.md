---
title: CorValidatorModuleType-Enumeration
ms.date: 03/30/2017
api_name:
- CorValidatorModuleType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorValidatorModuleType
helpviewer_keywords:
- CorValidatorModuleType enumeration [.NET Framework metadata]
ms.assetid: 748f1ab2-fbcb-4f55-89ec-8d23d81ebc80
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 14eee096c25967d321e4693b260501827d944a80
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045174"
---
# <a name="corvalidatormoduletype-enumeration"></a>CorValidatorModuleType-Enumeration
Gibt den Typ eines Moduls.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef enum  
{  
    ValidatorModuleTypeInvalid  = 0x0,  
    ValidatorModuleTypeMin      = 0x00000001,  
    ValidatorModuleTypePE       = 0x00000001,  
    ValidatorModuleTypeObj      = 0x00000002,  
    ValidatorModuleTypeEnc      = 0x00000003,  
    ValidatorModuleTypeIncr     = 0x00000004,  
    ValidatorModuleTypeMax      = 0x00000004  
} CorValidatorModuleType;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`ValidatorModuleTypeInvalid`|Das Modul ist ein ungültiger Typ.|  
|`ValidatorModuleTypeMin`|Der minimale Wert des der `CorValidatorModuleType` Enum.|  
|`ValidatorModuleTypePE`|Das Modul ist eine Datei (portable Executable)-Datei.|  
|`ValidatorModuleTypeObj`|Das Modul ist eine OBJ-Datei.|  
|`ValidatorModuleTypeEnc`|Das Modul ist eine Debugsitzung mit bearbeiten und fortfahren.|  
|`ValidatorModuleTypeIncr`|Das Modul ist ein, die inkrementell erstellt wurde.|  
|`ValidatorModuleTypeMax`|Der maximale Wert, der die `CorValidatorModuleType` Enum.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
