---
title: Indizierte Eigenschaften
description: Erfahren Sie mehr über indizierte Eigenschaften in F#, die einen Array ähnlichen Zugriff auf geordnete Daten ermöglichen.
ms.date: 10/17/2018
ms.openlocfilehash: 379417e31b8e178d8c939e5b23dc144bfb17e562
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627556"
---
# <a name="indexed-properties"></a>Indizierte Eigenschaften

Beim Definieren einer Klasse, die geordnete Daten abstrahiert, kann es manchmal hilfreich sein, den indizierten Zugriff auf diese Daten bereitzustellen, ohne die zugrunde liegende Implementierung verfügbar zu machen. Dies erfolgt mit dem `Item` -Member.

## <a name="syntax"></a>Syntax

```fsharp
// Indexed property that can be read and written to
member self-identifier.Item
    with get(index-values) =
        get-member-body
    and set index-values values-to-set =
        set-member-body

// Indexed property can only be read
member self-identifier.Item
    with get(index-values) =
        get-member-body

// Indexed property that can only be set
member self-identifier.Item
    with set index-values values-to-set =
        set-member-body
```

## <a name="remarks"></a>Hinweise

Die Formen der vorherigen Syntax veranschaulichen, wie indizierte Eigenschaften definiert werden, die sowohl `get` eine- `set` als auch eine- `get` Methode aufweisen, nur über eine `set` -Methode verfügen oder nur über eine-Methode verfügen. Sie können auch die Syntax für "Get only" und die für "Set" angezeigte Syntax kombinieren und eine Eigenschaft mit "Get" und "Set" entwickeln. In diesem letzteren Formular können Sie verschiedene Zugriffsmodifizierer und Attribute für die Get-und Set-Methoden einfügen.

Wenn Sie den Namen `Item`verwenden, behandelt der Compiler die Eigenschaft als indizierte Standard Eigenschaft. Eine *indizierte Standard Eigenschaft* ist eine Eigenschaft, auf die Sie mithilfe einer Array ähnlichen Syntax für die Objektinstanz zugreifen können. Wenn `o` z. b. ein Objekt vom Typ ist, das diese Eigenschaft definiert, wird `o.[index]` die Syntax für den Zugriff auf die-Eigenschaft verwendet.

Die Syntax für den Zugriff auf eine nicht standardmäßig indizierte Eigenschaft besteht darin, den Namen der Eigenschaft und den Index in Klammern wie einem regulären Member bereitzustellen. Wenn beispielsweise die-Eigenschaft `o` für aufgerufen `Ordinal`wird, schreiben `o.Ordinal(index)` Sie, um darauf zuzugreifen.

Unabhängig davon, welches Formular Sie verwenden, sollten Sie immer das Curry-Formular für die Set-Methode für eine indizierte Eigenschaft verwenden. Weitere Informationen zu Curry-Funktionen finden Sie unter [Functions](../functions/index.md).

## <a name="example"></a>Beispiel

Im folgenden Codebeispiel werden die Definition und die Verwendung von standardmäßigen und nicht standardmäßig indizierten Eigenschaften veranschaulicht, die über Get-und Set-Methoden verfügen.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a>Ausgabe

```console
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-values"></a>Indizierte Eigenschaften mit mehreren Indexwerten

Indizierte Eigenschaften können über mehr als einen Indexwert verfügen. In diesem Fall werden die Werte durch Kommas getrennt, wenn die-Eigenschaft verwendet wird. Die Set-Methode in einer solchen Eigenschaft muss zwei Curry-Argumente aufweisen, wobei das erste ein Tupel ist, das die Schlüssel enthält, und das zweite ist der festzulegende Wert.

Der folgende Code veranschaulicht die Verwendung einer indizierten Eigenschaft mit mehreren Indexwerten.

```fsharp
open System.Collections.Generic

/// Basic implementation of a sparse matrix based on a dictionary
type SparseMatrix() =
    let table = new Dictionary<(int * int), float>()
    member __.Item
        // Because the key is comprised of two values, 'get' has two index values
        with get(key1, key2) = table.[(key1, key2)]

        // 'set' has two index values and a new value to place in the key's position
        and set (key1, key2) value = table.[(key1, key2)] <- value

let sm = new SparseMatrix()
for i in 1..1000 do
    sm.[i, i] <- float i * float i
```

## <a name="see-also"></a>Siehe auch

- [Mitglieder](index.md)
