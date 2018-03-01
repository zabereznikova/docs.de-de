---
title: IIdentityAuthority-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IIdentityAuthority
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IIdentityAuthority
helpviewer_keywords:
- IIdentityAuthority interface [.NET Framework fusion]
ms.assetid: 6277f914-51a8-49be-bec6-52d6d648527d
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 322b15252271472b5bee1dfc6a843079cebbe0b8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iidentityauthority-interface"></a>IIdentityAuthority-Schnittstelle
Verwaltet die Identitätsschlüssel für Codeobjekte.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|`IIdentityAuthority::AreDefinitionsEqual`|Ruft einen Wert, der angibt, ob die beiden angegebenen [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) Instanzen gleich sind.|  
|`IIdentityAuthority::AreReferencesEqual`|Ruft einen Wert, der angibt, ob die beiden angegebenen [IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md) Instanzen gleich sind.|  
|`IIdentityAuthority::AreTextualDefinitionsEqual`|Ruft einen Wert, der angibt, ob die beiden angegebenen Zeichenfolge Definition Identity Darstellungen gleich sind.|  
|`IIdentityAuthority::AreTextualReferencesEqual`|Ruft einen Wert, der angibt, ob die beiden angegebenen Zeichenfolge Verweis Identität Darstellungen gleich sind.|  
|`IIdentityAuthority::CreateDefinition`|Ruft einen Zeiger auf ein neues `IDefinitionIdentity` Instanz, die das Codeobjekt im aktuellen Bereich darstellt.|  
|`IIdentityAuthority::CreateReference`|Ruft einen Zeiger auf ein neues `IReferenceIdentity` Instanz, die das Codeobjekt im aktuellen Bereich darstellt.|  
|`IIdentityAuthority::DefinitionToText`|Ruft eine formatierte Zeichenfolge-Version des angegebenen `IDefinitionIdentity`.|  
|`IIdentityAuthority::DefinitionToTextBuffer`|Füllt den angegebenen Breitzeichenpuffer mit eine Zeichenfolgenversion des angegebenen `IDefinitionIdentity`.|  
|`IIdentityAuthority::DoesDefinitionMatchReference`|Ruft einen Wert, der angibt, ob das angegebene `IDefinitionIdentity` und `IReferenceIdentity` Instanzen auf demselben Codeobjekt verweisen.|  
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|Ruft einen Wert, der angibt, ob die angegebenen Zeichenfolgen auf dasselbe Codeobjekt verweisen.|  
|`IIdentityAuthority::GenerateDefinitionKey`|Ruft einen Zeiger auf einen neu erstellten Zeichenfolgenschlüssel für die angegebene `IDefinitionIdentity`.|  
|`IIdentityAuthority::GenerateReferenceKey`|Ruft einen Zeiger auf einen neu erstellten Zeichenfolgenschlüssel für die angegebene `IReferenceIdentity`.|  
|`IIdentityAuthority::HashDefinition`|Ruft einen Hashwert für den angegebenen `IDefinitionIdentity`.|  
|`IIdentityAuthority::HashReference`|Ruft einen Hashwert für den angegebenen `IreferenceIdentity`.|  
|`IIdentityAuthority::ReferenceToText`|Ruft eine formatierte Zeichenfolge-Version des angegebenen `IReferenceIdentity`.|  
|`IIdentityAuthority::ReferenceToTextBuffer`|Füllt den angegebenen Breitzeichenpuffer mit eine Zeichenfolgenversion des angegebenen `IReferenceIdentity`.|  
|`IIdentityAuthority::TextToDefinition`|Ruft einen Schnittstellenzeiger auf eine `IDefinitionIdentity` generiert aus der angegebenen Instanz formatierte Zeichenfolge.|  
|`IIdentityAuthority::TextToReference`|Ruft einen Schnittstellenzeiger auf eine `IReferenceIdentity` generiert aus der angegebenen Instanz formatierte Zeichenfolge.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Isolation.h  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Fusion-Schnittstellen](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
