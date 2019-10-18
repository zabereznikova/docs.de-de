---
title: Portieren von Code von .NET Framework auf .NET Core
description: Verstehen Sie den Portiervorgang und entdecken Sie Tools, die Ihnen beim Portieren eines .NET Framework-Projekts zu .NET Core behilflich sein können.
author: cartermp
ms.date: 09/13/2019
ms.custom: seodec18
ms.openlocfilehash: c349f7df3726e7a9814e5ad5e738742ab1bb9ff8
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522988"
---
# <a name="port-your-code-from-net-framework-to-net-core"></a>Portieren Ihres Codes von .NET Framework auf .NET Core

Wenn Code auf .NET Framework ausgeführt wird, sind Sie vielleicht daran interessiert, Ihren Code auch auf .NET Core auszuführen. Dieser Artikel enthält eine Übersicht über den Portiervorgang und eine Liste der Tools, die beim Portieren Ihres Codes auf .NET Core hilfreich sein können.

## <a name="overview-of-the-porting-process"></a>Übersicht über den Portiervorgang

Dies ist die Vorgehensweise, die wir zur Portierung Ihres Projekts auf .NET Core empfehlen. Jeder Schritt in dieser Vorgehensweise wird in weiteren Artikeln genauer erläutert.

1. Identifizieren Sie sich und weisen Sie sich für Ihre Drittanbieter-Abhängigkeiten aus.

   Dieser Schritt beinhaltet das Verständnis, welche Drittanbieterkomponenten erforderlich sind, welche Abhängigkeiten von diesen Komponenten bestehen, wie Sie überprüfen können, ob die Komponenten auch auf .NET Core ausgeführt werden können, und welche Maßnahmen Sie ergreifen können, falls dem nicht so ist. Darüber hinaus wird erläutert, wie Sie erforderliche Komponenten zum Format [PackageReference](/nuget/consume-packages/package-references-in-project-files) migrieren können, das in .NET Core verwendet wird.

2. Legen Sie für alle zu portierenden Projekte .NET Framework 4.7.2 oder höher als neues Ziel fest.

   Durch diesen Schritt wird sichergestellt, dass Sie API-Alternativen für bestimmte .NET Framework-Ziele verwenden können, falls .NET Core eine bestimmte API nicht unterstützt.

3. Verwenden Sie das [Analysetool für .NET-Portierbarkeit](../../standard/analyzers/portability-analyzer.md), um Ihre Assemblys zu analysieren, und um einen Plan zum Portieren auf Grundlage der Ergebnisse zu entwickeln.

   Das API Portability Analyzer-Tool analysiert Ihre kompilierten Assemblys und generiert einen Bericht, der eine allgemeine Zusammenfassung zur Portabilität und eine Aufschlüsselung zu jeder verwendeten API anzeigt, die nicht für die öffentliche Oberfläche der .NET Core-Zielplattform verfügbar ist. Sie können diesen Bericht zusammen mit einer Analyse Ihrer Codebase verwenden, um einen Plan zum Portieren Ihres Codes zu entwickeln.

4. Nachdem Sie die Projektdatei in Ihre .NET Core-Zielversion konvertiert haben, können Sie mit dem Roslyn-basierten [.NET API-Analysetool](../../standard/analyzers/api-analyzer.md) APIs ermitteln, die auf einigen Plattformen <xref:System.PlatformNotSupportedException> sowie einige andere potenzielle Kompatibilitätsprobleme auslösen.

5. Portieren Sie Ihre Testcodes.

   Die Portierung auf .NET Core stellt eine erhebliche Änderung Ihrer Codebase dar, deshalb wird dringend empfohlen, Ihre Tests zu portieren. Auf diese Weise können Sie Tests ausführen, wenn Sie Ihren Code portieren. MSTest, xUnit und NUnit bieten Unterstützung für .NET Core.

6. Führen Sie Ihren Plan zum Portieren aus!

Die folgende Liste enthält Tools, die während der Portierung nützlich sein könnten:

- .NET Portability Analyzer: [Befehlszeilentool](https://github.com/Microsoft/dotnet-apiport/releases) oder [Visual Studio-Erweiterung](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer). Mit diesem Tool kann ein Bericht generiert werden, der Aufschluss über die Portierbarkeit Ihres Codes von .NET Framework auf Ihre .NET Core-Zielplattform gibt. In diesem Bericht werden der Typ und die APIs, die auf der .NET Core-Zielplattform fehlen, nach Assembly aufgeschlüsselt. Weitere Informationen finden Sie unter [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md). Es wird empfohlen, .NET Portability Analyzer vor dem Portieren auszuführen, um eventuelle Lücken bei den fehlenden APIs auf bestimmten öffentlichen Oberflächen der .NET-Zielplattform zu finden.
- .NET API-Analysetool: Hierbei handelt es sich um ein Roslyn-Analysetool, das die .NET Standard-API, die auf einigen Plattformen <xref:System.PlatformNotSupportedException> auslöst, Aufrufe von veralteten APIs und potenzielle Kompatibilitätsrisiken für C#-APIs auf verschiedenen Plattformen erkennt. Weitere Informationen finden Sie unter [.NET API-Analysetool](../../standard/analyzers/api-analyzer.md). Dieses Analysetool ist hilfreich, um Unterschiede beim Laufzeitverhalten auf den verschiedenen Plattformen zu ermitteln, nachdem Sie bereits Ihr .NET Core-Projekt erstellt haben.
- Reverse Package Search – ein [nützlicher Webdienst](https://packagesearch.azurewebsites.net), mit dem Sie einen Typ suchen können und Pakete finden können, die diesen Typ enthalten.

Darüber hinaus können Sie mit dem Tool [CsprojToVs2017](https://github.com/hvanbakel/CsprojToVs2017) versuchen, kleinere Lösungen oder einzelne Projekte auf das .NET Core-Projektdateiformat zu portieren.

> [!WARNING]
> CsprojToVs2017 ist ein Drittanbietertool. Es kann nicht garantiert werden, dass das Tool für all Ihre Projekte funktioniert, und es kann zu subtilen Änderungen bei Verhalten kommen, von dem Sie abhängig sind. CsprojToVs2017 sollte als _Ausgangspunkt_ verwendet werden, um grundlegende Elemente zu automatisieren. Es handelt sich nicht um ein garantierte Lösung zum Migrieren von Projektdateiformaten.

>[!div class="step-by-step"]
>[Nächste](net-framework-tech-unavailable.md)
