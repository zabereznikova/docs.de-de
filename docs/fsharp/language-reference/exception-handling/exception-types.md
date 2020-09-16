---
title: Ausnahmetypen
description: 'Erfahren Sie, wie Sie F #-Ausnahme Typen definieren und verwenden.'
ms.date: 05/16/2016
ms.openlocfilehash: 8b4ceec31a2d68abbcd025812ffeeefc0c090efb
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557228"
---
# <a name="exception-types"></a>Ausnahmetypen

Es gibt zwei Kategorien von Ausnahmen in f #: .NET-Ausnahme Typen und f #-Ausnahme Typen. In diesem Thema wird beschrieben, wie Sie F #-Ausnahme Typen definieren und verwenden.

## <a name="syntax"></a>Syntax

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a>Hinweise

In der vorherigen Syntax ist *Exception-Type* der Name eines neuen F #-Ausnahme Typs, und der *Argumenttyp* stellt den Typ eines Arguments dar, das bereitgestellt werden kann, wenn Sie eine Ausnahme dieses Typs auslöst. Sie können mehrere Argumente angeben, indem Sie einen tupeltyp für den *Argumenttyp*verwenden.

Eine typische Definition für eine F #-Ausnahme ähnelt der folgenden.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

Sie können eine Ausnahme dieses Typs generieren, indem Sie die- `raise` Funktion wie folgt verwenden.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

Sie können einen F #-Ausnahmetyp direkt in den Filtern in einem- `try...with` Ausdruck verwenden, wie im folgenden Beispiel gezeigt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

Der Ausnahmetyp, den Sie mit dem- `exception` Schlüsselwort in F # definieren, ist ein neuer Typ, der von erbt `System.Exception` .

## <a name="see-also"></a>Siehe auch

- [Ausnahmebehandlung](index.md)
- [Ausnahmen: Die `raise`-Funktion](the-raise-function.md)
- [Ausnahmenhierarchie](../../../standard/exceptions/index.md)
