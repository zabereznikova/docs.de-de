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
ms.openlocfilehash: 6c3e721c24da217eaf2e8857377359e1c51b7b59
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677011"
---
# <a name="cormethodattr-enumeration"></a>CorMethodAttr-Enumeration

Enthält Werte, die die Funktionen einer Methode beschreiben.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`mdMemberAccessMask`|Gibt den Element Zugriff an.|  
|`mdPrivateScope`|Gibt an, dass auf den Member nicht verwiesen werden kann.|  
|`mdPrivate`|Gibt an, dass der Zugriff auf den Member nur über den übergeordneten Typ möglich ist.|  
|`mdFamANDAssem`|Gibt an, dass nur Untertypen in dieser Assembly auf den Member zugreifen kann.|  
|`mdAssem`|Gibt an, dass der Member von allen Personen in der Assembly zugänglich ist.|  
|`mdFamily`|Gibt an, dass auf den Member nur nach Typ und Untertypen zugegriffen werden kann.|  
|`mdFamORAssem`|Gibt an, dass auf den Member durch abgeleitete Klassen und andere Typen in der Assembly zugegriffen werden kann.|  
|`mdPublic`|Gibt an, dass der Zugriff auf den Member für alle Typen mit Zugriff auf den Bereich möglich ist.|  
|`mdStatic`|Gibt an, dass der Member als Teil des Typs und nicht als Member einer Instanz definiert wird.|  
|`mdFinal`|Gibt an, dass die Methode nicht überschrieben werden kann.|  
|`mdVirtual`|Gibt an, dass die Methode überschrieben werden kann.|  
|`mdHideBySig`|Gibt an, dass die Methode nach Name und Signatur und nicht nur nach Namen ausgeblendet wird.|  
|`mdVtableLayoutMask`|Gibt das Layout der virtuellen Tabelle an.|  
|`mdReuseSlot`|Gibt an, dass der für diese Methode in der virtuellen Tabelle verwendete Slot wieder verwendet werden soll. Dies ist die Standardoption.|  
|`mdNewSlot`|Gibt an, dass die Methode immer einen neuen Slot in der virtuellen Tabelle erhält.|  
|`mdCheckAccessOnOverride`|Gibt an, dass die Methode von denselben Typen überschrieben werden kann, auf die Sie sichtbar ist.|  
|`mdAbstract`|Gibt an, dass die Methode nicht implementiert ist.|  
|`mdSpecialName`|Gibt an, dass die Methode speziell ist, und dass Ihr Name beschreibt, wie.|  
|`mdPinvokeImpl`|Gibt an, dass die Methoden Implementierung mithilfe von PInvoke weitergeleitet wird.|  
|`mdUnmanagedExport`|Gibt an, dass die Methode eine verwaltete Methode ist, die in nicht verwalteten Code exportiert wird.|  
|`mdReservedMask`|Reserviert für die interne Verwendung durch den Common Language Runtime.|  
|`mdRTSpecialName`|Gibt an, dass die Common Language Runtime die Codierung des Methoden namens überprüfen soll.|  
|`mdHasSecurity`|Gibt an, dass der Methode Sicherheit zugeordnet ist.|  
|`mdRequireSecObject`|Gibt an, dass die Methode eine andere Methode aufruft, die Sicherheitscode enthält.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Corhdr. h  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Metadatenenumerationen](metadata-enumerations.md)
