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
ms.openlocfilehash: 5f83cb96e39b257a1d35786130cd5ed31d071de7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443869"
---
# <a name="corattributetargets-enumeration"></a>CorAttributeTargets-Enumeration
Gibt die Anwendungselemente an, auf die ein Attribut angewendet werden kann.  
  
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
|`catAssembly`|Das Attribut kann auf eine Assembly angewendet werden.|  
|`catModule`|Das Attribut kann auf ein ausführbares ausführbares ausführbares Modul (. dll oder. exe) angewendet werden.|  
|`catClass`|Das Attribut kann auf eine Klasse angewendet werden.|  
|`catStruct`|Das Attribut kann auf eine Struktur angewendet werden. Das heißt, ein Werttyp.|  
|`catEnum`|Das Attribut kann auf eine Enumeration angewendet werden.|  
|`catConstructor`|Das Attribut kann auf einen Konstruktor angewendet werden.|  
|`catMethod`|Das Attribut kann auf eine Methode angewendet werden.|  
|`catProperty`|Das Attribut kann auf eine Eigenschaft angewendet werden.|  
|`catField`|Das Attribut kann auf ein Feld angewendet werden.|  
|`catEvent`|Das Attribut kann auf ein Ereignis angewendet werden.|  
|`catInterface`|Das Attribut kann auf eine Schnittstelle angewendet werden.|  
|`catParameter`|Das Attribut kann auf einen Parameter angewendet werden.|  
|`catDelegate`|Das Attribut kann auf einen Delegaten angewendet werden.|  
|`catGenericParameter`|Das Attribut kann auf einen generischen Parameter angewendet werden.|  
|`catAll`|Das Attribut kann auf ein beliebiges Anwendungs Element angewendet werden.|  
|`catClassMembers`|Das Attribut kann auf einen Member einer Klasse angewendet werden.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CorAttributeTargets` Enumerationswerte können mit einer bitweisen OR-Operation kombiniert werden, um die bevorzugte Kombination zu erhalten.  
  
 Der `CorAttributeTargets` der die verwaltete <xref:System.AttributeTargets?displayProperty=nameWithType>-Enumeration entspricht.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Corhdr. h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
