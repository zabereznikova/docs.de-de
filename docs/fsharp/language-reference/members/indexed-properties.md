---
title: Indizierte Eigenschaften
description: Erfahren Sie mehr über indizierte Eigenschaften in F#, das arrayähnlichen Zugriff auf die sortierten Daten ermöglichen.
ms.date: 10/17/2018
ms.openlocfilehash: 3817290505339803814e981cd5408cd4df6bd283
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2018
ms.locfileid: "53611775"
---
# <a name="indexed-properties"></a>Indizierte Eigenschaften

Beim Definieren einer Klasse, die für sortierte Daten abstrahiert, kann es manchmal hilfreich, indizierten Zugriff auf diese Daten bereitstellen, ohne die zugrunde liegende Implementierung verfügbar zu machen sein. Dies erfolgt mit der `Index` Member.

## <a name="syntax"></a>Syntax

```fsharp
// Indexed property that has both get and set defined.
member self-identifier.Index
    with get(index-values) =
        get-member-body
    and set index-values values-to-set =
        set-member-body

// Indexed property with get only
member self-identifier.Index
    with get(index-values) =
        get-member-body

// Indexed property that has set only.
member self-identifier.Index
    with set index-values values-to-set =
        set-member-body
```

## <a name="remarks"></a>Hinweise

Die Formen der vorherigen Syntax zeigen, wie Sie indizierte Eigenschaften definiert, die sowohl eine `get` und ein `set` -Methode, haben eine `get` Methode nur oder über eine `set` Methode nur. Sie können auch kombiniert sowohl die Syntax für nur Get- und die Syntax für die Gruppe nur und erzeugen eine Eigenschaft, die sowohl get- und Set hat. Diese Form können Sie verschiedene Zugriffsmodifizierer und Attribute für die Get-und set-Methoden.

Mit dem Namen `Item`, behandelt der Compiler die Eigenschaft als eine indizierte Standardeigenschaft. Ein *indizierte Standardeigenschaft* ist eine Eigenschaft, die Sie zugreifen können, mithilfe einer arrayähnlichen Syntax in der Objektinstanz. Z. B. wenn `o` ist ein Objekt des Typs, der diese Eigenschaft, die Syntax definiert `o.[index]` wird verwendet, um die Eigenschaft zugreifen.

Die Syntax für den Zugriff auf eine nicht standardmäßige indizierte Eigenschaft ist zum Bereitstellen des Namens der Eigenschaft und der Index in Klammern ein, wie ein reguläres Element. Z. B. wenn die Eigenschaft `o` heißt `Ordinal`, Sie schreiben `o.Ordinal(index)` , darauf zuzugreifen.

Unabhängig davon, welche Form, die Sie verwenden, sollten Sie immer die Curry-Form für die Set-Methode für eine indizierte Eigenschaft verwenden. Weitere Informationen zu Funktionen mit Currying, finden Sie unter [Funktionen](../functions/index.md).

## <a name="example"></a>Beispiel

Das folgende Codebeispiel veranschaulicht die Definition und Verwendung von Standard- und nicht standardmäßigen indizierte Eigenschaften, die verfügen über get- und set-Methoden.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a>Output

```console
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-variables"></a>Indizierte Eigenschaften mit mehreren Indexvariablen

Indizierte Eigenschaften können mehrere Indexvariable haben. In diesem Fall werden die Variablen durch Kommas getrennt, wenn die Eigenschaft verwendet wird. Die Set-Methode in eine entsprechende Eigenschaft benötigen zwei Curry-Argumente, das erste Argument ist ein Tupel, die die Schlüssel und die zweite ist der Wert festgelegt wird.

Der folgende Code veranschaulicht die Verwendung einer indizierten Eigenschaft mit mehreren Indexvariablen.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3302.fs)]

## <a name="see-also"></a>Siehe auch

- [Mitglieder](index.md)