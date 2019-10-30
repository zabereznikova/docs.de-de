---
title: IIdentityAuthority-Schnittstelle
ms.date: 03/30/2017
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
ms.openlocfilehash: 3e2d2335e37ced9139ea44092f10b19566894681
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127092"
---
# <a name="iidentityauthority-interface"></a>IIdentityAuthority-Schnittstelle

Verwaltet Identitätsschlüssel für Code Objekte.

## <a name="methods"></a>Methoden

|Methode|Beschreibung|
|------------|-----------------|
|`IIdentityAuthority::AreDefinitionsEqual`|Ruft einen Wert ab, der angibt, ob die beiden angegebenen [IDefinitionIdentity](idefinitionidentity-interface.md) -Instanzen gleich sind.|
|`IIdentityAuthority::AreReferencesEqual`|Ruft einen Wert ab, der angibt, ob die beiden angegebenen [IReferenceIdentity](ireferenceidentity-interface.md) -Instanzen gleich sind.|
|`IIdentityAuthority::AreTextualDefinitionsEqual`|Ruft einen Wert ab, der angibt, ob die zwei angegebenen Identitäts Darstellungen der Zeichen folgen Definitionen gleich sind.|
|`IIdentityAuthority::AreTextualReferencesEqual`|Ruft einen Wert ab, der angibt, ob die zwei angegebenen Zeichen folgen Verweis-Identitäts Darstellungen gleich sind.|
|`IIdentityAuthority::CreateDefinition`|Ruft einen Zeiger auf eine neue `IDefinitionIdentity`-Instanz ab, die das Code Objekt im aktuellen Bereich darstellt.|
|`IIdentityAuthority::CreateReference`|Ruft einen Zeiger auf eine neue `IReferenceIdentity`-Instanz ab, die das Code Objekt im aktuellen Bereich darstellt.|
|`IIdentityAuthority::DefinitionToText`|Ruft eine formatierte Zeichen folgen Version des angegebenen `IDefinitionIdentity`ab.|
|`IIdentityAuthority::DefinitionToTextBuffer`|Füllt den angegebenen breit Zeichen Puffer mit einer Zeichen folgen Version des angegebenen `IDefinitionIdentity`.|
|`IIdentityAuthority::DoesDefinitionMatchReference`|Ruft einen Wert ab, der angibt, ob die angegebene `IDefinitionIdentity` und `IReferenceIdentity` Instanzen auf dasselbe Code Objekt verweisen.|
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|Ruft einen Wert ab, der angibt, ob die angegebenen Zeichen folgen auf dasselbe Code Objekt verweisen.|
|`IIdentityAuthority::GenerateDefinitionKey`|Ruft einen Zeiger auf einen neu erstellten Zeichen folgen Schlüssel für den angegebenen `IDefinitionIdentity`ab.|
|`IIdentityAuthority::GenerateReferenceKey`|Ruft einen Zeiger auf einen neu erstellten Zeichen folgen Schlüssel für den angegebenen `IReferenceIdentity`ab.|
|`IIdentityAuthority::HashDefinition`|Ruft einen Hashwert für die angegebene `IDefinitionIdentity`ab.|
|`IIdentityAuthority::HashReference`|Ruft einen Hashwert für die angegebene `IReferenceIdentity`ab.|
|`IIdentityAuthority::ReferenceToText`|Ruft eine formatierte Zeichen folgen Version des angegebenen `IReferenceIdentity`ab.|
|`IIdentityAuthority::ReferenceToTextBuffer`|Füllt den angegebenen breit Zeichen Puffer mit einer Zeichen folgen Version des angegebenen `IReferenceIdentity`.|
|`IIdentityAuthority::TextToDefinition`|Ruft einen Schnittstellen Zeiger auf eine `IDefinitionIdentity` Instanz ab, die aus der angegebenen formatierten Zeichenfolge generiert wurde.|
|`IIdentityAuthority::TextToReference`|Ruft einen Schnittstellen Zeiger auf eine `IReferenceIdentity` Instanz ab, die aus der angegebenen formatierten Zeichenfolge generiert wurde.|

## <a name="requirements"></a>Anforderungen

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

**Header:** Isolation. h

**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Siehe auch

- [Fusion-Schnittstellen](fusion-interfaces.md)
