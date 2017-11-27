---
title: "Typabkürzungen (F#)"
description: "Informationen Sie zu f# typabkürzungen auf einem Typ einen aussagekräftigeren Namen geben, um den Code verständlicher zu gestalten."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 560af74f-935f-415c-af56-604cddb9da6b
ms.openlocfilehash: 235c0240fe89d203b9474dec2b3f91947f453cd8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="type-abbreviations"></a>Typabkürzungen

Ein *-typabkürzung* einen Alias oder ein alternativer Name für einen Typ ist.

## <a name="syntax"></a>Syntax

```fsharp
type type-abbreviation = type-name
```

## <a name="remarks"></a>Hinweise
Typabkürzungen können Sie einem Typ einen aussagekräftigeren Namen geben, um den Code verständlicher zu gestalten. Sie können Sie auch verwenden, um eine einfach zu verwendende Name für einen Typ zu erstellen, die andernfalls schwierig zu schreiben sind. Darüber hinaus können Sie typabkürzungen verwenden, um ihn leichter ändern, einen zugrunde liegenden Typ ohne Ändern der gesamte Code, der den Typ verwendet. Der folgende Code ist eine Abkürzung des einfachen Typs.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2301.fs)]

Typabkürzungen zählen generische Parameter, wie im folgenden Code.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2302.fs)]

Im vorherigen Code `Transform` ist eine typabkürzung, der eine Funktion darstellt, die ein einzelnes eines beliebigen Typs Argument und einen einzelnen Wert desselben Typs zurückgibt.

Typabkürzungen werden in der .NET Framework-MSIL-Code nicht beibehalten. Bei Verwendung eine f#-Assembly aus einer anderen .NET Framework-Sprache müssen Sie daher der Typname des zugrunde liegenden für typabkürzung verwenden.

Typabkürzungen können auch für Maßeinheiten verwendet werden. Weitere Informationen finden Sie unter [Einheiten](units-of-measure.md).


## <a name="see-also"></a>Siehe auch
[F#-Sprachreferenz](index.md)

