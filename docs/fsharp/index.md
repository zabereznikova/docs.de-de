---
title: Leitfaden für F#
description: Dieses Handbuch enthält einen Überblick über die verschiedenen Lernmaterialien für f#, funktionalen Programmiersprachen, die auf .NET ausgeführt wird.
author: jackfoxy
ms.date: 03/19/2018
ms.openlocfilehash: 393214a5da7445d8ee3dced844da8592f4ca6d31
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="f-guide"></a>Leitfaden für F#

F# ist eine funktionale Programmiersprache, die auf .NET ausgeführt wird. Zudem ist eine vollständige Unterstützung für Objekte, können Sie mit Blend funktionale und Objekt-Programmierung pragmatisches Lösungen für Probleme.

```fsharp
open System // Get access to functionality in System namespace.

// Function: takes a name and produces a greeting.
let getGreeting name =
    sprintf "Hello, %s! Isn't F# great?" name

// Use the EntryPoint attribute to run the program.
[<EntryPoint>]
let main args =
    // Define a list of names
    let names = [| "Don"; "Julia"; "Xi" |]
    
    // Print a fun greeting for each name!
    names
    |> Array.map getGreeting
    |> Array.iter (fun greeting -> printfn "%s" greeting)

    0
```

F# ist zur Steigerung der Produktivität im Wesentlichen. Die toolunterstützung für f# ist weit verbreitete und vollständige erweiterte Funktionen.

## <a name="learning-f"></a>Learning [F#] #

[Tour durch f#](tour.md) vermittelt einen Überblick über die wichtigsten Sprachfunktionen mit vielen Codebeispielen. Dies wird empfohlen, wenn Sie mit dem f# vertraut sind und ein Verhalten für die Funktionsweise der Sprache abgerufen werden soll.

[Erste Schritte mit f# in Visual Studio](get-started/get-started-visual-studio.md) Wenn Sie auf Windows und die vollständige Visual Studio-IDE (Integraded Development Environment)-Erfahrung werden soll.

[Erste Schritte mit f# in Visual Studio für Mac](get-started/get-started-with-visual-studio-for-mac.md) Wenn Sie MacOS und eine Visual Studio-IDE verwendet werden soll.

[Erste Schritte mit f# in Visual Studio Code](get-started/get-started-vscode.md) Wenn Sie eine einfache, plattformübergreifende und Feature-packed IDE auftreten.

[Erste Schritte mit f# mit der .NET Core-CLI](get-started/get-started-command-line.md) , wenn Sie die Befehlszeilentools verwenden möchten.

[Erste Schritte mit F#- und Xamarin](https://docs.microsoft.com/xamarin/cross-platform/platform/fsharp/) für die mobile-Programmierung mit f#.

## <a name="references"></a>Verweise

[F#-Sprachreferenz](language-reference/index.md) ist die offizielle, eine umfassende Referenz für alle F#-Funktionen. Jeder Artikel erklärt die Syntax und zeigt Codebeispiele. Die Filterleiste können im Inhaltsverzeichnis Sie um bestimmte Artikeln zu suchen.

[Referenz zur F#-Kernbibliothek](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference) ist die API-Referenz für die f#-Kernbibliothek.


## <a name="additional-guides"></a>Zusätzliche Anleitungen

[F# für lustige und Gewinn](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/) ist eine umfassende und detaillierte Book auf learning f#. Inhalt und der Autor sind von f#-Community geliebten. Die Zielgruppe wird in erster Linie Entwicklern eine objektorientierte Programmierung im Hintergrund.

[F#-Programmierung Wikibook](https://en.wikibooks.org/wiki/F_Sharp_Programming) ist eine Wikibook zu Lernressourcen f#. Es ist auch ein Produkt mit der f#-Community. Die Zielgruppe wird Personen, die f# mit ein wenig objektorientierte Programmierung im Hintergrund.

## <a name="learn-f-through-videos"></a>Lernen F#-videos

[F#-Lernprogramm auf YouTube](https://www.youtube.com/watch?v=c7eNDJN758U) ist eine gute Einführung in f# mithilfe von Visual Studio, viele gute Beispiele dafür im Verlauf von 1,5 Stunden angezeigt. Die Zielgruppe ist Visual Studio-Entwickler, die für f# neu sind.

[Einführung in die Programmierung mit F#-](https://www.youtube.com/watch?v=Teak30_pXHk&list=PLEoMzSkcN8oNiJ67Hd7oRGgD1d4YBxYGC) ist eine hervorragende Videoreihe, die Visual Studio-Code als der Haupt-Editor verwendet. Die Videoreihe aus einem unbenannten beginnt und endet mit einer textbasierten RPG-Video-Spiel erstellen. Die Zielgruppe ist Entwickler, die dann Visual Studio Code (oder eine einfache IDE) und sind für f# neu.

[Neues in Visual Studio 2017 für f# für Entwickler](https://www.linkedin.com/learning/what-s-new-in-visual-studio-2017-for-f-sharp-for-developers) ist ein video Kurs, die einige der neueren Funktionen für f# in Visual Studio 2017 anzeigt. Die Zielgruppe ist Visual Studio-Entwickler, die für f# neu sind.

## <a name="other-useful-resources"></a>Andere nützliche Ressourcen

Die [f# Ausschnitte Website](http://www.fssnip.net) enthält eine umfassende Reihe von Codeausschnitte, so ziemlich alles in f# von Neueinsteiger bis hin zu fortschrittlichen Ausschnitte Vorgang zeigt.

Die [f# Software Foundation Slack](http://fsharp.org/guides/slack/) eignet sich hervorragend für Anfänger und Experten gleichermaßen, sehr aktiv ist und über einige der weltweit besten F#-Programmierer chatten. Es wird dringend empfohlen, verknüpfen.

## <a name="the-f-software-foundation"></a>Die F# Software Foundation

Obwohl Microsoft den primären Entwickler der Programmiersprache f# und die zugehörigen Tools in Visual Studio ist, wird f# auch von einer unabhängigen Foundation, die F#-Software Foundation (FSSF) gesichert.

Das Ziel der F# Software Foundation ist, die Programmiersprache F# zu fördern, zu schützen und weiterzuentwickeln sowie das Wachstum einer vielfältigen und internationalen Community von F#-Programmierern zu unterstützen.

Um mehr zu erfahren und mitzumachen, gehen Sie unter [fsharp.org](http://fsharp.org). Es ist kostenlos zu verknüpfen, und das Netzwerk des F#-Entwickler in die Grundlage etwas, das Sie nicht verpassen möchten!
