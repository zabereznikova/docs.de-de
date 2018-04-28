---
title: Delegaten (F#)
description: Informationen Sie zum Arbeiten mit Delegaten in F# erläutert werden.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 56520cc631d889f390a7d4300be1cb3185306be9
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="delegates"></a>Delegaten

Ein Delegat stellt einen Funktionsaufruf dar, wie ein Objekt. In F# erläutert werden sollten Sie normalerweise Funktionswerte verwenden, um Funktionen als erstrangige Werte darzustellen. Allerdings Delegaten in .NET Framework verwendet werden und daher werden benötigt, wenn Interoperation mit APIs, die sie erwarten. Sie können auch verwendet werden, wenn authoring Bibliotheken, die für entwickelt von anderen .NET Framework-Sprachen verwenden.


## <a name="syntax"></a>Syntax

```fsharp
type delegate-typename = delegate of type1 -> type2
```

## <a name="remarks"></a>Hinweise
In der vorherigen Syntax `type1` stellt den Argumenttyp bzw. die Datentypen und `type2` den Rückgabetyp darstellt. Die Argumenttypen, das von dargestellt sind `type1` werden automatisch mit Currying. Dies legt nahe, die für diesen Typ, der ein Tupel-Formular verwenden, wenn die Argumente der Zielfunktion Curry sind, und ein Tupel in Klammern für Argumente, die bereits in der Tupelform sind. Die automatische currying entfernt einen Satz von Klammern, lassen ein Tupelargument, das die Zielmethode übereinstimmt. Finden Sie im Codebeispiel wird die Syntax, die in jedem Fall verwendet werden sollte.

Delegaten angefügt werden können, in f#-Funktionswerte und statische oder Instanzmethoden. F#-Funktionswerte können direkt als Argumente an die Konstruktoren delegieren übergeben werden. Bei einer statischen Methode erstellen Sie den Delegaten mit dem Namen der Klasse und die Methode an. Für eine Instanzmethode ist Geben Sie die Objektinstanz und-Methode in ein Argument. In beiden Fällen wird der Memberzugriffsoperator (`.`) verwendet wird.

Die `Invoke` Methode auf den Delegattyp gekapselten Funktionsaufrufe. Darüber hinaus können Delegaten als Funktionswerte übergeben werden, auf den Namen des Invoke-Methode ohne Klammern verweisen.

Der folgende Code zeigt die Syntax zum Erstellen von Delegaten, die verschiedene Methoden in einer Klasse darstellen. Je nachdem, ob die Methode eine statische Methode oder Instanzmethode handelt, und gibt an, ob Argumente in die Tupelform oder die Curry-Form verfügt ist die Syntax zum Deklarieren und Zuweisen der Delegat etwas anders.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4201.fs)]

Der folgende Code zeigt einige der Arbeit mit Delegaten können unterschiedliche Arten.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4202.fs)]

Im vorangehenden Codebeispiel wird die Ausgabe lautet wie folgt.

```console
aaaaa
bbbbb
ccccc
[|"aaa"; "bbb"|]
```

## <a name="see-also"></a>Siehe auch
[F#-Sprachreferenz](index.md)

[Parameter und Argumente](parameters-and-arguments.md)

[Ereignisse](members/events.md)
