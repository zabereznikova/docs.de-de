---
title: Erste Schritte mit f# in Visual Studio
description: Informationen Sie zum Verwenden von f# in Visual Studio.
ms.date: 02/13/2017
ms.openlocfilehash: 22fbe8086ec133605e1d9b4b28e524fe2ed8ac28
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34728533"
---
# <a name="get-started-with-f-in-visual-studio"></a>Erste Schritte mit f# in Visual Studio

F# und Visual f#-Tools werden in der Visual Studio-IDE unterstützt.  Um zu beginnen, sollten Sie [Herunterladen von Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs), sofern Sie noch nicht geschehen.  In diesem Artikel verwendet 2017 Community-Edition von Visual Studio, aber Sie können f# mit der Version Ihrer Wahl.

## <a name="installing-f"></a>Installieren [F#] #

Wenn beim Herunterladen von Visual Studio zum ersten Mal werden zunächst im Visual Studio-Installer installiert.  Installieren Sie eine beliebige Version von Visual Studio 2017 vom Installationsprogramm ein. Wenn Sie bereits installiert haben, klicken Sie auf **ändern**.

Als Nächstes sehen Sie eine Liste von Arbeitslasten. Sie können f# mithilfe einer der folgenden arbeitsauslastungen installieren:

|Arbeitsauslastung|Aktion|
|--------|------|
| Plattformübergreifende .NET Core-Entwicklung | Keine Aktion - f# wird standardmäßig installiert. |
| ASP.NET und Webentwicklung | Keine Aktion - f# wird standardmäßig installiert. |
| Azure-Entwicklung | Keine Aktion - f# wird standardmäßig installiert. |
| Mobile Entwicklung mit .NET | Keine Aktion - f# wird standardmäßig installiert. |
| Data Science und analytische Anwendungen | Keine Aktion - f# wird standardmäßig installiert. |
| .NET-Desktopentwicklung | Wählen Sie **desktop f#-sprachunterstützung** aus der rechten Seite |
| Datenspeicherung und -verarbeitung | Wählen Sie **desktop f#-sprachunterstützung** aus der rechten Seite |

Klicken Sie anschließend auf **ändern** in der unteren rechten Ecke.  Dies installiert alles, was, die Sie ausgewählt haben.  Anschließend können Sie Visual Studio 2017 mit f#-sprachunterstützung öffnen, indem Sie auf **starten**.

## <a name="creating-a-console-application"></a>Erstellen einer Konsolenanwendung

Eines der grundlegendsten Projekte in Visual Studio ist die Konsolenanwendung.  Und so gehen Sie dabei vor.  Nachdem Sie Visual Studio geöffnet ist:

1. Auf der **Datei** Sie im Menü **neu**, und wählen Sie dann **Projekt**.

2.  In das neue Projekt im Dialogfeld unter **Vorlagen**, sehen Sie **Visual f#**.  Wählen Sie diese Option, um die F#-Vorlagen anzeigen.

3. Wählen Sie entweder **.NET Core-Konsolen-app** oder **Konsolen-app**.

3. Wählen Sie die **Okay** Schaltfläche, um die f#-Projekt zu erstellen!  Jetzt sollte eine f#-Projekt im Projektmappen-Explorer angezeigt werden.

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

Sie können der Code ausgeführt und Ergebnisse durch Drücken von **Strg + f5**.  Dies wird das Programm ohne Debuggen auszuführen und ermöglicht Ihnen, um die Ergebnisse anzuzeigen.  Alternativ können Sie auch die **Debuggen** Menü der obersten Ebene in Visual Studio und wählen Sie **Starten ohne Debugging**.

Jetzt sollte gedruckt an das Konsolenfenster, das Visual Studio per POP, um ausgelesen Folgendes angezeigt:

```
12 squared is 144!
```

Herzlichen Glückwunsch!  Erste f#-Projekts in Visual Studio erstellten haben, geschrieben, dass eine F#-Funktion die Ergebnisse der Aufrufe dieser Funktion gedruckt und führen Sie das Projekt, um einige Ergebnisse.

## <a name="next-steps"></a>Nächste Schritte

Wenn Sie nicht bereits getan haben, sehen Sie sich die [Tour von F#-](../tour.md), die behandelt einige der wichtigsten Funktionen der Programmiersprache f#.  Er bieten Ihnen einen Überblick über die Funktionen von f#, und gibt ausreichend Codebeispiele, die Sie in Visual Studio kopieren und ausführen können.  Es gibt auch einige sehr hilfreiche externe Ressourcen, die Sie verwenden können, präsentiert, in der [F#-Handbuch](../index.md).

## <a name="see-also"></a>Siehe auch
 [Visual F#](index.md)  
 [Einführung in F#](../tour.md)  
 [F#-Sprachreferenz](../language-reference/index.md)  
 [Typrückschluss](../language-reference/type-inference.md)  
 [Symbol und dem Operator-Referenz](../language-reference/symbol-and-operator-reference/index.md)  
