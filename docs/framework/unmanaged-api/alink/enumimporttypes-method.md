---
title: EnumImportTypes-Methode
ms.date: 03/30/2017
api_name:
- EnumImportTypes
- IALink.EnumImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EnumImportTypes
helpviewer_keywords:
- EnumImportTypes method
ms.assetid: 83a0e4e7-ec06-40cb-9b63-700b9695bb04
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0cd154ac90418dd0f6f476151686ff670c01c98c
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632234"
---
# <a name="enumimporttypes-method"></a>EnumImportTypes-Methode

Listet jeden Typ in jedem Bereich an.

## <a name="syntax"></a>Syntax

```cpp
HRESULT EnumImportTypes(
    HALINKENUM   hEnum,
    DWORD        dwMax,
    mdTypeDef    aTypeDefs[],
    DWORD*       pdwCount
) PURE;
```

## <a name="parameters"></a>Parameter

`hEnum`\
Handle für Enumerator.

`dwMax`\
Maximale Anzahl von Typen, die abgerufen werden.

`aTypeDefs`\
Typtoken, nicht zu überschreiten erhält `dwMax`.

`pdwCount`\
Empfängt die tatsächliche Anzahl der Typen in `aTypeDefs`.

## <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück, wenn die Methode erfolgreich ist.

## <a name="requirements"></a>Anforderungen

Erfordert alink.h

## <a name="see-also"></a>Siehe auch

- [IALink-Schnittstelle](ialink-interface.md)
- [IALink2-Schnittstelle](ialink2-interface.md)
- [Alink-API](index.md)
