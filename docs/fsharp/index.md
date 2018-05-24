---
title: Leitfaden für F#
description: Dieses Handbuch enthält einen Überblick über die verschiedenen Lernmaterialien für F#, funktionalen Programmiersprachen, die auf .NET ausgeführt wird.
author: jackfoxy
ms.date: 03/19/2018
ms.openlocfilehash: cb829e904c006467e1470752b4fe8757ca694b05
ms.sourcegitcommit: 895c7602386a6dfe7ca4facce3d965b27e5c6e87
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2018
---
# <a name="f-guide"></a>Leitfaden für F#

F# ist eine funktionale Programmiersprache, die auf .NET ausgeführt wird. Die vollständige Unterstützung für Objekte lässt Sie  funktionale und objektorientierte Programmierung für pragmatische Lösungen für jedes Problem vermischen.

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

Im Fokus von F# steht die Steigerung der Produktivität. Die toolunterstützung für F# ist weit verbreitete und voller moderner Funktionen.

## <a name="learning-f"></a>Learning [F#] #

[Tour durch F#](tour.md) vermittelt einen Überblick über die wichtigsten Sprachfunktionen mit vielen Codebeispielen. Dies wird empfohlen, wenn Sie mit F# beginnen und sich mit der Funktionsweise der Sprache vertraut machen wollen.

[Erste Schritte mit F# in Visual Studio](get-started/get-started-visual-studio.md) , wenn Sie für Windows entwickeln und die vollständige Visual Studio-IDE (Integraded Development Environment)-Erfahrung erleben wollen.

[Erste Schritte mit F# in Visual Studio für Mac](get-started/get-started-with-visual-studio-for-mac.md) , wenn Sie MacOS nutzen und eine Visual Studio-IDE verwendet wollen.

[Erste Schritte mit F# in Visual Studio Code](get-started/get-started-vscode.md) , wenn Sie eine einfache, plattformübergreifende und funktionsreiche IDE nutzen wollen.

[Erste Schritte mit F# mit der .NET Core-CLI](get-started/get-started-command-line.md) , wenn Sie die Befehlszeilentools verwenden möchten.

[Erste Schritte mit F#- und Xamarin](https://docs.microsoft.com/xamarin/cross-platform/platform/fsharp/) für die mobile-Programmierung mit F#.

[F# für Azure-Notebooks](https://notebooks.azure.com/Microsoft/libraries/samples/html/FSharp%20for%20Azure%20Notebooks.ipynb) ist ein Lernprogramm für das Erlernen von F# in einem kostenlosen, gehosteten Jupyter Notebook.

## <a name="references"></a>Verweise

[F#-Sprachreferenz](language-reference/index.md) ist die offizielle, umfassende Referenz über alle F#-Funktionen. Jeder Artikel erklärt die Syntax und zeigt Codebeispiele. Nutzen Sie die Filterleiste im Inhaltsverzeichnis um bestimmte Artikeln zu suchen.

[Referenz zur F#-Kernbibliothek](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference) ist die API-Referenz für die F#-Kernbibliothek.


## <a name="additional-guides"></a>Zusätzliche Anleitungen

[F# für Spaß und Gewinn](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/) ist ein umfassendes und detailreiches Buch um F# zu lernen. Inhalt und Autor werden von der F#-Community geliebten. Die Zielgruppe sind in erster Linie Entwickler mit objektorientierter Programmierung als Hintergrund.

[F#-Programmierung Wikibook](https://en.wikibooks.org/wiki/F_Sharp_Programming) ist eine Wikibook zum F# lernen. Es ist ebenfalls ein Produkt der F#-Community. Die Zielgruppe sind Personen, die neu bei F# sind und ein wenig objektorientierte Programmierung als Hintergrund haben.

## <a name="learn-f-through-videos"></a>Lernen F#-Videos

[F#-Lernprogramm auf YouTube](https://www.youtube.com/watch?v=c7eNDJN758U) ist eine gute Einführung in F#. Mithilfe von Visual Studio und vielen guten Beispielen wird hier innerhalb von 1,5 Stunden ein Einblick gezeigt. Die Zielgruppe sind Visual Studio-Entwickler, die mit F# beginnen.

[Einführung in die Programmierung mit F#-](https://www.youtube.com/watch?v=Teak30_pXHk&list=PLEoMzSkcN8oNiJ67Hd7oRGgD1d4YBxYGC) ist eine hervorragende Videoreihe, die Visual Studio-Code als der Haupt-Editor verwendet. Die Videoreihe startet von Grund auf und endet mit der Erstellung eines textbasierten RPG-Videospiels. Die Zielgruppe sind Entwickler, die Visual Studio Code (oder eine einfache IDE) nutzen wollen und mit F# beginnen.

[Neues in Visual Studio 2017 für F# für Entwickler](https://www.linkedin.com/learning/what-s-new-in-visual-studio-2017-for-f-sharp-for-developers) ist ein Videkours, der die neueren Funktionen von F# in Visual Studio 2017 zeigt. Die Zielgruppe sind Visual Studio-Entwickler, die mit F# beginnen.

## <a name="other-useful-resources"></a>Andere nützliche Ressourcen

Die [F# Ausschnitte Website](http://www.fssnip.net) enthält eine umfassende Reihe von Codeausschnitten. Interessant für alle Entwickler, von F#-Neulingen bis Fortgeschrittene.

Die [F# Software Foundation Slack](http://fsharp.org/guides/slack/) eignet sich hervorragend für Anfänger und Experten gleichermaßen. Sie ist sehr aktiv und bietet einige der weltweit besten F#-Programmierer für einen Chat. Es empfehlen dringend die Teilnahme.

## <a name="the-f-software-foundation"></a>Die F# Software Foundation

Obwohl Microsoft der primäre Entwickler der Programmiersprache F# und die der dazugehörigen Tools in Visual Studio ist, wird F# auch von einer unabhängigen Foundation, die F#-Software Foundation (FSSF) gesichert.

Das Ziel der F# Software Foundation ist, die Programmiersprache F# zu fördern, zu schützen und weiterzuentwickeln sowie das Wachstum einer vielfältigen und internationalen Community von F#-Programmierern zu unterstützen.

Um mehr zu erfahren und mitzumachen, gehen Sie auf [fsharp.org](http://fsharp.org). Mitmachen ist kostenlos und das Netzwerk der F#-Entwickler der Foundation ist etwas, das Sie garantiert nicht verpassen möchten!
