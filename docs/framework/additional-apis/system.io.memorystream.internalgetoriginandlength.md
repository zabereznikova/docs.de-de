---
title: MemoryStream. internalgetoriginandlength-Methode (System.IO)
author: mairaw
ms.author: mairaw
ms.date: 11/19/2019
topic_type:
- apiref
api_name:
- System.IO.MemoryStream.InternalGetOriginAndLength
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: d2bfa087fe2fb247f963cfa687c27056363d5696
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74284042"
---
# <a name="memorystreaminternalgetoriginandlength-method"></a>MemoryStream. internalgetoriginandlength-Methode

Ruft die internen Werte des Ursprungs und der Länge des Arbeitsspeicherstreams ab.

```csharp
internal void InternalGetOriginAndLength(out int origin, out int length)
```

## <a name="parameters"></a>Parameter

- `origin` <xref:System.Int32>\
  Wenn diese Methode zurückgegeben wird, der Offset des Bytearrays, das beim Erstellen eines neuen <xref:System.IO.MemoryStream>-Objekts angegeben wird. Enthält 0, wenn das Bytearray von <xref:System.IO.MemoryStream>erstellt wurde.

- `length` <xref:System.Int32>\
  Wenn diese Methode zurückgegeben wird, wird die Anzahl der Bytes im Arbeitsspeicherstream angezeigt.

## <a name="remarks"></a>Hinweise

> [!WARNING]
> Die `MemoryStream.InternalGetOriginAndLength`-Methode ist intern und sollte nicht direkt im Code verwendet werden.
>
> Microsoft unterstützt die Verwendung dieser Methode in einer Produktionsanwendung unter keinen Umständen.

## <a name="requirements"></a>Anforderungen

**Namespace:** <xref:System.IO>

**Assembly:** mscorlib. dll (in "mscorlib. dll")

**.NET Framework Versionen:** Verfügbar seit 2,0.
