---
title: IReferenceIdentity-Schnittstelle
ms.date: 03/30/2017
api_name:
- IReferenceIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IReferenceIdentity
helpviewer_keywords:
- IReferenceIdentity interface [.NET Framework fusion]
ms.assetid: 9180ac5a-7019-4716-9f83-8a91d157239a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2bb151d7c77104d8e24acefaac2e1f109b67f168
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796355"
---
# <a name="ireferenceidentity-interface"></a>IReferenceIdentity-Schnittstelle
Stellt einen Verweis auf die eindeutige Signatur eines Code Objekts dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|`IReferenceIdentity::Clone`|Ruft einen Schnittstellen Zeiger auf eine neue `IReferenceIdentity` -Instanz ab, die mit `IReferenceIdentity`dieser identisch ist, mit Ausnahme der angegebenen Attribut Änderungen.|  
|`IReferenceIdentity::EnumAttributes`|Ruft einen Schnittstellen Zeiger auf eine `IEnumIDENTITY_ATTRIBUTE` -Instanz ab, die die diesem `IReferenceIdentity`zugeordneten Attribute enthält.|  
|`IReferenceIdentity::GetAttribute`|Ruft den Wert des Attributs im angegebenen Namespace mit dem angegebenen Namen ab.|  
|`IReferenceIdentity::SetAttribute`|Legt das Attribut mit dem angegebenen Namespace und dem angegebenen Namen auf den angegebenen Wert fest.|  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Isolation. h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Fusion-Schnittstellen](fusion-interfaces.md)
- [IEnumIDENTITY_ATTRIBUTE-Schnittstelle](ienumidentity-attribute-interface.md)
