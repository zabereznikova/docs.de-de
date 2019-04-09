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
ms.openlocfilehash: dd46ea26532074c9ea42da4d07a38ed583aad076
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220161"
---
# <a name="ireferenceidentity-interface"></a>IReferenceIdentity-Schnittstelle
Stellt einen Verweis auf die eindeutige Signatur ein Codeobjekt dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|`IReferenceIdentity::Clone`|Ruft einen Schnittstellenzeiger zu einem neuen `IReferenceIdentity` -Instanz, die identisch ist `IReferenceIdentity`, mit Ausnahme der angegebenen Attribut ändert.|  
|`IReferenceIdentity::EnumAttributes`|Ruft einen Schnittstellenzeiger auf ein `IEnumIDENTITY_ATTRIBUTE` -Instanz, die mit diesem verknüpften Attribute enthält `IReferenceIdentity`.|  
|`IReferenceIdentity::GetAttribute`|Ruft den Wert des Attributs im angegebenen Namespace, mit dem angegebenen Namen ab.|  
|`IReferenceIdentity::SetAttribute`|Legt das Attribut mit dem angegebenen Namespace und dem angegebenen Namen auf den angegebenen Wert fest.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Isolation.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Fusion-Schnittstellen](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [IEnumIDENTITY_ATTRIBUTE-Schnittstelle](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)
