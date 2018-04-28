---
title: Indizierte Eigenschaften (F#)
description: Informationen Sie zu f#-indizierte Eigenschaften, die Eigenschaften sind, die arrayähnlichen Zugriff auf geordnete Daten bereitstellen.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 39396b3a5ec43f9a8ab0df96afeb69e05801c752
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="indexed-properties"></a>Indizierte Eigenschaften

*Indizierte Eigenschaften* befohlen Eigenschaften, die arrayähnlichen Zugriff auf Daten.


## <a name="syntax"></a>Syntax

```fsharp
// Indexed property that has both get and set defined.
member self-identifier.PropertyName
    with get(index-variable) =
        get-function-body
    and set index-variablesvalue-variables =
        set-function-body

// Indexed property that has get only.
member self-identifier.PropertyName(index-variable) =
    get-function-body

// Alternative syntax for indexed property with get only
member self-identifier.PropertyName
    with get(index-variables) =
        get-function-body

// Indexed property that has set only.
member self-identifier.PropertyName
    with set index-variablesvalue-variables = 
        set-function-body
```

## <a name="remarks"></a>Hinweise
Die drei Arten von der vorherigen Syntax zeigen, wie indizierte Eigenschaften definieren, die sowohl eine `get` und eine `set` -Methode, haben eine `get` Methode nur oder über eine `set` Methode nur. Sie können auch kombiniert sowohl die Syntax für nur Get- und Set nur die Syntax und erzeugt eine Eigenschaft, die Get- und Set hat. Diese Form können Sie unterschiedliche Zugriffsmodifizierer und Attribute in der Get und set-Methoden.

Wenn die *PropertyName* ist `Item`, behandelt der Compiler die Eigenschaft als eine indizierte Standardeigenschaft. Ein *indizierte Standardeigenschaft* ist eine Eigenschaft, die Sie mithilfe einer arrayähnlichen Syntax auf die Objektinstanz zugreifen können. Z. B. wenn `obj` ist ein Objekt des Typs, der diese Eigenschaft, die Syntax definiert `obj.[index]` wird verwendet, um Zugriff auf die Eigenschaft.

Die Syntax für den Zugriff auf eine nicht standardmäßige indizierte Eigenschaft wird zum Bereitstellen des Namens der Eigenschaft und der Index in Klammern. Wenn die Eigenschaft beispielsweise `Ordinal`, Schreiben Sie `obj.Ordinal(index)` darauf zugreifen.

Unabhängig davon, welche Form, die Sie verwenden, immer die Curry-Form verwenden sollte die `set` Methode nach einer indizierten Eigenschaft. Informationen über Curry-Funktionen finden Sie unter [Funktionen](../functions/index.md).

## <a name="example"></a>Beispiel

Das folgende Codebeispiel veranschaulicht die Definition und Verwendung von Standard- und nicht standardmäßiger indizierte Eigenschaften, die verfügen über get- und set-Methoden.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a>Ausgabe

```
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-variables"></a>Indizierte Eigenschaften mit mehreren Indexvariablen
Indizierte Eigenschaften können mehr als eine Indexvariable haben. In diesem Fall werden die Variablen durch Kommas getrennt, wenn die Eigenschaft verwendet wird. Die Set-Methode in einer solchen Eigenschaft benötigen zwei Curry-Argumenten, das erste ist ein Tupel, die mit den Schlüsseln, und das zweite ist der festgelegte Wert.

Der folgende Code veranschaulicht die Verwendung einer indizierten Eigenschaft mit mehreren Indexvariablen.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3302.fs)]
    
## <a name="see-also"></a>Siehe auch
[Mitglieder](index.md)
