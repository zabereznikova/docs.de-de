---
title: Typabkürzungen (F#)
description: Informationen Sie zu f# typabkürzungen auf einem Typ einen aussagekräftigeren Namen geben, um den Code verständlicher zu gestalten.
ms.date: 05/16/2016
ms.openlocfilehash: e222caa41a20a64071c94cffea6ea7b2bec8eb22
ms.sourcegitcommit: ff1d40507b3eb6e2185478e37c66c66be6de46f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2018
---
# <a name="type-abbreviations"></a>Typabkürzungen

Ein *-typabkürzung* einen Alias oder ein alternativer Name für einen Typ ist.

## <a name="syntax"></a>Syntax

```fsharp
type [accessibility-modifier] type-abbreviation = type-name
```

## <a name="remarks"></a>Hinweise
Typabkürzungen können Sie einem Typ einen aussagekräftigeren Namen geben, um den Code verständlicher zu gestalten. Sie können Sie auch verwenden, um eine einfach zu verwendende Name für einen Typ zu erstellen, die andernfalls schwierig zu schreiben sind. Darüber hinaus können Sie typabkürzungen verwenden, um ihn leichter ändern, einen zugrunde liegenden Typ ohne Ändern der gesamte Code, der den Typ verwendet. Der folgende Code ist eine Abkürzung des einfachen Typs.

Zugriff auf typabkürzungen standardmäßig `public`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2301.fs)]

Typabkürzungen zählen generische Parameter, wie im folgenden Code.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2302.fs)]

Im vorherigen Code `Transform` ist eine typabkürzung, der eine Funktion darstellt, die ein einzelnes eines beliebigen Typs Argument und einen einzelnen Wert desselben Typs zurückgibt.

Typabkürzungen werden in der .NET Framework-MSIL-Code nicht beibehalten. Bei Verwendung eine f#-Assembly aus einer anderen .NET Framework-Sprache müssen Sie daher der Typname des zugrunde liegenden für typabkürzung verwenden.

Typabkürzungen können auch für Maßeinheiten verwendet werden. Weitere Informationen finden Sie unter [Einheiten](units-of-measure.md).


## <a name="see-also"></a>Siehe auch
[F#-Sprachreferenz](index.md)

