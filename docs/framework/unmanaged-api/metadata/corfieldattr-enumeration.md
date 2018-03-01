---
title: CorFieldAttr-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b5128ea59f7668737885835723156fc7f1786872
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
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
|`fdFieldAccessMask`|Gibt Informationen über Eingabehilfen an.|  
|`fdPrivateScope`|Gibt an, dass auf das Feld nicht verwiesen werden kann.|  
|`fdPrivate`|Gibt an, dass das Feld nur einen übergeordneten Typ zugänglich ist.|  
|`fdFamANDAssem`|Gibt an, dass das Feld von abgeleiteten Klassen in seiner Assembly zugegriffen werden kann.|  
|`fdAssembly`|Gibt an, dass das Feld von allen Typen in seiner Assembly zugegriffen werden kann.|  
|`fdFamily`|Gibt an, dass das Feld nur anhand des Typs zugegriffen werden kann und Klassen abgeleitete.|  
|`fdFamORAssem`|Gibt an, dass das Feld von abgeleiteten Klassen und alle Typen in seiner Assembly zugegriffen werden.|  
|`fdPublic`|Gibt an, dass das Feld alle Typen mit Sichtbarkeit dieses Bereichs zugänglich ist.|  
|`fdStatic`|Gibt an, dass das Feld ein Member dieses Typs statt einen Instanzmember ist.|  
|`fdInitOnly`|Gibt an, dass das Feld nach der Initialisierung nicht geändert werden kann.|  
|`fdLiteral`|Gibt an, dass der Wert des Felds eine Kompilierzeitkonstante.|  
|`fdNotSerialized`|Gibt an, dass das Feld nicht serialisiert wird, wenn dessen Typ Remote ausgeführt wird.|  
|`fdSpecialName`|Gibt an, dass das Feld besondere und seinen Namen wird beschrieben, wie.|  
|`fdPinvokeImpl`|Gibt an, dass die Implementierung des Felds über PInvoke weitergeleitet wird.|  
|`fdReservedMask`|Reserviert für interne Verwendung durch die common Language Runtime.|  
|`fdRTSpecialName`|Gibt an, dass die common Language Runtime-Metadaten über interne APIs überprüfen soll, die die Codierung des Namens.|  
|`fdHasFieldMarshal`|Gibt an, dass das Feld Marshallinginformationen enthält.|  
|`fdHasDefault`|Gibt an, dass das Feld einen Standardwert besitzt.|  
|`fdHasFieldRVA`|Gibt an, dass das Feld eine relative virtuelle Adresse verfügt.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorHdr.h  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
