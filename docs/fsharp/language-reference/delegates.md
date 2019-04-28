---
title: Delegaten
description: Informationen zum Arbeiten mit Delegaten F#.
ms.date: 05/16/2016
ms.openlocfilehash: 772685488b7caef92123979d817929c631248afb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766076"
---
# <a name="delegates"></a>Delegaten

Ein Delegat stellt einen Funktionsaufruf dar, wie ein Objekt. In F#, normalerweise verwenden Sie Werte von Funktionen zum Darstellen von Funktionen als erstrangige Werte; Allerdings Delegaten in .NET Framework verwendet werden und daher sind erforderlich, wenn Interoperation mit APIs, die sie erwarten. Sie können auch authoring Bibliotheken zur Verwendung von anderen .NET Framework-Sprachen verwendet werden.

## <a name="syntax"></a>Syntax

```fsharp
type delegate-typename = delegate of type1 -> type2
```

## <a name="remarks"></a>Hinweise

In der vorherigen Syntax `type1` stellt den Argumenttyp bzw. die Datentypen und `type2` den Rückgabetyp darstellt. Die Argumenttypen, das von dargestellt sind `type1` werden automatisch mit Currying. Dies deutet darauf hin, die für diesen Typ, der Sie ein Tupel-Formular verwenden, wenn die Argumente der Zielfunktion Currying verarbeitet werden, und ein Tupel in Klammern für Argumente, die bereits in der Tupelform sind. Die automatische currying entfernt einen Satz von Klammern, sodass ein Tupelargument, das die Zielmethode entspricht. Finden Sie im Codebeispiel wird die Syntax, die Sie in jedem Fall verwenden sollten.

Delegaten angefügt werden können, um F#-Funktionswerte, und statische oder Instanzmethoden. F#Werte von Funktionen können direkt als Argumente für das Delegieren von Konstruktoren übergeben werden. Für eine statische Methode erstellen Sie den Delegaten, mit dem Namen der Klasse und Methode. Für eine Instanzmethode stellen Sie die Objektinstanz und der-Methode in ein Argument bereit. In beiden Fällen der Memberzugriffsoperator (`.`) verwendet wird.

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