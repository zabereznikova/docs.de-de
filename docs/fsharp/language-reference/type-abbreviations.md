---
title: Typabkürzungen
description: Informationen Sie zu F# typabkürzungen auf einem Typ einen aussagekräftigeren Namen geben, damit der um Code leichter lesbar zu machen.
ms.date: 05/16/2016
ms.openlocfilehash: 0deaef789367aad413e5a537bf7164034e1275c0
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2018
ms.locfileid: "53613348"
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

Typabkürzungen werden nicht in der .NET Framework-MSIL-Code beibehalten. Aus diesem Grund bei Verwendung einer F# Assembly von einer anderen .NET Framework-Sprache, müssen Sie den zugrunde liegenden Typnamen für eine typabkürzung verwenden.

Typabkürzungen können auch auf Maßeinheiten verwendet werden. Weitere Informationen finden Sie unter [Einheiten](units-of-measure.md).

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)