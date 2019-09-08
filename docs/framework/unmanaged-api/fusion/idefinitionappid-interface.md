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
ms.openlocfilehash: 929909a7f2c4fa1799c8fed94787b8f853c7eac2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796517"
---
# <a name="idefinitionappid-interface"></a>IDefinitionAppId-Schnittstelle
Stellt einen eindeutigen Bezeichner für den Code dar, der die Anwendung im aktuellen Gültigkeitsbereich definiert.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|Ruft eine formatierte Zeichenfolge ab, die den `IDefinitionAppId` Code in diesem-Objekt darstellt.|  
|`IDefinitionAppId::put_Codebase`|Legt den Code dieses `IDefinitionAppId` Objekts auf den angegebenen formatierten Zeichen folgen Wert fest.|  
|`IDefinitionAppId::EnumAppPath`|Ruft einen Schnittstellen Zeiger auf ein [IEnumDefinitionIdentity](ienumdefinitionidentity-interface.md) -Objekt ab, das die Assemblys im aktuellen Anwendungspfad enthält.|  
|`IDefinitionAppId::SetAppPath`|Legt den Anwendungspfad für die Assembly im aktuellen Gültigkeitsbereich auf den Wert fest, auf den vom angegebenen [IDefinitionIdentity](idefinitionidentity-interface.md) -Objekt verwiesen wird.|  
|`IDefinitionAppId::get_SubscriptionId`|Ruft einen Zeiger auf eine Zeichen folgen Darstellung des Tokenbezeichners für ein Abonnement `IDefinitionAppId` für dieses-Objekt ab.|  
|`IDefinitionAppId::put_SubscriptionId`|Legt den Tokenbezeichner für ein Abonnement `IDefinitionAppId` für dieses-Objekt auf den angegebenen Zeichen folgen Wert fest.|  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Isolation. h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Fusion-Schnittstellen](fusion-interfaces.md)
