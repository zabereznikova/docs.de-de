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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9fb1dff80fccc920540d370797441b3a019d766c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780910"
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
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`catAssembly`|Attribut kann auf eine Assembly angewendet werden.|  
|`catModule`|Attribut kann auf ein portierbare ausführbare Datei (.dll oder .exe) Modul angewendet werden.|  
|`catClass`|Attribut kann auf eine Klasse angewendet werden.|  
|`catStruct`|Auf einer Struktur können Attribute angewendet werden; Typ, d. h. ein Wert.|  
|`catEnum`|Attribut kann auf eine Enumeration angewendet werden.|  
|`catConstructor`|Attribut kann an einen Konstruktor angewendet werden.|  
|`catMethod`|Attribut kann auf eine Methode angewendet werden.|  
|`catProperty`|Attribut kann auf eine Eigenschaft angewendet werden.|  
|`catField`|Attribut kann auf ein Feld angewendet werden.|  
|`catEvent`|Attribut kann auf ein Ereignis angewendet werden.|  
|`catInterface`|Attribut kann auf eine Schnittstelle angewendet werden.|  
|`catParameter`|Attribut kann auf einen Parameter angewendet werden.|  
|`catDelegate`|In einen Delegaten können Attribute angewendet werden.|  
|`catGenericParameter`|Attribut kann auf einen generischen Parameter angewendet werden.|  
|`catAll`|Auf jedes Anwendungselement kann Attribute angewendet werden.|  
|`catClassMembers`|Attribut kann auf einen Member einer Klasse angewendet werden.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CorAttributeTargets` Enumerationswerte können kombiniert werden, mit der eine bitweise OR-Operation, um die gewünschte Kombination zu erhalten.  
  
 Die `CorAttributeTargets` gleicht die verwaltete <xref:System.AttributeTargets?displayProperty=nameWithType> Enumeration.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorHdr.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
