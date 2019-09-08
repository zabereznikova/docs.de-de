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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7421e0d0e1a1f0e1a5fbe0d0eb7d5a0ab2a48b9a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796424"
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
|`IIdentityAuthority::CreateDefinition`|Ruft einen Zeiger auf eine neue `IDefinitionIdentity` -Instanz ab, die das Code Objekt im aktuellen Bereich darstellt.|
|`IIdentityAuthority::CreateReference`|Ruft einen Zeiger auf eine neue `IReferenceIdentity` -Instanz ab, die das Code Objekt im aktuellen Bereich darstellt.|
|`IIdentityAuthority::DefinitionToText`|Ruft eine formatierte Zeichen folgen Version des `IDefinitionIdentity`angegebenen ab.|
|`IIdentityAuthority::DefinitionToTextBuffer`|Füllt den angegebenen breit Zeichen Puffer mit einer Zeichen folgen Version des angegebenen `IDefinitionIdentity`aus.|
|`IIdentityAuthority::DoesDefinitionMatchReference`|Ruft einen Wert ab, der angibt, `IDefinitionIdentity` ob `IReferenceIdentity` die angegebene-Instanz und die-Instanz auf dasselbe Code Objekt verweisen.|
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|Ruft einen Wert ab, der angibt, ob die angegebenen Zeichen folgen auf dasselbe Code Objekt verweisen.|
|`IIdentityAuthority::GenerateDefinitionKey`|Ruft einen Zeiger auf einen neu erstellten Zeichen folgen Schlüssel für den `IDefinitionIdentity`angegebenen ab.|
|`IIdentityAuthority::GenerateReferenceKey`|Ruft einen Zeiger auf einen neu erstellten Zeichen folgen Schlüssel für den `IReferenceIdentity`angegebenen ab.|
|`IIdentityAuthority::HashDefinition`|Ruft einen Hashwert für den angegebenen `IDefinitionIdentity`ab.|
|`IIdentityAuthority::HashReference`|Ruft einen Hashwert für den angegebenen `IReferenceIdentity`ab.|
|`IIdentityAuthority::ReferenceToText`|Ruft eine formatierte Zeichen folgen Version des `IReferenceIdentity`angegebenen ab.|
|`IIdentityAuthority::ReferenceToTextBuffer`|Füllt den angegebenen breit Zeichen Puffer mit einer Zeichen folgen Version des angegebenen `IReferenceIdentity`aus.|
|`IIdentityAuthority::TextToDefinition`|Ruft einen Schnittstellen Zeiger auf eine `IDefinitionIdentity` Instanz ab, die aus der angegebenen formatierten Zeichenfolge generiert wurde.|
|`IIdentityAuthority::TextToReference`|Ruft einen Schnittstellen Zeiger auf eine `IReferenceIdentity` Instanz ab, die aus der angegebenen formatierten Zeichenfolge generiert wurde.|

## <a name="requirements"></a>Anforderungen

**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

**Header:** Isolation. h

**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Siehe auch

- [Fusion-Schnittstellen](fusion-interfaces.md)
