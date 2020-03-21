---
title: CorAttributeTargets-Enumeration
ms.date: 03/30/2017
api_name:
- CorAttributeTargets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorAttributeTargets
helpviewer_keywords:
- CorAttributeTargets enumeration [.NET Framework metadata]
ms.assetid: 694c0fa0-7011-41a9-9dfd-f0e16ea574b5
topic_type:
- apiref
ms.openlocfilehash: 51741aa3a6d965c1e9743081628d8ad62e8fb04e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176200"
---
# <a name="corattributetargets-enumeration"></a>CorAttributeTargets-Enumeration
Gibt die Anwendungselemente an, auf die Attribute angewendet werden können.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum CorAttributeTargets  
{  
    catAssembly            = 0x0001,  
    catModule              = 0x0002,  
    catClass               = 0x0004,  
    catStruct              = 0x0008,  
    catEnum                = 0x0010,  
    catConstructor         = 0x0020,  
    catMethod              = 0x0040,  
    catProperty            = 0x0080,  
    catField               = 0x0100,  
    catEvent               = 0x0200,  
    catInterface           = 0x0400,  
    catParameter           = 0x0800,  
    catDelegate            = 0x1000,  
    catGenericParameter    = 0x4000,  
  
    catAll                 =
        catAssembly | catModule | catClass | catStruct |
        catEnum | catConstructor | catMethod | catProperty |
        catField | catEvent | catInterface | catParameter |
        catDelegate | catGenericParameter,  
  
    catClassMembers        =
        catClass | catStruct | catEnum | catConstructor |
        catMethod | catProperty | catField | catEvent |
        catDelegate | catInterface  
  
} CorAttributeTargets;  
```  
  
## <a name="members"></a>Members  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`catAssembly`|Auf Assemblys können Attribute angewendet werden.|  
|`catModule`|Attribute können auf ein portables ausführbares Modul (.dll oder .exe) angewendet werden.|  
|`catClass`|Auf Klassen können Attribute angewendet werden.|  
|`catStruct`|Auf Strukturen, d. h. auf Werttypen, können Attribute angewendet werden.|  
|`catEnum`|Auf Enumerationen können Attribute angewendet werden.|  
|`catConstructor`|Auf Konstruktoren können Attribute angewendet werden.|  
|`catMethod`|Auf Methoden können Attribute angewendet werden.|  
|`catProperty`|Auf Eigenschaften können Attribute angewendet werden.|  
|`catField`|Auf Felder können Attribute angewendet werden.|  
|`catEvent`|Auf Ereignisse können Attribute angewendet werden.|  
|`catInterface`|Auf Schnittstellen können Attribute angewendet werden.|  
|`catParameter`|Auf Parameter können Attribute angewendet werden.|  
|`catDelegate`|Auf Delegaten können Attribute angewendet werden.|  
|`catGenericParameter`|Auf generische Parameter können Attribute angewendet werden.|  
|`catAll`|Auf jedes Anwendungselement können Attribute angewendet werden.|  
|`catClassMembers`|Attribute können auf einen Member einer Klasse angewendet werden.|  
  
## <a name="remarks"></a>Bemerkungen  
 Die `CorAttributeTargets` Enumerationswerte können mit einem bitweisen ODER-Vorgang kombiniert werden, um die bevorzugte Kombination zu erhalten.  
  
 Die `CorAttributeTargets` Parallelen <xref:System.AttributeTargets?displayProperty=nameWithType> zur verwalteten Enumeration.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** CorHdr.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
