---
title: IDefinitionIdentity-Schnittstelle
ms.date: 03/30/2017
api_name:
- IDefinitionIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionIdentity
helpviewer_keywords:
- IDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: ce5ba888-5fbe-4efd-91cf-f0ff94d8428b
topic_type:
- apiref
ms.openlocfilehash: 4f08fbbf9c8be16dff092327713e731c5aa14661
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732871"
---
# <a name="idefinitionidentity-interface"></a>IDefinitionIdentity-Schnittstelle

Stellt die eindeutige Signatur des Codes dar, der die Anwendung im aktuellen Gültigkeitsbereich definiert.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|Ruft einen Schnittstellen Zeiger auf ein neues-Objekt ab, `IDefinitionIdentity` das mit diesem identisch ist `IDefinitionIdentity` , mit Ausnahme der angegebenen Attribut Änderungen.|  
|`IDefinitionIdentity::EnumAttributes`|Ruft einen Schnittstellen Zeiger auf ein [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md) -Objekt ab, das die diesem zugeordneten Attribute enthält `IDefinitionIdentity` .|  
|`IDefinitionIdentity::GetAttribute`|Ruft den Wert des Attributs mit dem angegebenen Namen im angegebenen Namespace ab.|  
|`IDefinitionIdentity::SetAttribute`|Legt das Attribut mit dem angegebenen Namen im angegebenen Namespace auf den angegebenen Wert fest.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Isolation. h  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Fusion-Schnittstellen](fusion-interfaces.md)
