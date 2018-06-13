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
ms.openlocfilehash: 819afec2c448e5f396ab54e2dde00c01da310b12
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433749"
---
# <a name="iappidauthority-interface"></a>IAppIdAuthority-Schnittstelle
Stellt Methoden, die zum Generieren und Vergleichen von Schlüsseln für Anwendungsidentitäten und Verweise.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|Ruft einen Wert, der angibt, ob die beiden angegebenen [IDefinitionAppId](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md) Instanzen gleich sind. Sie können den Flagwert IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION übergeben, damit die jeweiligen Versionsinformationen ignorieren übergeben.|  
|`IAppIdAuthority::AreReferencesEqual`|Ruft einen Wert, der angibt, ob die beiden angegebenen [IReferenceAppId](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md) Instanzen gleich sind. Sie können den Flagwert IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION übergeben, damit die jeweiligen Versionsinformationen ignorieren übergeben.|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|Ruft einen Wert, der angibt, ob die beiden Definitionen für die angegebene Zeichenfolge gleich sind. Sie können den Flagwert IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION übergeben, damit die jeweiligen Versionsinformationen ignorieren übergeben.|  
|`IAppIdAuthority::AreTextualReferencesEqual`|Ruft einen Wert, der angibt, ob die beiden angegebenen Zeichenfolgenverweise gleich sind. Sie können den Flagwert IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION übergeben, damit die jeweiligen Versionsinformationen ignorieren übergeben.|  
|`IAppIdAuthority::CreateDefinition`|Ruft einen Schnittstellenzeiger auf eine neu generierte `IDefinitionAppId` Instanz, die die Assembly im aktuellen Bereich darstellt.|  
|`IAppIdAuthority::CreateReference`|Ruft einen Schnittstellenzeiger auf eine neu erstellte `IReferenceAppId` , die die Assembly im aktuellen Bereich darstellt.|  
|`IAppIdAuthority::DefinitionToText`|Ruft eine Zeichenfolgenversion des angegebenen `IDefinitionAppId`, mit der angegebenen Flagwerte.|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|Ruft einen Wert, der angibt, ob das angegebene `IDefinitionAppId` und `IReferenceAppId` dieselbe Assembly darstellen.|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|Ruft einen Wert, der angibt, ob die angegebene parameterdefinitions-Zeichenfolge und der Verweiszeichenfolge dieselbe Assembly darstellen.|  
|`IAppIdAuthority::GenerateDefinitionKey`|Ruft einen Zeichenfolgenschlüssel, der dem angegebenen darstellt `IDefinitionAppId` Instanz.|  
|`IAppIdAuthority::GenerateReferenceKey`|Ruft einen Zeichenfolgenschlüssel, der dem angegebenen darstellt `IReferenceAppId` Instanz.|  
|`IAppIdAuthority::HashDefinition`|Ruft einen Hash-Schlüssel für den angegebenen `IDefinitionAppId` Instanz.|  
|`IAppIdAuthority::HashReference`|Ruft einen Hash-Schlüssel für den angegebenen `IReferenceAppId` Instanz.|  
|`IAppIdAuthority::ReferenceToText`|Ruft eine Zeichenfolgenversion des angegebenen `IReferenceAppId`, mit der angegebenen Flagwerte.|  
|`IAppIdAuthority::TextToDefinition`|Ruft einen Schnittstellenzeiger auf eine `IDefinitionAppId` Instanz, die die Assembly verwiesen wird, durch den Schlüssel für die angegebene Zeichenfolge darstellt.|  
|`IAppIdAuthority::TextToReference`|Ruft einen Schnittstellenzeiger auf eine `IReferenceAppId` Instanz, die die Assembly verwiesen wird, durch den Schlüssel für die angegebene Zeichenfolge darstellt.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Isolation.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Fusion-Schnittstellen](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
