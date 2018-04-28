---
title: Erste Schritte mit f# in Visual Studio für Mac
description: Informationen Sie zum f# mit Visual Studio für Mac verwenden
author: cartermp
ms.author: phcart
ms.date: 02/13/2017
ms.topic: conceptual
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 232235952ec43f682dc21de4ef7dde9c1b553364
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="get-started-with-f-in-visual-studio-for-mac"></a>Erste Schritte mit f# in Visual Studio für Mac

F# und Visual f#-Tools werden in der Visual Studio für Mac-IDE unterstützt.  Um zu beginnen, sollten Sie [Visual Studio für Mac herunterladen](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs), sofern Sie noch nicht geschehen.  In diesem Artikel verwendet die Visual Studio Community 2017 für Mac, jedoch können Sie f# mit der Version Ihrer Wahl.

## <a name="installing-f"></a>Installieren [F#] #

Nach dem Herunterladen von Visual Studio für Mac, werden sie aufgefordert, wählen, was Sie installieren möchten.  Im Rahmen dieses Artikels wird die Standardeinstellungen verlassen.  Im Gegensatz zu Visual Studio für Windows müssen Sie nicht ausdrücklich F#-Unterstützung installieren.  Drücken Sie auf "Installieren", um den Vorgang fortzusetzen.

Nachdem die Installation abgeschlossen ist, wählen Sie "Visual Studio starten" aus.  Sie können es auch über Finder auf MacOS starten.

## <a name="creating-a-console-application"></a>Erstellen einer Konsolenanwendung

Eines der grundlegendsten Projekte in Visual Studio für Mac ist die Konsolenanwendung.  Und so gehen Sie dabei vor.  Sobald Visual Studio für Mac geöffnet wird:

1. Auf der **Datei** Sie im Menü **neue Projektmappe**.

2.  Klicken Sie im Dialogfeld "Neues Projekt" stehen für die Konsolenanwendung 2 unterschiedliche Vorlagen zur Verfügung.  Ist ein anderen -> .NET, das auf .NET Framework abzielt.  Die andere Vorlage ist unter .NET Core -> App verwendet, die .NET Core als Ziel verwendet.  Entweder Vorlage sollte für die in diesem Artikel funktionieren.

3. Unter Konsolen-app C#-, f# bei Bedarf ändern.  Wählen Sie die **Weiter** Schaltfläche weitergehen!  

4. Benennen Sie dem Projekt, und wählen Sie die Optionen für die app aus.  Beachten Sie, dass das Vorschaufenster auf der Seite des Bildschirms, der die Verzeichnisstruktur anzeigt, die erstellt werden soll, basierend auf der ausgewählten Optionen.  

5. Klicken Sie auf **Erstellen**.  Jetzt sollte eine f#-Projekt im Projektmappen-Explorer angezeigt werden.

## <a name="writing-your-code"></a>Das Schreiben des Codes

Fangen wir zuerst, Code zu schreiben.  Stellen Sie sicher, dass die `Program.fs` Datei geöffnet ist, und Ersetzen Sie den Inhalt durch Folgendes:

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

Im vorherigen Codebeispiel ist eine Funktion `square` hat definiert wurde, der mit dem Namen Eingabe akzeptiert `x` und multipliziert es eigenständig.  Da die f# verwendet [Typrückschluss](../language-reference/type-inference.md), den Typ des `x` muss nicht angegeben werden.  F#-Compiler erkennt die Typen, in denen Multiplikation gültig ist, und weist einen Typ an `x` basierend auf wie `square` aufgerufen wird.  Wenn Sie zeigen `square`, sollte Folgendes angezeigt:

```
val square: x:int -> int
```

Dies ist das sogenannte Typsignatur für die Funktion.  Sie können wie folgt gelesen werden: "Quadrat ist eine Funktion, die eine ganze Zahl, die mit dem Namen akzeptiert x und erzeugt eine ganze Zahl".  Beachten Sie, den der Compiler gegeben haben `square` der `int` Typ fürs - Dies ist da Multiplikation nicht generisch über ist *alle* Typen, aber stattdessen über einen vollständigen Satz von Typen ist generisch.  Der f#-Compiler, die entnommen `int` an diesem Punkt, aber es wird anpassen die Typsignatur beim Aufrufen `square` durch ein anderes Eingabetyp, z. B. eine `float`.

Eine andere Funktion `main`, definiert ist, ist die Angabe der `EntryPoint` Attribut anzuweisen, die f#-Compiler, Ausführung des Programms sollte dort starten.  Es folgt die gleiche Konvention wie andere [Programmiersprachen C-Stil](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), wobei Befehlszeilenargumente an diese Funktion übergeben werden können und ein ganzzahligen Code zurückgegeben wird (in der Regel `0`).

