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
ms.openlocfilehash: 3be8a004be752af8a8675a3499bdb6cbfd785840
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009196"
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
|`MDImportOptionDefault`|Gibt das Standardverhalten an, das zum Überspringen gelöschter Datensätze dient.|  
|`MDImportOptionAll`|Gibt an, dass alle Metadaten aufgezählt werden sollen.|  
|`MDImportOptionAllTypeDefs`|Gibt an, dass alle Typedefs, einschließlich gelöschter Typen, aufgelistet werden sollen.|  
|`MDImportOptionAllMethodDefs`|Gibt an, dass alle methoddefs, einschließlich der gelöschten, aufgezählt werden sollen.|  
|`MDImportOptionAllFieldDefs`|Gibt an, dass alle FieldDefs, einschließlich gelöschter, aufgezählt werden sollen.|  
|`MDImportOptionAllProperties`|Gibt an, dass alle PropertyDefs, einschließlich gelöschter Werte, aufgelistet werden sollen.|  
|`MDImportOptionAllEvents`|Gibt an, dass alle EventDefs, einschließlich der gelöschten, aufgezählt werden sollen.|  
|`MDImportOptionAllCustomAttributes`|Gibt an, dass alle benutzerdefinierten Attribute, einschließlich gelöschter Attribute, aufgezählt werden sollen.|  
|`MDImportOptionAllExportedTypes`|Gibt an, dass alle exportierten Typen, einschließlich gelöschter Typen, aufgezählt werden sollen.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Corhdr. h  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](metadata-enumerations.md)
