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
ms.openlocfilehash: 263dc0f9d686440aaa23e359c26db1b4d3d09b1e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57375966"
---
# <a name="iidentityauthority-interface"></a>IIdentityAuthority-Schnittstelle

Verwaltet die Identitätsschlüssel für Codeobjekte.

## <a name="methods"></a>Methoden

|Methode|Beschreibung|
|------------|-----------------|
|`IIdentityAuthority::AreDefinitionsEqual`|Ruft einen Wert, der angibt, ob die beiden angegebenen [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) -Instanzen gleich sind.|
|`IIdentityAuthority::AreReferencesEqual`|Ruft einen Wert, der angibt, ob die beiden angegebenen [IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md) -Instanzen gleich sind.|
|`IIdentityAuthority::AreTextualDefinitionsEqual`|Ruft einen Wert, der angibt, ob zwei angegebene Definition Identity zeichenfolgendarstellungen, die gleich sind.|
|`IIdentityAuthority::AreTextualReferencesEqual`|Ruft einen Wert, der angibt, ob zwei angegebene Verweis Identität zeichenfolgendarstellungen, die gleich sind.|
|`IIdentityAuthority::CreateDefinition`|Ruft einen Zeiger auf ein neues `IDefinitionIdentity` Instanz, die Codeobjekt im aktuellen Bereich darstellt.|
|`IIdentityAuthority::CreateReference`|Ruft einen Zeiger auf ein neues `IReferenceIdentity` Instanz, die Codeobjekt im aktuellen Bereich darstellt.|
|`IIdentityAuthority::DefinitionToText`|Ruft eine formatierte Zeichenfolge-Version des angegebenen `IDefinitionIdentity`.|
|`IIdentityAuthority::DefinitionToTextBuffer`|Füllt den angegebenen Breitzeichen-Puffer mit eine Zeichenfolgenversion des angegebenen `IDefinitionIdentity`.|
|`IIdentityAuthority::DoesDefinitionMatchReference`|Ruft einen Wert, der angibt, ob das angegebene `IDefinitionIdentity` und `IReferenceIdentity` Instanzen auf demselben Codeobjekt verweisen.|
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|Ruft einen Wert, der angibt, ob die angegebenen Zeichenfolgen auf dasselbe Codeobjekt verweisen.|
|`IIdentityAuthority::GenerateDefinitionKey`|Ruft einen Zeiger auf eine neu erstellte Zeichenfolge-Schlüssel für das angegebene `IDefinitionIdentity`.|
|`IIdentityAuthority::GenerateReferenceKey`|Ruft einen Zeiger auf eine neu erstellte Zeichenfolge-Schlüssel für das angegebene `IReferenceIdentity`.|
|`IIdentityAuthority::HashDefinition`|Ruft einen Hashwert für den angegebenen `IDefinitionIdentity`.|
|`IIdentityAuthority::HashReference`|Ruft einen Hashwert für den angegebenen `IReferenceIdentity`.|
|`IIdentityAuthority::ReferenceToText`|Ruft eine formatierte Zeichenfolge-Version des angegebenen `IReferenceIdentity`.|
|`IIdentityAuthority::ReferenceToTextBuffer`|Füllt den angegebenen Breitzeichen-Puffer mit eine Zeichenfolgenversion des angegebenen `IReferenceIdentity`.|
|`IIdentityAuthority::TextToDefinition`|Ruft einen Schnittstellenzeiger auf ein `IDefinitionIdentity` -Instanz, aus dem angegebenen generiert formatierte Zeichenfolge.|
|`IIdentityAuthority::TextToReference`|Ruft einen Schnittstellenzeiger auf ein `IReferenceIdentity` -Instanz, aus dem angegebenen generiert formatierte Zeichenfolge.|

## <a name="requirements"></a>Anforderungen

**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).

**Header:** Isolation.h

**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Siehe auch

- [Fusion-Schnittstellen](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