Es ist in dieser Funktion, die wir Aufrufen der `square` Funktion mit dem Argument `12`.  F#-Compiler weist den Typ des `square` werden `int -> int` (d. h. eine Funktion, die akzeptiert ein `int` und erzeugt eine `int`).  Der Aufruf von `printfn` ist eine formatierte Druckfunktion befindlichen eine Formatzeichenfolge, ähnlich wie bei Programmiersprachen C-Format verwenden, Parameter, der den angegebenen, in der Formatzeichenfolge entspricht, und gibt dann das Ergebnis und eine neue Zeile.

## <a name="running-your-code"></a>Ausführen des Codes

Sie können den Code ausführen und Ergebnisse anzeigen, indem Sie auf **ausführen** aus dem Menü der obersten Ebene und dann **Starten ohne Debugging**.  Dies wird das Programm ohne Debuggen auszuführen und ermöglicht Ihnen, um die Ergebnisse anzuzeigen.

Jetzt sollte gedruckt an das Konsolenfenster, das Visual Studio für Mac per POP, um ausgelesen Folgendes angezeigt:

```
12 squared is 144!
```

Herzlichen Glückwunsch!  Erste f#-Projekts in Visual Studio für Mac erstellt haben, geschrieben, dass eine F#-Funktion die Ergebnisse der Aufrufe dieser Funktion gedruckt und führen Sie das Projekt, um einige Ergebnisse.

## <a name="using-f-interactive"></a>Verwenden von f# Interactive

Eine der besten Funktionen oder die Visual F#-Datenbanktools in Visual Studio für Mac ist das f# Interactive-Fenster.  Sie können Sie Code über an einen Prozess zu senden, Sie diesen Code aufrufen können und das Ergebnis interaktiv angezeigt.

Um zu beginnen, verwenden es, markieren Sie die `square` Funktion, die in Ihrem Code definiert.  Klicken Sie anschließend auf **bearbeiten** aus dem Menü der obersten Ebene.  Wählen Sie als Nächstes **Auswahl an f# Interactive senden**.  Dies führt den Code in der f# Interactive-Fenster.  Alternativ können Sie mit der rechten Maustaste auf die Auswahl und wählen Sie **Auswahl an f# Interactive senden**.  Daraufhin sollte das f# Interactive-Fenster mit den folgenden darin angezeigt werden:

```
>

val square : x:int -> int

>
```

Dies zeigt die gleiche Funktionssignatur für die `square` -Funktion, die Sie zuvor gesehen haben, wenn Sie über die Funktion gezeigt.  Da `square` ist nun in der f# Interactive-Prozess definiert, können Sie es mit unterschiedlichen Werten aufrufen:

```
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

Dies führt die Funktion, bindet das Ergebnis in einen neuen Namen `it`, und zeigt den Typ und Wert des `it`.  Beachten Sie, dass Sie jede Zeile mit beenden müssen `;;`.  Dies ist wie f# Interactive weiß, wenn der Funktionsaufruf abgeschlossen ist.  Sie können auch neue Funktionen in f# Interactive definieren:

```
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

Die oben genannten definiert eine neue Funktion `isOdd`, nimmt ein `int` und prüft, ob es ungerade ist!  Sie können diese Funktion, um festzustellen, was es mit unterschiedlichen Eingaben zurückgibt aufrufen.  Sie können Funktionen in Funktionsaufrufen aufrufen:

```
> isOdd (square 15);;
val it : bool = true
```

Sie können auch die [Pipe-Forward-Operator](../language-reference/symbol-and-operator-reference/index.md) pipeline den Wert in die zwei Funktionen für:

```
> 15 |> square |> isOdd;;
val it : bool = true
```

Der Pipe-Forward-Operator und vieles mehr, werden in späteren Lernprogrammen behandelt.

Dies ist nur einen Einblick in die Verwendungsmöglichkeiten mit f# Interactive.  Weitere Auschecken [Interaktive Programmierung mit F#-](../tutorials/fsharp-interactive/index.md).

## <a name="next-steps"></a>Nächste Schritte

Wenn Sie nicht bereits getan haben, sehen Sie sich die [Tour von F#-](../tour.md), die behandelt einige der wichtigsten Funktionen der Programmiersprache f#.  Er bieten Ihnen einen Überblick über die Funktionen von f#, und gibt ausreichend Codebeispiele, die Sie in Visual Studio für Mac kopieren und ausführen können.  Es gibt auch einige sehr hilfreiche externe Ressourcen, die Sie verwenden können, präsentiert, in der [F#-Handbuch](../index.md).

## <a name="see-also"></a>Siehe auch
 [Visual F#](../index.md)  
 [Einführung in F#](../tour.md)  
 [F#-Sprachreferenz](../language-reference/index.md)  
 [Typrückschluss](../language-reference/type-inference.md)  
 [Symbol und dem Operator-Referenz](../language-reference/symbol-and-operator-reference/index.md)  
