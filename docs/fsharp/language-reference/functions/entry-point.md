---
title: Einstiegspunkt
description: Erfahren Sie, wie eine F#-Programm Einstiegspunkt fest, die als ausführbare Datei kompiliert wird, in dem Ausführung formal beginnt.
ms.date: 05/16/2016
ms.openlocfilehash: 5e13416131d4dfd22583439fedf51f18f7a461da
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630524"
---
# <a name="entry-point"></a>Einstiegspunkt

In diesem Thema wird die-Methode beschrieben, mit der Sie den Einstiegspunkt F# auf ein-Programm festlegen.

## <a name="syntax"></a>Syntax

```fsharp
[<EntryPoint>]
let-function-binding
```

## <a name="remarks"></a>Hinweise

In der vorherigen Syntax ist *let-function-binding* die Definition einer Funktion in einer `let` Bindung.

Der Einstiegspunkt zu einem Programm, das als ausführbare Datei kompiliert wird, ist die formale Ausführung. Sie geben den Einstiegspunkt für eine F# Anwendung an, indem `EntryPoint` Sie das- `main` Attribut auf die Funktion des Programms anwenden. Diese Funktion (erstellt mithilfe einer `let` -Bindung) muss die letzte Funktion in der letzten kompilierten Datei sein. Die letzte kompilierte Datei ist die letzte Datei im Projekt oder die letzte Datei, die an die Befehlszeile übermittelt wird.

Die Einstiegspunkt Funktion weist den `string array -> int`Typ auf. Die Argumente, die in der Befehlszeile angegeben werden, `main` werden an die Funktion im Zeichen folgen Array weitergegeben. Das erste Element des Arrays ist das erste Argument. der Name der ausführbaren Datei ist nicht im Array enthalten, da Sie in einigen anderen Sprachen enthalten ist. Der Rückgabewert wird als Exitcode für den Prozess verwendet. NULL zeigt normalerweise den Erfolg an. Werte ungleich 0 (null) geben einen Fehler an. Es gibt keine Konvention für die jeweilige Bedeutung von Rückgabecodes, die nicht NULL sind. die Bedeutungen der Rückgabecodes sind anwendungsspezifisch.

Im folgenden Beispiel wird eine einfache `main` Funktion veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/entry-point/snippet501.fs)]

Wenn dieser Code mit der Befehlszeile `EntryPoint.exe 1 2 3`ausgeführt wird, lautet die Ausgabe wie folgt.

```console
Arguments passed to function : [|"1"; "2"; "3"|]
```

## <a name="implicit-entry-point"></a>Impliziter Einstiegspunkt

Wenn ein Programm über kein **entryPoint** -Attribut verfügt, das den Einstiegspunkt explizit angibt, werden die Bindungen auf oberster Ebene in der letzten zu kompilierenden Datei als Einstiegspunkt verwendet.

## <a name="see-also"></a>Siehe auch

- [Funktionen](index.md)
- [let-Bindungen](let-bindings.md)
