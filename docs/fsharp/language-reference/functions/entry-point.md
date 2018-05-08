---
title: Einstiegspunkt (F#)
description: Erfahren Sie, wie ein f#-Programms Einstiegspunkt fest, die als eine ausführbare Datei kompiliert wird, in dem Ausführung formal beginnt.
ms.date: 05/16/2016
ms.openlocfilehash: 3d6cab755dd89f2d3d669a8763aa08660432a0ac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="entry-point"></a>Einstiegspunkt

Dieses Thema beschreibt die Methode, mit denen Sie den Einstiegspunkt auf einem F#-Programm festgelegt.


## <a name="syntax"></a>Syntax

```fsharp
[<EntryPoint>]
let-function-binding
```

## <a name="remarks"></a>Hinweise
In der vorherigen Syntax *Let funktionsbindung* ist die Definition einer Funktion in einer `let` Bindung.

Der Einstiegspunkt an ein Programm, das kompiliert wird, wie eine ausführbare Datei handelt, in dem Ausführung formal beginnt. Geben Sie den Einstiegspunkt für eine f#-Anwendung, durch Anwenden der `EntryPoint` -Attribut auf des Programms `main` Funktion. Diese Funktion (erstellt mit einer `let` Bindung) muss die letzte Funktion in der letzten kompilierten Datei sein. Die letzte kompilierte Datei ist die letzte Datei im Projekt oder die letzte Datei, die an der Befehlszeile übergeben wird.

Die Einstiegspunktfunktion weist den Typ `string array -> int`. Argumente in der Befehlszeile übergeben werden, um die `main` -Funktion in das Array von Zeichenfolgen. Das erste Element des Arrays ist das erste Argument; der Name der ausführbaren Datei ist nicht im Array enthalten, da es in einigen anderen Sprachen ist. Der zurückgegebene Wert wird als der Exitcode für den Prozess verwendet. 0 (null) gibt in der Regel die erfolgreiche Ausführung; Werte ungleich Null geben einen Fehler an. Es gibt keine Konvention für die spezifische Bedeutung des Rückgabecodes ungleich null; die Bedeutung des Rückgabecodes sind anwendungsspezifisch.

Das folgende Beispiel veranschaulicht eine einfache `main` Funktion.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/entry-point/snippet501.fs)]

Wenn dieser Code ausgeführt wird, mit der Befehlszeile `EntryPoint.exe 1 2 3`, die Ausgabe lautet wie folgt.

```console
Arguments passed to function : [|"1"; "2"; "3"|]
```

## <a name="implicit-entry-point"></a>Implizite Einstiegspunkt
Wenn ein Programm hat keine **EntryPoint** -Attribut, das den Einstiegspunkt der obersten Ebene Bindungen in der letzten Datei zu kompilierenden gibt explizit an als Einstiegspunkt verwendet werden.


## <a name="see-also"></a>Siehe auch
[Funktionen](index.md)

[let-Bindungen](let-bindings.md)
