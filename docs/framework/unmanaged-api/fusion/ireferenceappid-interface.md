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
ms.openlocfilehash: 9aa7173d81d84d9080d90b0890769ffeaee6a738
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728614"
---
# <a name="ireferenceappid-interface"></a>IReferenceAppId-Schnittstelle

Stellt einen Verweis auf den eindeutigen Bezeichner für die Anwendung im aktuellen Gültigkeitsbereich dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|Ruft einen Zeiger auf eine Zeichen folgen Darstellung des Code Bezeichners für die Anwendung ab, auf die von verwiesen wird `IReferenceAppId` .|  
|`IReferenceAppId::put_CodeBase`|Legt den Code Bezeichner für die Anwendung fest, auf die von verwiesen wird `IReferenceAppId` .|  
|`IReferenceAppId::EnumAppPath`|Ruft einen Schnittstellen Zeiger auf eine-Instanz ab, `IEnumReferenceIdentity` die die- `IReferenceIdentity` Instanzen enthält, die Elemente dieser darstellen `IReferenceAppId` .|  
|`IReferenceAppId::get_SubscriptionId`|Ruft einen Zeiger auf eine Zeichen folgen Darstellung des Tokenbezeichners für ein Abonnement für dieses ab `IReferenceAppId` .|  
|`IReferenceAppId::put_SubscriptionId`|Legt den Tokenbezeichner für ein Abonnement auf `IReferenceAppId` den angegebenen Zeichen folgen Wert fest.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Isolation. h  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Fusion-Schnittstellen](fusion-interfaces.md)
- [IEnumReferenceIdentity-Schnittstelle](ienumreferenceidentity-interface.md)
- [IReferenceIdentity-Schnittstelle](ireferenceidentity-interface.md)
