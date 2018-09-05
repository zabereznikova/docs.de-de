---
title: Indizierte Eigenschaften (F#)
description: Informationen Sie zu F#-indizierte Eigenschaften, die Eigenschaften sind, die arrayähnlichen Zugriff auf sortierte Daten bereitstellen.
ms.date: 05/16/2016
ms.openlocfilehash: e56e4e2ea3f35df4c8ec46012357242cb6ce69f3
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43749592"
---
# <a name="indexed-properties"></a>Indizierte Eigenschaften

*Indizierte Eigenschaften* sind Eigenschaften, die arrayähnlichen Zugriff auf bereitstellen sortiert Daten. Sie gibt drei Arten:

* `Item`
* `Ordinal`
* `Cardinal`

Ein F#-Element muss einen dieser drei Namen arrayähnlichen Zugriff bereitstellen benannt werden. `IndexerName` wird verwendet, um jeden der drei folgenden Optionen darstellen:

## <a name="syntax"></a>Syntax

```fsharp
// Indexed property that has both get and set defined.
member self-identifier.IndexerName
    with get(index-variable) =
        get-function-body
    and set index-variablesvalue-variables =
        set-function-body

// Indexed property that has get only.
member self-identifier.IndexerName(index-variable) =
    get-function-body

// Alternative syntax for indexed property with get only
member self-identifier.IndexerName
    with get(index-variables) =
        get-function-body

// Indexed property that has set only.
member self-identifier.IndexerName
    with set index-variablesvalue-variables = 
        set-function-body
```

## <a name="remarks"></a>Hinweise

Die Formen der vorherigen Syntax zeigen, wie Sie indizierte Eigenschaften definiert, die sowohl eine `get` und ein `set` -Methode, haben eine `get` Methode nur oder über eine `set` Methode nur. Sie können auch kombiniert sowohl die Syntax für nur Get- und die Syntax für die Gruppe nur und erzeugen eine Eigenschaft, die sowohl get- und Set hat. Diese Form können Sie verschiedene Zugriffsmodifizierer und Attribute für die Get-und set-Methoden.

Wenn die *IndexerName* ist `Item`, behandelt der Compiler die Eigenschaft als eine indizierte Standardeigenschaft. Ein *indizierte Standardeigenschaft* ist eine Eigenschaft, die Sie zugreifen können, mithilfe einer arrayähnlichen Syntax in der Objektinstanz. Z. B. wenn `obj` ist ein Objekt des Typs, der diese Eigenschaft, die Syntax definiert `obj.[index]` wird verwendet, um die Eigenschaft zugreifen.

Die Syntax für den Zugriff auf eine nicht standardmäßige indizierte Eigenschaft ist auf den Namen der Eigenschaft und der Index in Klammern angeben. Wenn die Eigenschaft ist z. B. `Ordinal`, Sie schreiben `obj.Ordinal(index)` , darauf zuzugreifen.

Unabhängig davon, welche Form, die Sie verwenden, Sie immer die Curry-Form verwenden sollten die `set` Methode für eine indizierte Eigenschaft. Weitere Informationen zu Funktionen mit Currying, finden Sie unter [Funktionen](../functions/index.md).

## <a name="example"></a>Beispiel

Das folgende Codebeispiel veranschaulicht die Definition und Verwendung von Standard- und nicht standardmäßigen indizierte Eigenschaften, die verfügen über get- und set-Methoden.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a>Ausgabe

```
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
