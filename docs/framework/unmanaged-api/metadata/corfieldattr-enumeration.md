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
ms.openlocfilehash: d28a0c8b7ee85f023026dde6f3cc8f3a8406aa64
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450312"
---
# <a name="corfieldattr-enumeration"></a>CorFieldAttr-Enumeration
Enthält Werte, die die Metadaten über ein Feld beschreiben.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
  
## <a name="members"></a>Mitglieder  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`fdFieldAccessMask`|Gibt Barrierefreiheits Informationen an.|  
|`fdPrivateScope`|Gibt an, dass auf das Feld nicht verwiesen werden kann.|  
|`fdPrivate`|Gibt an, dass auf das Feld nur über den übergeordneten Typ zugegriffen werden kann.|  
|`fdFamANDAssem`|Gibt an, dass abgeleitete Klassen in der Assembly auf das Feld zugreifen.|  
|`fdAssembly`|Gibt an, dass auf das Feld für alle Typen in der Assembly zugegriffen werden kann.|  
|`fdFamily`|Gibt an, dass auf das Feld nur über den Typ und die abgeleiteten Klassen zugegriffen werden kann.|  
|`fdFamORAssem`|Gibt an, dass auf das Feld von abgeleiteten Klassen und von allen Typen in der Assembly zugegriffen werden kann.|  
|`fdPublic`|Gibt an, dass auf das Feld alle Typen mit Sichtbarkeit dieses Bereichs zugreifen kann.|  
|`fdStatic`|Gibt an, dass das Feld ein Member seines Typs und kein Instanzmember ist.|  
|`fdInitOnly`|Gibt an, dass das Feld nicht geändert werden kann, nachdem es initialisiert wurde.|  
|`fdLiteral`|Gibt an, dass der Feldwert eine Kompilierzeit Konstante ist.|  
|`fdNotSerialized`|Gibt an, dass das Feld nicht serialisiert wird, wenn der Typ Remote ist.|  
|`fdSpecialName`|Gibt an, dass es sich um ein spezielles Feld handelt und wie der Name beschreibt.|  
|`fdPinvokeImpl`|Gibt an, dass die Feld Implementierung über PInvoke weitergeleitet wird.|  
|`fdReservedMask`|Reserviert für die interne Verwendung durch den Common Language Runtime.|  
|`fdRTSpecialName`|Gibt an, dass die Common Language Runtime Metadaten-internen APIs die Codierung des Namens überprüfen sollen.|  
|`fdHasFieldMarshal`|Gibt an, dass das Feld Marshallinginformationen enthält.|  
|`fdHasDefault`|Gibt an, dass das Feld einen Standardwert besitzt.|  
|`fdHasFieldRVA`|Gibt an, dass das Feld über eine relative virtuelle Adresse verfügt.|  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Corhdr. h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
