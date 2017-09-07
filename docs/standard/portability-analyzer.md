---
title: '.NET Portability Analyzer: .NET | Microsoft-Dokumentation'
description: Erfahren Sie, wie Sie mit dem Tool .NET Portability Analyzer bewerten, wie portabel Ihr Code zwischen den verschiedenen .NET-Implementierungen ist.
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 07/26/2017
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 0375250f-5704-4993-a6d5-e21c499cea1e
ms.translationtype: HT
ms.sourcegitcommit: 3155295489e1188640dae5aa5bf9fdceb7480ed6
ms.openlocfilehash: adb1971c14c8ff8c147dba378ae0e9a5bc0fb5ad
ms.contentlocale: de-de
ms.lasthandoff: 08/21/2017

---

# <a name="the-net-portability-analyzer"></a>.NET Portability Analyzer

Sollen Ihre Bibliotheken auf mehreren Plattformen einsetzbar sein? Möchten Sie wissen, wie viel Arbeit erforderlich ist, um Ihre Anwendung mit anderen .NET-Implementierungen kompatibel zu machen? [.NET Portability Analyzer](http://go.microsoft.com/fwlink/?LinkID=507467) ist ein Tool, das Ihnen durch die Analyse von Assemblys einen detaillierten Bericht zur Flexibilität Ihres Programms auf verschiedenen .NET-Implementierungen bietet. Portability Analyzer wird als Visual Studio-Extension und als Konsolen-App angeboten.

## <a name="new-targets"></a>Neue Ziele

* [.NET Core](https://dotnetfoundation.org/net-core): Besitzt einen modularen Aufbau, verwendet die parallele Ausführung und ist auf plattformübergreifende Szenarios ausgerichtet. Die parallele Ausführung ermöglicht Ihnen die Übernahme neuer Versionen von .NET Core, ohne andere Apps zu beeinträchtigen.
* [ASP.NET Core](https://dotnetfoundation.org/asp-net-core): Ist ein modernes Webframework, das auf .NET Core beruht, sodass Entwickler von denselben Vorteilen profitieren.
* [Universelle Windows-Plattform](https://blogs.msdn.microsoft.com/dotnet/2014/04/24/net-native-performance): Verbessern Sie die Leistung Ihrer Windows Store-Apps, die mithilfe der statischen Kompilierung von .NET Native auf X64- und ARM-Computern ausgeführt werden. 
* .NET Core + Plattformerweiterungen: dazu zählen die .NET Core-APIs zusätzlich zu anderen APIs in der .NET-Umgebung wie z.B. WCF, ASP.NET Core, FSharp und Azure.
* .NET Standard + Plattformerweiterungen: dazu zählen die .NET Standard-APIs zusätzlich zu anderen .NET-Umgebungen wie z.B. WCF, ASP.NET Core, FSharp und Azure.

## <a name="how-to-use-portability-analyzer"></a>Gewusst wie: Verwenden von Portability Analyzer

Um mit der Verwendung von .NET Portability Analyzer zu beginnen, müssen Sie die Erweiterung zunächst aus der [Visual Studio Gallery](http://go.microsoft.com/fwlink/?LinkID=507467) herunterladen. Er wird in Visual Studio 2015 und Visual Studio 2017 unterstützt. Sie können ihn in Visual Studio über **Analysieren** > **Einstellungen des Portability Analyzer** konfigurieren und Ihre Zielplattformen auswählen.

![Screenshot zur Portabilität](./media/portability-analyzer/portability-screenshot.png)

Um das gesamte Projekt zu analysieren, klicken Sie mit der rechten Maustaste im **Projektmappen-Explorer** auf Ihr Projekt, und wählen Sie **Assemblyportabilität analysieren** aus. Wechseln Sie andernfalls zum Menü **Analysieren**, und wählen Sie **Assemblyportabilität analysieren**. Wählen Sie dort die ausführbare Datei oder DLL-Datei des Projekts aus.

![Projektmappen-Explorer für Portabilität](./media/portability-analyzer/portability-solution-explorer.png)

Nach dem Ausführen der Analyse wird Ihnen der .NET-Portabilitätsbericht angezeigt. Nur Typen, die von einer Zielplattform nicht unterstützt werden, sind in der Liste enthalten, und Sie können Empfehlungen auf der Registerkarte **Meldungen** in der **Fehlerliste** anzeigen. Zudem können Sie direkt von der Registerkarte **Meldungen** zu Problembereichen springen.

![Portabilitätsbericht](./media/portability-analyzer/portability-report.png)

Sie möchten Visual Studio nicht verwenden? Sie können Portability Analyzer auch von der Befehlszeile aus verwenden. Laden Sie einfach den [API Portability Analyzer](http://www.microsoft.com/download/details.aspx?id=42678) herunter.

*   Geben Sie den folgenden Befehl an, um das aktuelle Verzeichnis zu analysieren: `\...\ApiPort.exe analyze -f .`
*   Um eine bestimmte Liste von DLL-Dateien zu analysieren, geben Sie den folgenden Befehl ein: `\...\ApiPort.exe analyze -f first.dll -f second.dll -f third.dll`

Der .NET-Portabilitätsbericht wird als Excel-Datei (*.xlsx*) im aktuellen Verzeichnis gespeichert. Die Registerkarte **Details** in der Excel-Arbeitsmappe enthält weitere Informationen.

Weitere Informationen zum .NET Portability Analyzer, finden Sie auf der [GitHub-Dokumentation](https://github.com/Microsoft/dotnet-apiport#documentation) und im Channel 9-Video [Eine kurze Betrachtung des .NET Portability Analyzer](https://channel9.msdn.com/Blogs/Seth-Juarez/A-Brief-Look-at-the-NET-Portability-Analyzer).

