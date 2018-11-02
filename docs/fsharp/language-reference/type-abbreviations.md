---
title: Typabkürzungen (F#)
description: Informationen Sie zu f# typabkürzungen auf einem Typ einen aussagekräftigeren Namen geben, damit der um Code leichter lesbar zu machen.
ms.date: 05/16/2016
ms.openlocfilehash: 259cd6c84e22fc7c98e08255d3e0ded5b87af352
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2018
ms.locfileid: "48842423"
---
# <a name="type-abbreviations"></a>Typabkürzungen

Ein *-typabkürzung* ist ein Alias oder alternative Namen für einen Typ.

## <a name="syntax"></a>Syntax

```fsharp
type [accessibility-modifier] type-abbreviation = type-name
```

## <a name="remarks"></a>Hinweise

Typabkürzungen können Sie einem Typ geben Sie einen aussagekräftigeren Namen, um den Code leichter lesbar zu machen. Sie können Sie auch verwenden, um eine benutzerfreundliche Namen für einen Typ zu erstellen, die andernfalls schwierig zu schreiben sind. Typabkürzungen können Sie darüber hinaus erleichtern es, einen zugrunde liegenden Typ ändern, ohne den Code aus, der den Typ verwendet. Folgendes ist eine Abkürzung des einfachen Typs.

Zugriff auf typabkürzungen standardmäßig `public`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2301.fs)]

Typabkürzungen können es sich um generische Parameter, wie im folgenden Code enthalten.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2302.fs)]

Im vorherigen Code `Transform` ist eine typabkürzung, die eine Funktion darstellt, die ein einzelnes Argument eines beliebigen Typs akzeptiert und einen einzelnen Wert desselben Typs zurückgibt.

Typabkürzungen werden nicht in der .NET Framework-MSIL-Code beibehalten. Wenn Sie eine F#-Assembly von einer anderen .NET Framework-Sprache verwenden, müssen Sie daher den zugrunde liegenden Typnamen für eine typabkürzung verwenden.

Typabkürzungen können auch auf Maßeinheiten verwendet werden. Weitere Informationen finden Sie unter [Einheiten](units-of-measure.md).

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
