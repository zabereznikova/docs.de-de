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
ms.openlocfilehash: 2289a9a75311c9642a764844ee466adcc5838655
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54744348"
---
# <a name="ireferenceappid-interface"></a>IReferenceAppId-Schnittstelle
Stellt einen Verweis auf den eindeutigen Bezeichner für die Anwendung im aktuellen Bereich.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|Ruft einen Zeiger auf eine Zeichenfolgendarstellung der Bezeichner für die Anwendung auf die dieses `IReferenceAppId`.|  
|`IReferenceAppId::put_CodeBase`|Den Bezeichner für die Anwendung auf die dieses legt `IReferenceAppId`.|  
|`IReferenceAppId::EnumAppPath`|Ruft einen Schnittstellenzeiger auf ein `IEnumReferenceIdentity` Instanz mit der `IReferenceIdentity` Instanzen, die Member dieser darstellen `IReferenceAppId`.|  
|`IReferenceAppId::get_SubscriptionId`|Ruft einen Zeiger in eine Zeichenfolgendarstellung der token-ID für ein Abonnement für diese `IReferenceAppId`.|  
|`IReferenceAppId::put_SubscriptionId`|Legt den Bezeichner für ein Abonnement zu diesem `IReferenceAppId` auf den angegebenen Zeichenfolgenwert.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Isolation.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Fusion-Schnittstellen](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [IEnumReferenceIdentity-Schnittstelle](../../../../docs/framework/unmanaged-api/fusion/ienumreferenceidentity-interface.md)
- [IReferenceIdentity-Schnittstelle](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
