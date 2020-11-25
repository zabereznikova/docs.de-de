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
ms.openlocfilehash: 867c09caa3bd3aed50de21c2ef91a02782830be2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704551"
---
# <a name="ireferenceidentity-interface"></a>IReferenceIdentity-Schnittstelle

Stellt einen Verweis auf die eindeutige Signatur eines Code Objekts dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|`IReferenceIdentity::Clone`|Ruft einen Schnittstellen Zeiger auf eine neue-Instanz ab, die mit `IReferenceIdentity` dieser identisch ist `IReferenceIdentity` , mit Ausnahme der angegebenen Attribut Änderungen.|  
|`IReferenceIdentity::EnumAttributes`|Ruft einen Schnittstellen Zeiger auf eine- `IEnumIDENTITY_ATTRIBUTE` Instanz ab, die die diesem zugeordneten Attribute enthält `IReferenceIdentity` .|  
|`IReferenceIdentity::GetAttribute`|Ruft den Wert des Attributs im angegebenen Namespace mit dem angegebenen Namen ab.|  
|`IReferenceIdentity::SetAttribute`|Legt das Attribut mit dem angegebenen Namespace und dem angegebenen Namen auf den angegebenen Wert fest.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Isolation. h  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Fusion-Schnittstellen](fusion-interfaces.md)
- [IEnumIDENTITY_ATTRIBUTE-Schnittstelle](ienumidentity-attribute-interface.md)
