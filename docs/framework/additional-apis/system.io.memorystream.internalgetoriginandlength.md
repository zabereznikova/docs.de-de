---
title: MemoryStream. internalgetoriginandlength-Methode (System.IO)
ms.date: 11/19/2019
topic_type:
- apiref
api_name:
- System.IO.MemoryStream.InternalGetOriginAndLength
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: d82b5080e9fbd5fc6603f1cddae996c75a06d3a3
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215459"
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

## <a name="remarks"></a>Bemerkungen

> [!WARNING]
> Die `MemoryStream.InternalGetOriginAndLength`-Methode ist intern und sollte nicht direkt im Code verwendet werden.
>
> Microsoft unterstützt die Verwendung dieser Methode in einer Produktionsanwendung unter keinen Umständen.

## <a name="requirements"></a>Requirements (Anforderungen)

**Namespace:** <xref:System.IO>

**Assembly:** mscorlib. dll (in "mscorlib. dll")

**.NET Framework Versionen:** Verfügbar seit 2,0.
