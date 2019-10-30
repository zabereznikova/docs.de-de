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
ms.openlocfilehash: 6f20fb2e9e026253fb02b47dfcd63cf655acc4ee
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131648"
---
# <a name="ireferenceappid-interface"></a>IReferenceAppId-Schnittstelle
Stellt einen Verweis auf den eindeutigen Bezeichner für die Anwendung im aktuellen Gültigkeitsbereich dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|Ruft einen Zeiger auf eine Zeichen folgen Darstellung des Code Bezeichners für die Anwendung ab, auf die von diesem `IReferenceAppId`verwiesen wird.|  
|`IReferenceAppId::put_CodeBase`|Legt den Code Bezeichner für die Anwendung fest, auf die von diesem `IReferenceAppId`verwiesen wird.|  
|`IReferenceAppId::EnumAppPath`|Ruft einen Schnittstellen Zeiger auf eine `IEnumReferenceIdentity`-Instanz ab, die die `IReferenceIdentity`-Instanzen enthält, die Elemente dieser `IReferenceAppId`darstellen.|  
|`IReferenceAppId::get_SubscriptionId`|Ruft einen Zeiger auf eine Zeichen folgen Darstellung des Tokenbezeichners für ein Abonnement für dieses `IReferenceAppId`ab.|  
|`IReferenceAppId::put_SubscriptionId`|Legt den Tokenbezeichner für ein Abonnement dieses `IReferenceAppId` auf den angegebenen Zeichen folgen Wert fest.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Isolation. h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Fusion-Schnittstellen](fusion-interfaces.md)
- [IEnumReferenceIdentity-Schnittstelle](ienumreferenceidentity-interface.md)
- [IReferenceIdentity-Schnittstelle](ireferenceidentity-interface.md)
