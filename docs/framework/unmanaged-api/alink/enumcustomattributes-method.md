---
title: EnumCustomAttributes-Methode
ms.date: 03/30/2017
api_name:
- EnumCustomAttributes
- IALink.EnumCustomAttributes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method
ms.assetid: 08dff60c-f01b-4050-8865-ea3f95361c9f
topic_type:
- apiref
ms.openlocfilehash: 6a5b3f1e9bf1444feb73949ef7133fbd9ae35134
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446474"
---
# <a name="enumcustomattributes-method"></a>EnumCustomAttributes-Methode
Ruft benutzerdefinierte Attribute auf Assemblyebene ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
## <a name="parameters"></a>Parameter  
 `hEnum`  
 Handle des Enumerators.  
  
 `tkType`  
 Typ der aufzuzählenden Attribute. Verwenden Sie `mdTokenNill` für alle Attribute.  
  
 `rCustomValues`  
 Empfängt benutzerdefinierte Attribut Token.  
  
 `cMax`  
 Gibt die Größe `rCustomValues` Arrays an.  
  
 `pcCustomValues`  
 Empfängt optional die Anzahl der Tokenwerte.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Voraussetzungen  
 Erfordert "Alink. h"  
  
## <a name="see-also"></a>Siehe auch

- [IALink-Schnittstelle](ialink-interface.md)
- [IALink2-Schnittstelle](ialink2-interface.md)
- [Alink-API](index.md)
