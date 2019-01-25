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
ms.openlocfilehash: fb97c545d2d57ef589b5a7a5b3618eaa2b6f364f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54686997"
---
# <a name="idefinitionidentity-interface"></a>IDefinitionIdentity-Schnittstelle
Stellt die eindeutige Signatur des Codes, der die Anwendung im aktuellen Bereich definiert.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|Ruft einen Schnittstellenzeiger zu einem neuen `IDefinitionIdentity` -Objekt, das identisch ist `IDefinitionIdentity`, mit Ausnahme der angegebenen Attribut ändert.|  
|`IDefinitionIdentity::EnumAttributes`|Ruft einen Schnittstellenzeiger auf ein [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md) Objekt, das die zugeordneten Attributen enthält `IDefinitionIdentity`.|  
|`IDefinitionIdentity::GetAttribute`|Ruft den Wert des Attributs mit dem angegebenen Namen im angegebenen Namespace ab.|  
|`IDefinitionIdentity::SetAttribute`|Legt das Attribut mit dem angegebenen Namen im angegebenen Namespace mit dem angegebenen Wert fest.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Isolation.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Fusion-Schnittstellen](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
