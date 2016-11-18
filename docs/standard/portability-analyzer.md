---
title: .NET Portability Analyzer | .NET
description: Erfahren Sie, wie Sie mit dem Tool .NET Portability Analyzer bewerten, wie portabel Ihr Code zwischen den verschiedenen .NET-Plattformen ist.
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
manager: wpickett
ms.date: 07/05/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 0375250f-5704-4993-a6d5-e21c499cea1e
translationtype: Human Translation
ms.sourcegitcommit: 8599be1eadcd6f005ef344bf173e8c06fce80725
ms.openlocfilehash: 9e35fd4dff15cec688ee11f98682eb7cb96e9403

---

# <a name="the-net-portability-analyzer"></a>.NET Portability Analyzer

Sollen Ihre Bibliotheken auf mehreren Plattformen einsetzbar sein? Möchten Sie wissen, wie viel Arbeit erforderlich ist, um Ihre Anwendung mit anderen .NET-Plattformen kompatibel zu machen? [.NET Portability Analyzer](http://go.microsoft.com/fwlink/?LinkID=507467) ist ein Tool, das Ihnen durch die Analyse von Assemblys einen detaillierten Bericht zur Flexibilität Ihres Programms auf verschiedenen .NET-Plattformen bietet. Portability Analyzer wird als Visual Studio-Extension und als Konsolen-App angeboten.

## <a name="new-targets"></a>Neue Ziele

*   [.NET Core](https://www.dotnetfoundation.org/netcore): Besitzt einen modularen Aufbau, verwendet die parallele Ausführung und ist auf plattformübergreifende Szenarios ausgerichtet. Die parallele Ausführung ermöglicht Ihnen die Übernahme neuer Versionen von .NET Core, ohne andere Apps zu beeinträchtigen.
*   [ASP.NET Core](https://www.dotnetfoundation.org/aspnet-core): Ist ein modernes Webframework, das auf .NET Core beruht, sodass Entwickler von denselben Vorteilen profitieren.
*   [.NET Native](https://blogs.msdn.microsoft.com/dotnet/2014/04/24/net-native-performance): Verbessert die Leistung Ihrer Windows Store-Apps, die mithilfe der statischen Kompilierung von .NET Native auf X64- und ARM-Computern ausgeführt werden.

## <a name="how-to-use-portability-analyzer"></a>Gewusst wie: Verwenden von Portability Analyzer

Um mit der Verwendung von .NET Portability Analyzer zu beginnen, müssen Sie die Erweiterung zunächst aus der [Visual Studio Gallery](http://go.microsoft.com/fwlink/?LinkID=507467) herunterladen. Sie können sie in Visual Studio über **Extras** > **Optionen** > **.NET Portability Analyzer** konfigurieren und Ihre Zielplattformen auswählen. Verwenden Sie vorerst ASP.NET Core als Proxy für alle .NET Core-basierten Plattformen (z.B. [Windows 10 .NET-UAP-Apps](http://blogs.windows.com/buildingapps/2015/03/02/a-first-look-at-the-windows-10-universal-app-platform/)).

![Screenshot zur Portabilität](./media/portability-analyzer/portability-screenshot.png)

Um das gesamte Projekt zu analysieren, klicken Sie mit der rechten Maustaste im Projektmappen-Explorer**** auf Ihr Projekt, und wählen Sie **Analysieren** > **Assemblyportabilität analysieren** aus. Wechseln Sie andernfalls zum Menü **Analysieren**, und wählen Sie **Assemblyportabilität analysieren**. Wählen Sie dort die ausführbare Datei oder DLL-Datei des Projekts aus.

![Projektmappen-Explorer für Portabilität](./media/portability-analyzer/portability-solution-explorer.png)

Nach dem Ausführen der Analyse wird Ihnen der .NET-Portabilitätsbericht angezeigt. Nur Typen, die von einer Zielplattform nicht unterstützt werden, sind in der Liste enthalten, und Sie können Empfehlungen auf der Registerkarte **Meldungen** in der **Fehlerliste** anzeigen. Zudem können Sie direkt von der Registerkarte **Meldungen** zu Problembereichen springen.

![Portabilitätsbericht](./media/portability-analyzer/portability-report.png)

Sie möchten Visual Studio nicht verwenden? Sie können Portability Analyzer auch von der Befehlszeile aus verwenden. Laden Sie einfach den [API Portability Analyzer](http://www.microsoft.com/download/details.aspx?id=42678) herunter.

*   Geben Sie den folgenden Befehl an, um das aktuelle Verzeichnis zu analysieren: `\...\ApiPort.exe .`
*   Um eine bestimmte Liste von DLL-Dateien zu analysieren, geben Sie den folgenden Befehl ein: `\...\ApiPort.exe first.dll second.dll third.dll`

Der .NET-Portabilitätsbericht wird als Excel-Datei (*.xlsx*) im aktuellen Verzeichnis gespeichert. Die Registerkarte **Details** in der Excel-Arbeitsmappe enthält weitere Informationen.

Weitere Informationen zu .NET Portability Analyzer finden Sie im Artikel [Verwenden von vorhandenem Code auf verschiedenen .NET-Plattformen](https://blogs.msdn.microsoft.com/dotnet/2014/08/06/leveraging-existing-code-across-net-platforms/) im .NET-Blog.



<!--HONumber=Nov16_HO3-->


