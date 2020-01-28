---
title: Das .NET Compiler Platform SDK (Roslyn APIs)
description: Erfahren Sie, wie das .NET Compiler Platform-SDK (auch als „Roslyn-APIs“ bezeichnet) verwendet wird, um den .NET-Code zu analysieren, Fehler zu erkennen und diese Fehler zu beheben.
ms.date: 10/10/2017
ms.custom: mvc
ms.openlocfilehash: a1ceb1d11cf846e67be2c6558978e01133e591da
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742738"
---
# <a name="the-net-compiler-platform-sdk"></a>.NET Compiler Platform-SDK

Compiler erstellen bei der Validierung der Syntax und Semantik eines Anwendungscodes ein detailliertes Modell davon. Basierend auf diesem Modell wird die ausführbare Ausgabe aus dem Quellcode erstellt. Zugriff auf dieses Modell wird durch das .NET Compiler Platform-SDK ermöglicht. Um die Produktivität zu steigern, greifen wir vermehrt auf Funktionen der integrierten Entwicklungsumgebung (IDE) zurück, wie IntelliSense, Refactoring, intelligentes Umbenennen, „Alle Verweise suchen“ und „Gehe zu Definition“. Zur Verbesserung unserer Codequalität nehmen wir Codeanalysetools und zur Unterstützung der Anwendungsentwicklung Codegeneratoren zu Hilfe. Je intelligenter diese Tools werden, desto umfangreicher wird auch der erforderliche Zugriff auf das Modell, das nur von Compilern bei der Verarbeitung des Anwendungscodes erstellt wird. Genau darin besteht das Hauptziel der Roslyn-APIs: Das Geheimnis um die Blackboxes zu lüften und Tools wie auch Endbenutzern die Nutzung der umfassenden Informationen zu ermöglichen, die bezüglich unseres Codes in den Compilern enthalten sind.
Anstatt eine nicht transparente Übersetzung von Quellcode in Objektcode bereitzustellen, werden Compiler durch Roslyn zu Plattformen: APIs, die Sie für codebezogene Aufgaben in Ihren Tools und Anwendungen einsetzen können.

## <a name="net-compiler-platform-sdk-concepts"></a>.NET Compiler Platform-SDK – Begriffe

Das .NET Compiler Platform-SDK vereinfacht die Erstellung von codeabhängigen Tools und Anwendungen um ein Vielfaches. Dieses schafft viele Möglichkeiten für Innovationen in Bereichen wie Metaprogrammierung, Codegenerierung und -transformation, die interaktive Verwendung der Programmiersprachen C# und Visual Basic und die Einbettung von C# und Visual Basic in domänenspezifische Sprachen.

Mit dem .NET Compiler Platform-SDK können Sie ***Analysetools*** und ***Codefehlerbehebungen*** erstellen, die Codierungsfehler finden und korrigieren. ***Analysetools*** analysieren die Syntax und Struktur des Codes und erkennen Praktiken, die korrigiert werden sollten. ***Codefehlerbehebungen*** stellen empfohlene Updates zur Behebung von Codierungsfehlern bereit, die von Analysetools gefunden werden. In der Regel werden ein Analysetool und die zugehörigen Codefehlerbehebungen in ein einzelnes Projekt gepackt.

Analysetools und Codefehlerbehebungen verwenden zur Codeanalyse statische Analysen. Sie führen den Code nicht aus oder bieten andere Vorteile in Bezug auf Tests. Sie können jedoch auf Verfahren hinweisen, die häufig zu Fehlern, zu Problemen bei der Codeverwaltung oder zu Verstößen gegen Standardrichtlinien führen.

Das .NET Compiler Platform-SDK stellt eine einzelne Gruppe von APIs zur Verfügung, mit denen Sie eine C#- oder Visual Basic-Codebasis untersuchen und analysieren können. Die Verwendung einer einzelnen Codebasis ermöglicht ein einfacheres Schreiben von Analysetools und Codefehlerbehebungen, indem die Syntax- und Semantikanalyse-APIs des .NET Compiler Platform-SDK genutzt werden. Durch den Wegfall der umfangreichen Aufgabe, die vom Compiler durchgeführte Analyse zu replizieren, können Sie sich auf die spezifischere Aufgabe konzentrieren, häufige Codierungsfehler für Ihr Projekt oder Ihre Bibliothek zu finden und zu beheben.

Ein weiterer nachrangiger Vorteil: Beim Laden in Visual Studio sind Ihre Analysetools und Codefehlerbehebungen kleiner und belegen deutlich weniger Speicher, als wenn Sie eine eigene Codebasis für die Analyse des Codes in einem Projekt schreiben würden. Da dieselben Klassen verwendet werden, die beim Compiler und in Visual Studio zum Einsatz kommen, können Sie eigene statische Analysetools erstellen. Dies bedeutet, dass Ihr Team Analysetools und Codefehlerbehebungen ohne spürbare Auswirkungen auf die Leistung von IDE verwenden kann.

Für das Schreiben von Analysetools und Codefehlerbehebungen gibt es drei Hauptszenarien:

