---
title: Ausnahmetypen (F#)
description: Informationen Sie zum Definieren und Verwenden von f#-Ausnahmetypen.
ms.date: 05/16/2016
ms.openlocfilehash: 4462dd00ddf9524d1fd376ee1e73e81fcfd5d945
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564037"
---
# <a name="exception-types"></a>Ausnahmetypen

Es gibt zwei Kategorien von Ausnahmen in F# erläutert werden: .NET Ausnahmetypen und f#-Ausnahmetypen. In diesem Thema wird beschrieben, wie zum Definieren und Verwenden von F#-Ausnahmetypen ermöglicht wird.


## <a name="syntax"></a>Syntax

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a>Hinweise
In der vorherigen Syntax *Ausnahmetyp* ist der Name, der einen neuen f#-Ausnahmetyp und *Argumenttyp* stellt den Typ eines Arguments, die beim Auslösen einer Ausnahme dieses Typs bereitgestellt werden kann. Sie können mehrere Argumente angeben, mit der ein Tupel für *Argumenttyp*.

Eine typische Definition für eine f#-Ausnahme sieht ungefähr so aus.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

Sie können eine Ausnahme dieses Typs generiert, mit der `raise` -Funktion wie folgt.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

Können Sie einen f#-Ausnahmetyp direkt in den Filtern in einem `try...with` Ausdruck, wie im folgenden Beispiel gezeigt.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

Der Typ der Ausnahme, die Sie definieren, mit der `exception` -Schlüsselwort in f# ist eine neue Anwendungsart, die von erben `System.Exception`.


## <a name="see-also"></a>Siehe auch
[Ausnahmebehandlung](index.md)

[Ausnahmen: Die `raise`-Funktion](the-raise-function.md)

[Ausnahmenhierarchie](https://msdn.microsoft.com/library/z4c5tckx.aspx)
