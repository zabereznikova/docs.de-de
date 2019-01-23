---
title: CorMethodAttr-Enumeration
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1a69ca889e226168adb1b84ab64dc0f882c27606
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54520531"
---
# <a name="cormethodattr-enumeration"></a>CorMethodAttr-Enumeration
Enthält Werte, die die Funktionen einer Methode zu beschreiben.  
  
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
|`mdPrivateScope`|Gibt an, dass der Member nicht verwiesen werden kann.|  
|`mdPrivate`|Gibt an, dass der Member nur von den übergeordneten Typ zugegriffen werden kann.|  
|`mdFamANDAssem`|Gibt an, dass der Member von Untertypen in dieser Assembly nur zugegriffen werden kann.|  
|`mdAssem`|Gibt an, dass der Member Zugriff von jedem Benutzer in der Assembly.|  
|`mdFamily`|Gibt an, dass der Member nur von Typen und Untertypen zugegriffen werden kann.|  
|`mdFamORAssem`|Gibt an, dass der Member von abgeleiteten Klassen und andere Typen in der Assembly verfügbar ist.|  
|`mdPublic`|Gibt an, dass der Member von allen Typen mit Zugriff auf den Bereich zugegriffen werden kann.|  
|`mdStatic`|Gibt an, dass der Member nicht als Mitglied einer Instanz, sondern als Teil des Typs definiert ist.|  
|`mdFinal`|Gibt an, dass die Methode nicht überschrieben werden kann.|  
|`mdVirtual`|Gibt an, dass die Methode überschrieben werden kann.|  
|`mdHideBySig`|Gibt an, dass die Methode durch den Namen und derselben Signatur und nicht nur durch den Namen verbirgt.|  
|`mdVtableLayoutMask`|Gibt die virtuellen Tabellenlayout.|  
|`mdReuseSlot`|Gibt an, dass der Slot für diese Methode in der virtuellen Tabelle verwendete wiederverwendet werden. Dies ist die Standardeinstellung.|  
|`mdNewSlot`|Gibt an, dass die Methode immer einen neuen Slot in der virtuellen Tabelle abruft.|  
|`mdCheckAccessOnOverride`|Gibt an, dass die Methode von den Typen überschrieben werden kann, zu dem es angezeigt wird.|  
|`mdAbstract`|Gibt an, dass die Methode nicht implementiert wird.|  
|`mdSpecialName`|Gibt an, dass besondere Methode handelt und der Name wird beschrieben, wie.|  
|`mdPinvokeImpl`|Gibt an, dass die methodenimplementierung mit PInvoke weitergeleitet wird.|  
|`mdUnmanagedExport`|Gibt an, dass die Methode eine verwaltete Methode, die in nicht verwaltetem Code exportiert.|  
|`mdReservedMask`|Durch die common Language Runtime können Sie für die interne Verwendung reserviert.|  
|`mdRTSpecialName`|Gibt an, dass die common Language Runtime die Codierung des Methodennamens überprüfen soll.|  
|`mdHasSecurity`|Gibt an, dass die Methode Sicherheitsfunktionen zugeordnet.|  
|`mdRequireSecObject`|Gibt an, dass die Methode, eine andere Methode aufruft, die Sicherheitscode enthält.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorHdr.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
