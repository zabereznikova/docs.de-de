---
title: CorImportOptions-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorImportOptions
api_location: mscoree.dll
api_type: COM
f1_keywords: CorImportOptions
helpviewer_keywords: CorImportOptions enumeration [.NET Framework metadata]
ms.assetid: 4e5d03cb-97c9-4ff4-8dbd-17d94ee374d3
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e9af7bbb6dd7cfa488f72ec99f9cfd848f04e72f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="corimportoptions-enumeration"></a>CorImportOptions-Enumeration
Enthält Flagwerte, die das Verhalten beim Import einer Assembly außerhalb des aktuellen Bereichs steuern.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef enum CorImportOptions {  
  
    MDImportOptionDefault                = 0x00000000,  
    MDImportOptionAll                    = 0xFFFFFFFF,  
    MDImportOptionAllTypeDefs            = 0x00000001,  
    MDImportOptionAllMethodDefs          = 0x00000002,  
    MDImportOptionAllFieldDefs           = 0x00000004,  
    MDImportOptionAllProperties          = 0x00000008,  
    MDImportOptionAllEvents              = 0x00000010,  
    MDImportOptionAllCustomAttributes    = 0x00000020,  
    MDImportOptionAllExportedTypes       = 0x00000040  
  
} CorImportOptions;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`MDImportOptionDefault`|Gibt an, das Standardverhalten, d. h. gelöschten Datensätze übersprungen.|  
|`MDImportOptionAll`|Gibt an, dass alle Metadaten aufgelistet werden sollen.|  
|`MDImportOptionAllTypeDefs`|Gibt an, dass alle TypeDefs, auch die gelöschten, aufgelistet werden sollen.|  
|`MDImportOptionAllMethodDefs`|Gibt an, dass alle MethodDefs, auch die gelöschten, aufgelistet werden sollen.|  
|`MDImportOptionAllFieldDefs`|Gibt an, dass alle FieldDefs, auch die gelöschten, aufgelistet werden sollen.|  
|`MDImportOptionAllProperties`|Gibt an, dass alle PropertyDefs, auch die gelöschten, aufgelistet werden sollen.|  
|`MDImportOptionAllEvents`|Gibt an, dass alle EventDefs, auch die gelöschten, aufgelistet werden sollen.|  
|`MDImportOptionAllCustomAttributes`|Gibt an, dass alle benutzerdefinierten Attribute, einschließlich der gelöschten, aufgelistet werden sollen.|  
|`MDImportOptionAllExportedTypes`|Gibt an, dass alle exportierte Typen, einschließlich der gelöschten, aufgelistet werden sollen.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorHdr.h  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
