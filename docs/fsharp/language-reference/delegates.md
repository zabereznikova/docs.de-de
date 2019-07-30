---
title: Delegaten
description: Erfahren Sie, wie Sie in F#mit Delegaten arbeiten.
ms.date: 05/16/2016
ms.openlocfilehash: 65875897d5fc4b2ac66f1dfbe913f29fb74137cd
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630369"
---
# <a name="delegates"></a>Delegaten

Ein Delegat stellt einen Funktionsaufruf als-Objekt dar. In F#sollten Sie in der Regel Funktions Werte verwenden, um Funktionen als First Class-Werte darzustellen. Delegaten werden jedoch im .NET Framework verwendet und sind daher erforderlich, wenn Sie mit APIs interagieren, die Sie erwarten. Sie können auch beim Erstellen von Bibliotheken verwendet werden, die für die Verwendung in anderen .NET Framework Sprachen entwickelt wurden.

## <a name="syntax"></a>Syntax

```fsharp
type delegate-typename = delegate of type1 -> type2
```

## <a name="remarks"></a>Hinweise

In der vorherigen Syntax `type1` stellt den Argumenttyp oder die Typen dar und `type2` stellt den Rückgabetyp dar. Die Argument Typen, die durch `type1` dargestellt werden, werden automatisch Curry. Dies deutet darauf hin, dass Sie bei diesem Typ ein tupelformular verwenden, wenn die Argumente der Zielfunktion "currried" sind, und ein Tupel in Klammern für Argumente, die sich bereits im tupelformular befinden. Bei der automatischen Currying wird eine Reihe von Klammern entfernt, wobei ein tupelargument, das mit der Ziel Methode übereinstimmt, erhalten bleibt. Die Syntax, die Sie in jedem Fall verwenden sollten, finden Sie im Codebeispiel.

Delegaten angefügt werden können, um F#-Funktionswerte, und statische oder Instanzmethoden. F#Funktions Werte können direkt als Argumente an Delegatkonstruktoren übergeben werden. Bei einer statischen Methode erstellen Sie den Delegaten mit dem Namen der Klasse und der-Methode. Bei einer Instanzmethode stellen Sie die Objektinstanz und-Methode in einem Argument bereit. In beiden Fällen wird der Member Access-Operator`.`() verwendet.

Die `Invoke` Methode für den Delegattyp Ruft die gekapselte Funktion auf. Delegaten können auch als Funktions Werte übergeben werden, indem auf den Aufruf Methodennamen ohne Klammern verwiesen wird.

Der folgende Code zeigt die Syntax zum Erstellen von Delegaten, die verschiedene Methoden in einer Klasse darstellen. Abhängig davon, ob es sich bei der Methode um eine statische Methode oder eine Instanzmethode handelt und ob Sie über Argumente im tupelformular oder in der geschweifenden Form verfügt, ist die Syntax zum Deklarieren und Zuweisen des Delegaten etwas anders.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4201.fs)]

Der folgende Code zeigt einige der verschiedenen Möglichkeiten, mit Delegaten zu arbeiten.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4202.fs)]

Die Ausgabe des vorherigen Code Beispiels lautet wie folgt.

```console
aaaaa
bbbbb
ccccc
[|"aaa"; "bbb"|]
```

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [Parameter und Argumente](parameters-and-arguments.md)
- [Ereignisse](./members/events.md)
