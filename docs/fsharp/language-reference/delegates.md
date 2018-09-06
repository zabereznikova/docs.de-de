---
title: Delegaten (F#)
description: Informationen Sie zum Arbeiten mit Delegaten in F# erläutert werden.
ms.date: 05/16/2016
ms.openlocfilehash: be58997dffe8fcd949bbc2d47d86ffccc157d43e
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43801525"
---
# <a name="delegates"></a>Delegaten

Ein Delegat stellt einen Funktionsaufruf dar, wie ein Objekt. In F# erläutert werden sollten Sie normalerweise Werte von Funktionen verwenden, um Funktionen als erstrangige Werte darzustellen; Allerdings Delegaten in .NET Framework verwendet werden und daher sind erforderlich, wenn Interoperation mit APIs, die sie erwarten. Sie können auch authoring Bibliotheken zur Verwendung von anderen .NET Framework-Sprachen verwendet werden.

## <a name="syntax"></a>Syntax

```fsharp
type delegate-typename = delegate of type1 -> type2
```

## <a name="remarks"></a>Hinweise

In der vorherigen Syntax `type1` stellt den Argumenttyp bzw. die Datentypen und `type2` den Rückgabetyp darstellt. Die Argumenttypen, das von dargestellt sind `type1` werden automatisch mit Currying. Dies deutet darauf hin, die für diesen Typ, der Sie ein Tupel-Formular verwenden, wenn die Argumente der Zielfunktion Currying verarbeitet werden, und ein Tupel in Klammern für Argumente, die bereits in der Tupelform sind. Die automatische currying entfernt einen Satz von Klammern, sodass ein Tupelargument, das die Zielmethode entspricht. Finden Sie im Codebeispiel wird die Syntax, die Sie in jedem Fall verwenden sollten.

Delegaten angefügt werden können, um f#-Funktionswerte, und statische oder Instanzmethoden. F#-Funktionswerte können direkt als Argumente für das Delegieren von Konstruktoren übergeben werden. Für eine statische Methode erstellen Sie den Delegaten, mit dem Namen der Klasse und Methode. Für eine Instanzmethode stellen Sie die Objektinstanz und der-Methode in ein Argument bereit. In beiden Fällen der Memberzugriffsoperator (`.`) verwendet wird.

Die `Invoke` Methode auf dem Delegattyp die gekapselte Funktion aufruft. Darüber hinaus können Delegaten durch Verweisen auf den Namen des Invoke-Methode ohne Klammern als Werte von Funktionen übergeben werden.

Der folgende Code zeigt die Syntax zum Erstellen von Delegaten, die verschiedene Methoden in einer Klasse darstellen. Je nachdem, ob die Methode eine statische Methode oder eine Instanzmethode ist, und gibt an, ob Argumente im Tupel Format oder die Curry-Form verfügt ist die Syntax zum Deklarieren und Zuweisen von Delegaten ein wenig anders.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4201.fs)]

Der folgende Code zeigt einige der Möglichkeiten, mit denen, die Sie Delegaten zusammenarbeiten können.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4202.fs)]

Die Ausgabe des vorherigen Codebeispiel lautet wie folgt aus.

```console
aaaaa
bbbbb
ccccc
[|"aaa"; "bbb"|]
```

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [Parameter und Argumente](parameters-and-arguments.md)
- [Ereignisse](members/events.md)
