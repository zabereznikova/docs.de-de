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
ms.openlocfilehash: 2484fa61c03b95e7cbdb452b92a68a2049701374
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="ireferenceappid-interface"></a>IReferenceAppId-Schnittstelle
Stellt einen Verweis auf den eindeutigen Bezeichner für die Anwendung im aktuellen Bereich.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|Ruft einen Zeiger auf eine Zeichenfolgendarstellung der Bezeichner für die Anwendung auf die verwiesen wird von diesem `IReferenceAppId`.|  
|`IReferenceAppId::put_CodeBase`|Legt den Bezeichner für die Anwendung auf die verwiesen wird von diesem `IReferenceAppId`.|  
|`IReferenceAppId::EnumAppPath`|Ruft einen Schnittstellenzeiger auf eine `IEnumReferenceIdentity` Instanz mit der `IReferenceIdentity` Instanzen, die Mitglieder dieser darstellen `IReferenceAppId`.|  
|`IReferenceAppId::get_SubscriptionId`|Ruft einen Zeiger auf eine Zeichenfolgendarstellung der token-ID für ein Abonnement für diese `IReferenceAppId`.|  
|`IReferenceAppId::put_SubscriptionId`|Legt den Bezeichner für ein Abonnement dieser `IReferenceAppId` auf den Wert der angegebenen Zeichenfolge.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Isolation.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Fusion-Schnittstellen](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [IEnumReferenceIdentity-Schnittstelle](../../../../docs/framework/unmanaged-api/fusion/ienumreferenceidentity-interface.md)  
 [IReferenceIdentity-Schnittstelle](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
