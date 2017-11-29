---
title: IReferenceAppId-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IReferenceAppId
api_location: fusion.dll
api_type: COM
f1_keywords: IReferenceAppId
helpviewer_keywords: IReferenceAppId interface [.NET Framework fusion]
ms.assetid: 8eb9e565-f358-43ce-900e-a8f8a5aa6cfb
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cac4ef63292f1bd342bb94799872b002fdcdf945
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Fusion-Schnittstellen](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [IEnumReferenceIdentity-Schnittstelle](../../../../docs/framework/unmanaged-api/fusion/ienumreferenceidentity-interface.md)  
 [IReferenceIdentity-Schnittstelle](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
