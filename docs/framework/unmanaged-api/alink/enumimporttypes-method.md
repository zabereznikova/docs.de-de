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
ms.openlocfilehash: ca7c7570aff63aa328dddc0626648fa74397addc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448734"
---
# <a name="enumimporttypes-method"></a>EnumImportTypes-Methode

Listet jeden Typ in jedem Bereich auf.

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
Maximale Anzahl der abzurufenden Typen.

`aTypeDefs`\
Empfängt Typtoken, ohne dass die `dwMax`überschritten wird.

`pdwCount`\
Empfängt die tatsächliche Anzahl von Typen in `aTypeDefs`.

## <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück, wenn die Methode erfolgreich ist.

## <a name="requirements"></a>Voraussetzungen

Erfordert "Alink. h"

## <a name="see-also"></a>Siehe auch

- [IALink-Schnittstelle](ialink-interface.md)
- [IALink2-Schnittstelle](ialink2-interface.md)
- [Alink-API](index.md)
