---
title: CorValidatorModuleType-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorValidatorModuleType
api_location: mscoree.dll
api_type: COM
f1_keywords: CorValidatorModuleType
helpviewer_keywords: CorValidatorModuleType enumeration [.NET Framework metadata]
ms.assetid: 748f1ab2-fbcb-4f55-89ec-8d23d81ebc80
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3367f6928b5d7378b2686185ee3e03d0279cc11d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
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
|`ValidatorModuleTypeMin`|Der Minimalwert der der `CorValidatorModuleType` Enum.|  
|`ValidatorModuleTypePE`|Das Modul ist eine PE (portable Executable)-Datei.|  
|`ValidatorModuleTypeObj`|Das Modul ist eine OBJ-Datei.|  
|`ValidatorModuleTypeEnc`|Das Modul ist eine Debugsitzung mit bearbeiten und fortfahren.|  
|`ValidatorModuleTypeIncr`|Das Modul ist eine, die inkrementell erstellt wurde.|  
|`ValidatorModuleTypeMax`|Der Maximalwert der der `CorValidatorModuleType` Enum.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
