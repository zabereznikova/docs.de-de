---
title: Einstiegspunkt (F#)
description: Erfahren Sie, wie eine f#-Programm Einstiegspunkt fest, die als ausführbare Datei kompiliert wird, in dem Ausführung formal beginnt.
ms.date: 05/16/2016
ms.openlocfilehash: 298500931d49c891a7a243295333df3a9f5d413e
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2018
ms.locfileid: "45515210"
---
# <a name="entry-point"></a>Einstiegspunkt

In diesem Thema wird beschrieben, die Methode, die Sie verwenden, um den Einstiegspunkt auf einem F#-Programm festgelegt wird.

## <a name="syntax"></a>Syntax

```fsharp
[<EntryPoint>]
let-function-binding
```

## <a name="remarks"></a>Hinweise

In der vorherigen Syntax *Let-Funktion-Bindung* ist die Definition einer Funktion in einer `let` Bindung.

Der Einstiegspunkt an ein Programm, das kompiliert wird, wie eine ausführbare Datei handelt, in dem Ausführung formal beginnt. Sie geben den Einstiegspunkt für eine F#-Anwendung durch Anwenden der `EntryPoint` Attribut des Programms `main` Funktion. Diese Funktion (erstellt mit einem `let` Bindung) muss die letzte Funktion in der letzten kompilierten Datei. Die letzte kompilierte Datei ist die letzte Datei im Projekt oder die letzte Datei, die an der Befehlszeile übergeben wird.

Die Einstiegspunktfunktion weist den Typ `string array -> int`. Die Argumente, die in der Befehlszeile angegeben werden übergeben die `main` -Funktion in das Array von Zeichenfolgen. Das erste Element des Arrays ist das erste Argument. der Name der ausführbaren Datei ist nicht im Array enthalten, da es in einigen anderen Sprachen ist. Der zurückgegebene Wert wird als Exitcode für den Prozess verwendet. 0 (null) gibt in der Regel Erfolg; ungleich NULL-Werte geben einen Fehler an. Es gibt keine Konvention für die spezifische Bedeutung des Rückgabecodes für ungleich NULL. die Bedeutung des Rückgabecodes sind anwendungsspezifisch.

Das folgende Beispiel veranschaulicht eine einfache `main` Funktion.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/entry-point/snippet501.fs)]

Wenn dieser Code ausgeführt wird, über die Befehlszeile `EntryPoint.exe 1 2 3`, die Ausgabe lautet wie folgt.

```console
Arguments passed to function : [|"1"; "2"; "3"|]
```

## <a name="implicit-entry-point"></a>Impliziter Einstiegspunkt

Wenn ein Programm hat keine **EntryPoint** -Attribut, das explizit angibt, den Einstiegspunkt, der die Bindungen auf oberster Ebene in der letzten Datei kompiliert werden, werden als Einstiegspunkt verwendet.

## <a name="see-also"></a>Siehe auch

- [Funktionen](index.md)
- [let-Bindungen](let-bindings.md)