1. [*Erzwingen von Codierungsstandards im Team*](#enforce-team-coding-standards)
1. [*Bereitstellen von Leitfäden mit Bibliothekspaketen*](#provide-guidance-with-library-packages)
1. [*Bereitstellen allgemeiner Leitfäden*](#provide-general-guidance)

## <a name="enforce-team-coding-standards"></a>Erzwingen von Codierungsstandards im Team

Viele Teams verfügen über Codierungsstandards, die durch Code Reviews bei anderen Teammitgliedern erzwungen werden. Die Effizienz dieses Prozesses kann durch Analysetools und Codefehlerbehebungen um ein Vielfaches erhöht werden. Code Reviews erfolgen, wenn ein Entwickler seine Arbeit mit anderen Mitgliedern des Teams teilt. In der Regel hat er viel Zeit in die Fertigstellung eines neuen Features investiert, bevor er Kommentare erhält. Dabei können Wochen vergehen, in denen er Gewohnheiten stärkt, die nicht den Praktiken des Teams entsprechen.

Während ein Entwickler Codes schreibt, werden Analysetools ausgeführt. Er erhält ein unmittelbares Feedback, das ihn direkt dazu animiert, dem Leitfaden zu folgen. Sobald er mit der Prototyperstellung beginnt, schafft er so Gewohnheiten zum Schreiben von konformen Codes. Wenn ein Review für das Feature durchgeführt werden kann, wurden sämtliche Standardrichtlinien erzwungen.

Teams können Analysetools und Codefehlerbehebungen erstellen, die nach den am häufigsten verwendeten Praktiken suchen, die gegen die Codierungspraktiken des Teams verstoßen. Diese können zur Erzwingung von Standards auf jedem Entwicklungscomputer installiert werden.

## <a name="provide-guidance-with-library-packages"></a>Bereitstellen von Leitfäden mit Bibliothekspaketen

NuGet bietet .NET-Entwicklern eine Vielzahl von Bibliotheken.
Diese stammen von Microsoft, Drittanbietern sowie von Communitymitgliedern und Freiwilligen. Diese Bibliotheken erhalten mehr Akzeptanz und höhere Bewertungen, wenn Entwickler mit diesen Bibliotheken erfolgreich sein können.

Neben der Dokumentation können Sie Analysetools und Codefehlerbehebungen bereitstellen, die häufige Verstöße gegen Ihre Bibliothek aufspüren und korrigieren. Diese unmittelbaren Korrekturen verhelfen Entwickler schneller zum Erfolg.

Sie können Analysetools und Codefehlerbehebungen mit Ihrer Bibliothek in NuGet packen. In diesem Szenario installiert jeder Entwickler, der Ihr NuGet-Paket installiert, auch das Paket des Analysetools. Alle Entwickler, die Ihre Bibliothek verwenden, erhalten sofort Richtlinien von Ihrem Team in Form eines unmittelbaren Feedbacks zu Fehlern und von Korrekturvorschlägen.

## <a name="provide-general-guidance"></a>Bereitstellen von allgemeinen Codierungsleitfäden

Die .NET-Entwicklercommunity hat basierend auf ihrem Erfahrungsschatz gut funktionierende Muster und Muster, die am besten vermieden werden sollten, ermittelt. Mehrere Communitymitglieder haben Analysetools erstellt, die diese empfohlenen Muster erzwingen. Mit fortschreitender Entwicklung haben wir erfahren, dass dem Ideenreichtum keine Grenzen gesetzt sind.

Diese Analysetools können im [Visual Studio Marketplace](https://marketplace.visualstudio.com/vs) hochgeladen und von Entwicklern über Visual Studio heruntergeladen werden. Benutzer, die mit der Sprache und Plattform noch nicht vertraut sind, lernen schnell akzeptierte Praktiken und erzielen so früher Produktivität, während sie Erfahrungen mit der .NET-Sprache sammeln. Mit der zunehmenden Verbreitung steigt auch die Wahrscheinlichkeit, dass diese Praktiken von der Community übernommen werden.

## <a name="next-steps"></a>Nächste Schritte

Das .NET Compiler Platform-SDK enthält die neuesten Sprachobjektmodelle für die Codegenerierung, die Analyse und das Refactoring. Dieser Abschnitt enthält einen konzeptionellen Überblick über das .NET Compiler Platform-SDK. Einzelheiten finden Sie in den Abschnitten „Schnellstarts“, „Beispiele“ und „Tutorials“.

In den folgenden fünf Themenbereichen erfahren Sie mehr über die Konzepte im .NET Compiler Platform-SDK:

- [Sehen Sie sich Code mit der Syntaxschnellansicht an.](syntax-visualizer.md)
- [Grundlegendes zum API-Modell von Compilern](compiler-api-model.md)
- [Arbeiten mit der Syntax](work-with-syntax.md)
- [Arbeiten mit der Semantik](work-with-semantics.md)
- [Arbeiten mit einem Arbeitsbereich](work-with-workspace.md)

Installieren Sie zunächst das **SDK für die .NET Compiler Platform**:

[!INCLUDE[interactive-note](~/includes/roslyn-installation.md)]

<!--

Turn this on as more of the conceptual content is in place:
- Try the [Quickstarts](quickstart/index.md) to create your first tutorial.
- Experiment with one of the [Tutorials](tutorials/index.md).
- Explore the [Samples](samples/index.md) to see some simple analyzers.
- Read the [Concepts](concepts/index.md) to understand the ideas behind analyzers and code fixes.

-->
