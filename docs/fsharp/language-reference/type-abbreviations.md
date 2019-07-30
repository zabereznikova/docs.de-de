---
title: Typabkürzungen
description: Informationen Sie zu F# typabkürzungen auf einem Typ einen aussagekräftigeren Namen geben, damit der um Code leichter lesbar zu machen.
ms.date: 05/16/2016
ms.openlocfilehash: 339b22a675e3f1ad8a3da207053e611942b55a22
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630212"
---
# <a name="type-abbreviations"></a>Typabkürzungen

Eine *typabkürzung* ist ein Alias oder ein alternativer Name für einen Typ.

## <a name="syntax"></a>Syntax

```fsharp
type [accessibility-modifier] type-abbreviation = type-name
```

## <a name="remarks"></a>Hinweise

Mit typabkürzungen können Sie einen aussagekräftigeren Namen geben, um den Code leichter lesbar zu machen. Sie können Sie auch verwenden, um einen benutzerfreundlichen Namen für einen Typ zu erstellen, der andernfalls mühsam zu schreiben ist. Außerdem können Sie typabkürzungen verwenden, um die Änderung eines zugrunde liegenden Typs zu vereinfachen, ohne den gesamten Code zu ändern, der den Typ verwendet. Im folgenden finden Sie eine einfache typabkürzung.

Der Zugriff auf typabkürzungen ist `public`standardmäßig auf.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2301.fs)]

Typabkürzungen können generische Parameter enthalten, wie im folgenden Code zu sehen.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2302.fs)]

Im vorherigen Code `Transform` ist eine typabkürzung, die eine Funktion darstellt, die ein einzelnes Argument eines beliebigen Typs annimmt und einen einzelnen Wert desselben Typs zurückgibt.

Typabkürzungen werden im .NET Framework MSIL-Code nicht beibehalten. Wenn Sie eine F# Assembly aus einer anderen .NET Framework Sprache verwenden, müssen Sie daher den zugrunde liegenden Typnamen für eine typabkürzung verwenden.

Typabkürzungen können auch für Maßeinheiten verwendet werden. Weitere Informationen finden Sie unter [Maßeinheiten](units-of-measure.md).

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
