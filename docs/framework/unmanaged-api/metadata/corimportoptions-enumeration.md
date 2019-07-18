---
title: CorImportOptions-Enumeration
ms.date: 03/30/2017
api_name:
- CorImportOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorImportOptions
helpviewer_keywords:
- CorImportOptions enumeration [.NET Framework metadata]
ms.assetid: 4e5d03cb-97c9-4ff4-8dbd-17d94ee374d3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 38c0937804eb82d1c96a605b55a00784ba58fe13
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781826"
---
# <a name="corimportoptions-enumeration"></a>CorImportOptions-Enumeration
Enthält Flagwerte, die das Verhalten beim Import einer Assembly außerhalb des aktuellen Bereichs steuern.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
|`MDImportOptionDefault`|Gibt an, das Standardverhalten, das gelöschte Datensätze übersprungen wird.|  
|`MDImportOptionAll`|Gibt an, dass alle Metadaten, die aufgelistet werden sollen.|  
|`MDImportOptionAllTypeDefs`|Gibt an, dass alle TypeDefs, einschließlich der gelöschten, aufgelistet werden sollen.|  
|`MDImportOptionAllMethodDefs`|Gibt an, dass alle MethodDefs, einschließlich der gelöschten, aufgelistet werden sollen.|  
|`MDImportOptionAllFieldDefs`|Gibt an, dass alle FieldDefs, einschließlich der gelöschten, aufgelistet werden sollen.|  
|`MDImportOptionAllProperties`|Gibt an, dass alle PropertyDefs, einschließlich der gelöschten, aufgelistet werden sollen.|  
|`MDImportOptionAllEvents`|Gibt an, dass alle EventDefs, einschließlich der gelöschten, aufgelistet werden sollen.|  
|`MDImportOptionAllCustomAttributes`|Gibt an, dass alle benutzerdefinierten Attribute, einschließlich der gelöschten, aufgelistet werden sollen.|  
|`MDImportOptionAllExportedTypes`|Gibt an, dass alle exportierte Typen, einschließlich der gelöschten, aufgelistet werden sollen.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorHdr.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
