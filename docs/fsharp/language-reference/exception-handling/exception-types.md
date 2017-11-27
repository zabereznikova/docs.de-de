---
title: Ausnahmetypen (F#)
description: Informationen Sie zum Definieren und Verwenden von f#-Ausnahmetypen.
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: e850205a-b8da-459e-8f6d-cb3510f8f173
ms.openlocfilehash: a0864218841396c0ebdf26c7585e0e5bb778f83e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
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
