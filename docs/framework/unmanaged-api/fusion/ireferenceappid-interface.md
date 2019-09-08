---
title: IReferenceAppId-Schnittstelle
ms.date: 03/30/2017
api_name:
- IReferenceAppId
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IReferenceAppId
helpviewer_keywords:
- IReferenceAppId interface [.NET Framework fusion]
ms.assetid: 8eb9e565-f358-43ce-900e-a8f8a5aa6cfb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 522ed80f161f114af25e1fa7ad041c8238073d6f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796372"
---
# <a name="ireferenceappid-interface"></a>IReferenceAppId-Schnittstelle
Stellt einen Verweis auf den eindeutigen Bezeichner für die Anwendung im aktuellen Gültigkeitsbereich dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|Ruft einen Zeiger auf eine Zeichen folgen Darstellung des Code Bezeichners für die Anwendung ab, `IReferenceAppId`auf die von verwiesen wird.|  
|`IReferenceAppId::put_CodeBase`|Legt den Code Bezeichner für die Anwendung fest, `IReferenceAppId`auf die von verwiesen wird.|  
|`IReferenceAppId::EnumAppPath`|Ruft einen Schnittstellen Zeiger auf eine `IEnumReferenceIdentity` -Instanz ab `IReferenceIdentity` , die die-Instanzen enthält `IReferenceAppId`, die Elemente dieser darstellen.|  
|`IReferenceAppId::get_SubscriptionId`|Ruft einen Zeiger auf eine Zeichen folgen Darstellung des Tokenbezeichners für ein Abonnement `IReferenceAppId`für dieses ab.|  
|`IReferenceAppId::put_SubscriptionId`|Legt den Tokenbezeichner für ein Abonnement `IReferenceAppId` auf den angegebenen Zeichen folgen Wert fest.|  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Isolation. h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Fusion-Schnittstellen](fusion-interfaces.md)
- [IEnumReferenceIdentity-Schnittstelle](ienumreferenceidentity-interface.md)
- [IReferenceIdentity-Schnittstelle](ireferenceidentity-interface.md)
