---
title: IAppIdAuthority-Schnittstelle
ms.date: 03/30/2017
api_name:
- IAppIdAuthority
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAppIdAuthority
helpviewer_keywords:
- IAppIdAuthority interface [.NET Framework fusion]
ms.assetid: ec354fa1-1efd-41b0-bc43-b90597b6e253
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c803169f87c4033d7e231e8b0243f502b9246f70
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54493923"
---
# <a name="iappidauthority-interface"></a>IAppIdAuthority-Schnittstelle
Stellt Methoden, die zum Generieren und Vergleichen von Schlüsseln für Anwendungsidentitäten und Verweise bereit.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|Ruft einen Wert, der angibt, ob die beiden angegebenen [IDefinitionAppId](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md) -Instanzen gleich sind. Sie können den Flagwert IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION übergeben, damit ihre jeweiligen Versionsinformationen ignorieren übergeben.|  
|`IAppIdAuthority::AreReferencesEqual`|Ruft einen Wert, der angibt, ob die beiden angegebenen [IReferenceAppId](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md) -Instanzen gleich sind. Sie können den Flagwert IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION übergeben, damit ihre jeweiligen Versionsinformationen ignorieren übergeben.|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|Ruft einen Wert, der angibt, ob die beiden Definitionen für die angegebene Zeichenfolge gleich sind. Sie können den Flagwert IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION übergeben, damit ihre jeweiligen Versionsinformationen ignorieren übergeben.|  
|`IAppIdAuthority::AreTextualReferencesEqual`|Ruft einen Wert, der angibt, ob die beiden Verweise für die angegebene Zeichenfolge gleich sind. Sie können den Flagwert IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION übergeben, damit ihre jeweiligen Versionsinformationen ignorieren übergeben.|  
|`IAppIdAuthority::CreateDefinition`|Ruft einen Schnittstellenzeiger auf einem neu generierten `IDefinitionAppId` -Instanz, die die Assembly im aktuellen Bereich darstellt.|  
|`IAppIdAuthority::CreateReference`|Ruft einen Schnittstellenzeiger zu einer neu erstellten `IReferenceAppId` , die die Assembly im aktuellen Bereich darstellt.|  
|`IAppIdAuthority::DefinitionToText`|Ruft eine Zeichenfolgenversion des angegebenen `IDefinitionAppId`, mit den Werten des angegebenen Flags.|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|Ruft einen Wert, der angibt, ob das angegebene `IDefinitionAppId` und `IReferenceAppId` dieselbe Assembly darstellen.|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|Ruft einen Wert, der angibt, ob die angegebenen parameterdefinitions-Zeichenfolge und die Verweiszeichenfolge wird die gleiche Assembly darstellen.|  
|`IAppIdAuthority::GenerateDefinitionKey`|Ruft einen Zeichenfolgenschlüssel, der dem angegebenen darstellt `IDefinitionAppId` Instanz.|  
|`IAppIdAuthority::GenerateReferenceKey`|Ruft einen Zeichenfolgenschlüssel, der dem angegebenen darstellt `IReferenceAppId` Instanz.|  
|`IAppIdAuthority::HashDefinition`|Ruft einen Hash-Schlüssel für den angegebenen `IDefinitionAppId` Instanz.|  
|`IAppIdAuthority::HashReference`|Ruft einen Hash-Schlüssel für den angegebenen `IReferenceAppId` Instanz.|  
|`IAppIdAuthority::ReferenceToText`|Ruft eine Zeichenfolgenversion des angegebenen `IReferenceAppId`, mit den Werten des angegebenen Flags.|  
|`IAppIdAuthority::TextToDefinition`|Ruft einen Schnittstellenzeiger auf ein `IDefinitionAppId` -Instanz, die die Assembly verwiesen wird, durch den Schlüssel für die angegebene Zeichenfolge darstellt.|  
|`IAppIdAuthority::TextToReference`|Ruft einen Schnittstellenzeiger auf ein `IReferenceAppId` -Instanz, die die Assembly verwiesen wird, durch den Schlüssel für die angegebene Zeichenfolge darstellt.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Isolation.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Fusion-Schnittstellen](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
