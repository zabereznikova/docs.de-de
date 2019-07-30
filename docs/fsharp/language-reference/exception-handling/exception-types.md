---
title: Ausnahmetypen
description: Erfahren Sie, wie Sie Ausnahme F# Typen definieren und verwenden.
ms.date: 05/16/2016
ms.openlocfilehash: 8545fab50ff6338d1f1621710a838a200f9ac705
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630310"
---
# <a name="exception-types"></a>Ausnahmetypen

Es gibt zwei Kategorien von Ausnahmen in F#: Ausnahmetypen in .NET und F#-Typen. In diesem Thema wird beschrieben, wie Ausnahme F# Typen definiert und verwendet werden.

## <a name="syntax"></a>Syntax

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a>Hinweise

In der vorherigen Syntax ist *Exception-Type* der Name eines neuen F# Ausnahme Typs, und der *Argumenttyp* stellt den Typ eines Arguments dar, das bereitgestellt werden kann, wenn Sie eine Ausnahme dieses Typs auslöst. Sie können mehrere Argumente angeben, indem Sie einen tupeltyp für den *Argumenttyp*verwenden.

Eine typische Definition für eine F# Ausnahme ähnelt der folgenden.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

Sie können eine Ausnahme dieses Typs generieren, indem Sie die `raise` -Funktion wie folgt verwenden.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

Sie können einen F# Ausnahmetyp direkt in den Filtern in einem `try...with` -Ausdruck verwenden, wie im folgenden Beispiel gezeigt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

Der Typ der Ausnahme, die Sie definieren, mit der `exception` Schlüsselwort in F# ist eine neue Art, die von erbt `System.Exception`.

## <a name="see-also"></a>Siehe auch

- [Ausnahmebehandlung](index.md)
- [Ausnahmen: Die `raise`-Funktion](the-raise-function.md)
- [Ausnahmenhierarchie](https://msdn.microsoft.com/library/z4c5tckx.aspx)
