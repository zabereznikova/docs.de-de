---
title: Ausnahmetypen (F#)
description: Informationen Sie zum Definieren und Verwenden von F#-Typen.
ms.date: 05/16/2016
ms.openlocfilehash: b8d648a3649153a3604856deb61ce41db8c40bf2
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2018
ms.locfileid: "43858820"
---
# <a name="exception-types"></a>Ausnahmetypen

Es gibt zwei Kategorien von Ausnahmen in F#: Ausnahmetypen in .NET und F#-Typen. Dieses Thema beschreibt, wie Sie definieren und Verwenden von F#-Typen.

## <a name="syntax"></a>Syntax

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a>Hinweise

In der vorherigen Syntax *Ausnahmetyp* ist der Name eines neuen F#-Ausnahme-Typs, und *Argumenttyp* stellt den Typ eines Arguments, die beim Auslösen einer Ausnahme dieses Typs bereitgestellt werden kann. Sie können mehrere Argumente angeben, indem Sie verwenden einen Tupeltyp für *Argumenttyp*.

Eine typische Definition für eine F#-Ausnahme ähnelt dem folgenden Code.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

Sie können eine Ausnahme dieses Typs generieren, mit der `raise` -Funktion wie folgt.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

Können Sie direkt in den Filtern in einer F#-Typ der Ausnahme eine `try...with` Ausdruck wie im folgenden Beispiel gezeigt.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

Der Typ der Ausnahme, die Sie definieren, mit der `exception` Schlüsselwort in F# ist eine neue Art, die von erbt `System.Exception`.

## <a name="see-also"></a>Siehe auch

- [Ausnahmebehandlung](index.md)
- [Ausnahmen: Die `raise`-Funktion](the-raise-function.md)
- [Ausnahmenhierarchie](https://msdn.microsoft.com/library/z4c5tckx.aspx)
