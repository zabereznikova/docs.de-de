---
title: CorMethodAttr-Enumeration
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
- CorMethodAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodAttr
helpviewer_keywords:
- CorMethodAttr enumeration [.NET Framework metadata]
ms.assetid: 4e0c3521-e54d-43c1-9857-cc76b49b8ffc
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e4e144b64664a149115f3047b98267c2f218a76e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="cormethodattr-enumeration"></a>CorMethodAttr-Enumeration
Enthält Werte, die die Funktionen einer Methode beschreiben.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef enum CorMethodAttr {  
  
    mdMemberAccessMask          =   0x0007,  
    mdPrivateScope              =   0x0000,  
    mdPrivate                   =   0x0001,  
    mdFamANDAssem               =   0x0002,  
    mdAssem                     =   0x0003,  
    mdFamily                    =   0x0004,  
    mdFamORAssem                =   0x0005,  
    mdPublic                    =   0x0006,  
  
    mdStatic                    =   0x0010,  
    mdFinal                     =   0x0020,  
    mdVirtual                   =   0x0040,  
    mdHideBySig                 =   0x0080,  
  
    mdVtableLayoutMask          =   0x0100,  
    mdReuseSlot                 =   0x0000,  
    mdNewSlot                   =   0x0100,  
  
    mdCheckAccessOnOverride     =   0x0200,  
    mdAbstract                  =   0x0400,  
    mdSpecialName               =   0x0800,  
  
    mdPinvokeImpl               =   0x2000,  
    mdUnmanagedExport           =   0x0008,  
  
    mdReservedMask              =   0xd000,  
    mdRTSpecialName             =   0x1000,  
    mdHasSecurity               =   0x4000,  
    mdRequireSecObject          =   0x8000,  
  
} CorMethodAttr;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`mdMemberAccessMask`|Gibt den Memberzugriff.|  
|`mdPrivateScope`|Gibt an, dass das Element verwiesen werden kann.|  
|`mdPrivate`|Gibt an, dass der Member nur von dem übergeordneten Typ zugegriffen werden kann.|  
|`mdFamANDAssem`|Gibt an, dass das Element Untertypen nur in dieser Assembly zugreifen können.|  
|`mdAssem`|Gibt an, dass das Element Zugriff von jedem Benutzer in der Assembly.|  
|`mdFamily`|Gibt an, dass der Member nur von Typ und Untertypen zugegriffen werden kann.|  
|`mdFamORAssem`|Gibt an, dass der Member von abgeleiteten Klassen und anderen Typen in seiner Assembly zugegriffen wird.|  
|`mdPublic`|Gibt an, dass das Element alle Typen mit Zugriff auf den Bereich zugänglich ist.|  
|`mdStatic`|Gibt an, dass der Member als Teil des Typs statt als Mitglied einer Instanz definiert ist.|  
|`mdFinal`|Gibt an, dass die Methode nicht überschrieben werden kann.|  
|`mdVirtual`|Gibt an, dass die Methode überschrieben werden kann.|  
|`mdHideBySig`|Gibt an, dass die Methode, durch den Namen und derselben Signatur statt nur über den Namen ausgeblendet.|  
|`mdVtableLayoutMask`|Gibt die virtuellen Tabellenlayout.|  
|`mdReuseSlot`|Gibt an, dass es sich bei der Slot für diese Methode in der virtuellen Tabelle verwendete wiederverwendet werden. Dies ist die Standardeinstellung.|  
|`mdNewSlot`|Gibt an, dass die Methode immer einen neuen Slot in der virtuellen Tabelle erhält.|  
|`mdCheckAccessOnOverride`|Gibt an, dass die Methode von den gleichen Typen überschrieben werden kann, zu dem er angezeigt wird.|  
|`mdAbstract`|Gibt an, dass die Methode nicht implementiert wird.|  
|`mdSpecialName`|Gibt an, dass die Methode spezielle ist und seinen Namen wird beschrieben, wie.|  
|`mdPinvokeImpl`|Gibt an, dass die Implementierung der Methode mit PInvoke weitergeleitet wird.|  
|`mdUnmanagedExport`|Gibt an, dass die Methode einer verwalteten Methode in nicht verwaltetem Code exportiert.|  
|`mdReservedMask`|Reserviert für interne Verwendung durch die common Language Runtime.|  
|`mdRTSpecialName`|Gibt an, dass die common Language Runtime die Codierung des Methodennamens überprüfen soll.|  
|`mdHasSecurity`|Gibt an, dass die Methode Sicherheit zugeordnet.|  
|`mdRequireSecObject`|Gibt an, dass die Methode, eine andere Methode aufruft, die Sicherheitscode enthält.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorHdr.h  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
