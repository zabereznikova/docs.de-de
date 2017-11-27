---
title: IDefinitionAppId-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IDefinitionAppId
api_location: fusion.dll
api_type: COM
f1_keywords: IDefinitionAppId
helpviewer_keywords: IDefinitionAppId interface [.NET Framework fusion]
ms.assetid: e72f2550-bdec-4a20-a2f4-2e14847266c1
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 382c82ff773d0ab1c046fc131fa87a4f74d19ea6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="idefinitionappid-interface"></a>IDefinitionAppId-Schnittstelle
Stellt einen eindeutigen Bezeichner für den Code, der die Anwendung im aktuellen Bereich definiert.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|Ruft eine formatierte Zeichenfolge, die den Code in diesem darstellt `IDefinitionAppId` Objekt.|  
|`IDefinitionAppId::put_Codebase`|Legt den Code dieses `IDefinitionAppId` -Objekts auf den angegebenen formatierten Zeichenfolgenwert.|  
|`IDefinitionAppId::EnumAppPath`|Ruft einen Schnittstellenzeiger auf eine [IEnumDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md) Objekt, das die Assemblys im aktuellen Anwendungspfad enthält.|  
|`IDefinitionAppId::SetAppPath`|Legt den Pfad der Anwendung für die Assembly im aktuellen Bereich auf den verwiesen wird, durch den angegebenen Wert [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) Objekt.|  
|`IDefinitionAppId::get_SubscriptionId`|Ruft einen Zeiger auf eine Zeichenfolgendarstellung der token-ID für ein Abonnement für diese `IDefinitionAppId` Objekt.|  
|`IDefinitionAppId::put_SubscriptionId`|Legt den Bezeichner für ein Abonnement dieser `IDefinitionAppId` Objekt, das den angegebenen Zeichenfolgenwert.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Isolation.h  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Fusion-Schnittstellen](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
