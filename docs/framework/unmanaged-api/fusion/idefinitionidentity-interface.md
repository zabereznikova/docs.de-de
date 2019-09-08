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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 84c595bfdcca84ee43a53e2ea913cc978ae0953e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796523"
---
# <a name="idefinitionidentity-interface"></a>IDefinitionIdentity-Schnittstelle
Stellt die eindeutige Signatur des Codes dar, der die Anwendung im aktuellen Gültigkeitsbereich definiert.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|Ruft einen Schnittstellen Zeiger auf ein neues `IDefinitionIdentity` -Objekt ab, das mit `IDefinitionIdentity`diesem identisch ist, mit Ausnahme der angegebenen Attribut Änderungen.|  
|`IDefinitionIdentity::EnumAttributes`|Ruft einen Schnittstellen Zeiger auf ein [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md) -Objekt ab, das die diesem `IDefinitionIdentity`zugeordneten Attribute enthält.|  
|`IDefinitionIdentity::GetAttribute`|Ruft den Wert des Attributs mit dem angegebenen Namen im angegebenen Namespace ab.|  
|`IDefinitionIdentity::SetAttribute`|Legt das Attribut mit dem angegebenen Namen im angegebenen Namespace auf den angegebenen Wert fest.|  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Isolation. h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Fusion-Schnittstellen](fusion-interfaces.md)
