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
ms.openlocfilehash: a344f2ab5d9a7aa92018c47ee7a162cd1721aeb5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732111"
---
# <a name="iappidauthority-interface"></a>IAppIdAuthority-Schnittstelle

Stellt Methoden bereit, die Schlüssel für Anwendungs Identitäten und-Verweise generieren und vergleichen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|Ruft einen Wert ab, der angibt, ob die beiden angegebenen [IDefinitionAppId](idefinitionappid-interface.md) -Instanzen gleich sind. Sie können den Flagwert IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION übergeben, um die jeweiligen Versionsinformationen zu ignorieren.|  
|`IAppIdAuthority::AreReferencesEqual`|Ruft einen Wert ab, der angibt, ob die beiden angegebenen [IReferenceAppId](ireferenceappid-interface.md) -Instanzen gleich sind. Sie können den Flagwert IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION übergeben, um die jeweiligen Versionsinformationen zu ignorieren.|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|Ruft einen Wert ab, der angibt, ob die beiden angegebenen Zeichen folgen Definitionen gleich sind. Sie können den Flagwert IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION übergeben, um die jeweiligen Versionsinformationen zu ignorieren.|  
|`IAppIdAuthority::AreTextualReferencesEqual`|Ruft einen Wert ab, der angibt, ob die beiden angegebenen Zeichen folgen Verweise gleich sind. Sie können den Flagwert IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION übergeben, um die jeweiligen Versionsinformationen zu ignorieren.|  
|`IAppIdAuthority::CreateDefinition`|Ruft einen Schnittstellen Zeiger auf eine neu generierte- `IDefinitionAppId` Instanz ab, die die Assembly im aktuellen Bereich darstellt.|  
|`IAppIdAuthority::CreateReference`|Ruft einen Schnittstellen Zeiger auf eine neu erstellte ab `IReferenceAppId` , die die Assembly im aktuellen Bereich darstellt.|  
|`IAppIdAuthority::DefinitionToText`|Ruft `IDefinitionAppId` mithilfe der angegebenen Flagwerte eine Zeichen folgen Version des angegebenen ab.|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|Ruft einen Wert ab, der angibt, ob der angegebene `IDefinitionAppId` und `IReferenceAppId` die gleiche Assembly darstellen.|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|Ruft einen Wert ab, der angibt, ob die angegebene Definitions Zeichenfolge und die Verweis Zeichenfolge dieselbe Assembly darstellen.|  
|`IAppIdAuthority::GenerateDefinitionKey`|Ruft einen Zeichen folgen Schlüssel ab, der die angegebene- `IDefinitionAppId` Instanz darstellt.|  
|`IAppIdAuthority::GenerateReferenceKey`|Ruft einen Zeichen folgen Schlüssel ab, der die angegebene- `IReferenceAppId` Instanz darstellt.|  
|`IAppIdAuthority::HashDefinition`|Ruft einen Hashwert für die angegebene- `IDefinitionAppId` Instanz ab.|  
|`IAppIdAuthority::HashReference`|Ruft einen Hashwert für die angegebene- `IReferenceAppId` Instanz ab.|  
|`IAppIdAuthority::ReferenceToText`|Ruft `IReferenceAppId` mithilfe der angegebenen Flagwerte eine Zeichen folgen Version des angegebenen ab.|  
|`IAppIdAuthority::TextToDefinition`|Ruft einen Schnittstellen Zeiger auf eine- `IDefinitionAppId` Instanz ab, die die Assembly darstellt, auf die vom angegebenen Zeichen folgen Schlüssel verwiesen wird.|  
|`IAppIdAuthority::TextToReference`|Ruft einen Schnittstellen Zeiger auf eine- `IReferenceAppId` Instanz ab, die die Assembly darstellt, auf die vom angegebenen Zeichen folgen Schlüssel verwiesen wird.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Isolation. h  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Fusion-Schnittstellen](fusion-interfaces.md)
