---
title: IDefinitionAppId-Schnittstelle
ms.date: 03/30/2017
api_name:
- IDefinitionAppId
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionAppId
helpviewer_keywords:
- IDefinitionAppId interface [.NET Framework fusion]
ms.assetid: e72f2550-bdec-4a20-a2f4-2e14847266c1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5bd705ef549de3a8018efe731ef8735ef7b6b915
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59083178"
---
# <a name="idefinitionappid-interface"></a>IDefinitionAppId-Schnittstelle
Stellt einen eindeutigen Bezeichner für den Code, der die Anwendung im aktuellen Bereich definiert.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|Ruft eine formatierte Zeichenfolge, die den Code in diesem darstellt `IDefinitionAppId` Objekt.|  
|`IDefinitionAppId::put_Codebase`|Legt den Code dieser `IDefinitionAppId` Objekt, das das angegebene formatierte Zeichenfolgenwert.|  
|`IDefinitionAppId::EnumAppPath`|Ruft einen Schnittstellenzeiger auf ein [IEnumDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md) Objekt, das die Assemblys in den Pfad der aktuellen Anwendung enthält.|  
|`IDefinitionAppId::SetAppPath`|Legt den Anwendungspfad für die Assembly im aktuellen Bereich auf den verwiesen wird, mit dem angegebenen Wert [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) Objekt.|  
|`IDefinitionAppId::get_SubscriptionId`|Ruft einen Zeiger in eine Zeichenfolgendarstellung der token-ID für ein Abonnement für diese `IDefinitionAppId` Objekt.|  
|`IDefinitionAppId::put_SubscriptionId`|Legt den Bezeichner für ein Abonnement zu diesem `IDefinitionAppId` Objekt, das den angegebenen Zeichenfolgenwert.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Isolation.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Fusion-Schnittstellen](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
