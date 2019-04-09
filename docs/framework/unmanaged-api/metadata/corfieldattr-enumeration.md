---
title: CorFieldAttr-Enumeration
ms.date: 03/30/2017
api_name:
- CorFieldAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFieldAttr
helpviewer_keywords:
- CorFieldAttr enumeration [.NET Framework metadata]
ms.assetid: 6ae2c4be-212c-4e74-9288-40a11dc26522
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 432e202eb8db105e8d56d3d36cdc8001bac5320c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182376"
---
# <a name="corfieldattr-enumeration"></a>CorFieldAttr-Enumeration
Enthält Werte, die die Metadaten über ein Feld beschreiben.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef enum CorFieldAttr {  
  
    fdFieldAccessMask           =   0x0007,  
    fdPrivateScope              =   0x0000,  
    fdPrivate                   =   0x0001,  
    fdFamANDAssem               =   0x0002,  
    fdAssembly                  =   0x0003,  
    fdFamily                    =   0x0004,  
    fdFamORAssem                =   0x0005,  
    fdPublic                    =   0x0006,  
  
    fdStatic                    =   0x0010,  
    fdInitOnly                  =   0x0020,  
    fdLiteral                   =   0x0040,  
    fdNotSerialized             =   0x0080,  
  
    fdSpecialName               =   0x0200,  
  
    fdPinvokeImpl               =   0x2000,  
  
    fdReservedMask              =   0x9500,  
    fdRTSpecialName             =   0x0400,  
    fdHasFieldMarshal           =   0x1000,  
    fdHasDefault                =   0x8000,  
    fdHasFieldRVA               =   0x0100  
  
} CorFieldAttr;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`fdFieldAccessMask`|Gibt Informationen zur Barrierefreiheit an.|  
|`fdPrivateScope`|Gibt an, dass auf das Feld nicht verwiesen werden kann.|  
|`fdPrivate`|Gibt an, dass das Feld nur von übergeordneten Typs zugegriffen werden kann.|  
|`fdFamANDAssem`|Gibt an, dass das Feld von abgeleiteten Klassen in seiner Assembly zugegriffen werden kann.|  
|`fdAssembly`|Gibt an, dass das Feld von allen Typen in seiner Assembly zugegriffen werden kann.|  
|`fdFamily`|Gibt an, dass das Feld nur über den Typ ist und den abgeleiteten Klassen.|  
|`fdFamORAssem`|Gibt an, dass das Feld von abgeleiteten Klassen und alle Typen in der Assembly zugegriffen werden.|  
|`fdPublic`|Gibt an, dass das Feld von allen Typen mit Sichtbarkeit dieses Bereichs zugegriffen werden kann.|  
|`fdStatic`|Gibt an, dass das Feld ein Member dieses Typs kein Instanzmember.|  
|`fdInitOnly`|Gibt an, dass das Feld kann nicht geändert werden, nach der Initialisierung.|  
|`fdLiteral`|Gibt an, dass der Wert des Felds eine Kompilierzeitkonstante.|  
|`fdNotSerialized`|Gibt an, dass das Feld nicht serialisiert wird, wenn der Typ Remote übergeben wird.|  
|`fdSpecialName`|Gibt an, dass das Feld spezielle ist und seinen Namen wird beschrieben, wie.|  
|`fdPinvokeImpl`|Gibt an, dass die Feld-Implementierung über PInvoke weitergeleitet wird.|  
|`fdReservedMask`|Durch die common Language Runtime können Sie für die interne Verwendung reserviert.|  
|`fdRTSpecialName`|Gibt an, dass die common Language Runtime-Metadaten über interne APIs überprüfen soll, die die Codierung mit dem Namen.|  
|`fdHasFieldMarshal`|Gibt an, dass das Feld über Marshallinginformationen enthält.|  
|`fdHasDefault`|Gibt an, dass das Feld einen Standardwert besitzt.|  
|`fdHasFieldRVA`|Gibt an, dass das Feld eine relative virtuelle Adresse.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorHdr.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
