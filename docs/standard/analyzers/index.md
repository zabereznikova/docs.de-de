---
title: Die auf Roslyn basierenden Analysetools – .NET
description: Erfahren Sie mehr zu auf Roslyn basierenden Analysetools, die Probleme erkennen und Problembehebungen vorschlagen.
keywords: .NET, .NET Core
author: billwagner
ms.author: billwagner
ms.date: 01/24/2018
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.openlocfilehash: 8c6524716ba403bc426df8dc33e64b8b2934d3d7
ms.sourcegitcommit: 3a96c706e4dbb4667bf3bf37edac9e1666646f93
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2018
---
# <a name="the-roslyn-based-analyzers"></a>Die auf Roslyn basierenden Analysetools

Auf Roslyn basierende Analysetools verwenden das .NET Compiler SDK (Roslyn-APIs), um den Quellcode Ihres Projekts zu analysieren, um Probleme zu finden und Korrekturen vorzuschlagen. Unterschiedliche Analysetools suchen nach verschiedenen Klassen von Problemen, angefangen bei Methoden, die wahrscheinlich Fehler verursachen, bis hin zu Sicherheitsaspekten bei der API-Kompatibilität.

Auf Roslyn basierende Analysetools funktionieren sowohl interaktiv als auch während der Builderstellung. Das Analysetool bietet in Visual Studio oder in Befehlszeilenbuilds unterschiedliche Hilfen.

Während Sie Code in Visual Studio bearbeiten, werden die Analysetools bei der Durchführung von Änderungen ausgeführt und erfassen dabei mögliche Fehler, sobald Sie Code erstellen, der Probleme verursacht. Probleme werden durch Wellenlinien unter einem Problem markiert. In Visual Studio wird eine Glühbirne angezeigt. Wenn Sie darauf klicken, schlägt das Analysetool mögliche Problembehebungen vor. Wenn Sie das Projekt erstellen – entweder in Visual Studio oder über die Befehlszeile – wird der gesamte Quellcode analysiert, und das Analysetool stellt eine vollständige Liste möglicher Probleme bereit. Die folgende Abbildung zeigt ein Beispiel.

![Probleme, die vom Framework Analyzer gemeldet werden.](./media/framework-analyzers-2.png)

Die auf Roslyn basierenden Analysetools melden mögliche Probleme anhand des Schweregrads des Problems als Fehler, Warnungen oder Informationen.

Sie installieren auf Roslyn basierende Analysetools in Ihrem Projekt als NuGet-Pakete. Das konfigurierte Analysetool sowie Einstellungen für jedes Analysetool werden wiederhergestellt und auf einem beliebigen Computer eines Entwicklers für diese Projekt ausgeführt.

> [!NOTE]
> Die Benutzererfahrung für auf Roslyn basierenden Analysetools unterscheidet sich von den Codeanalysebibliotheken, wie etwa die älteren Versionen von FxCop und die Sicherheitsanalysetools.  Sie müssen nicht explizit die auf Roslyn basierenden Analysetools ausführen. Es ist nicht erforderlich, das Menüelemente„Codeanalyse ausführen“ in Visual Studio im Menü „Analysieren“ zu verwenden. Auf Roslyn basierende Analysetools werden asynchron ausgeführt, während Sie arbeiten. 

## <a name="more-information-on-specific-analyzers"></a>Weitere Informationen zu bestimmten Analysetools

In diesem Abschnitt werden die folgenden Analysetools behandelt:

[API Analyzer](api-analyzer.md): Dieses Analysetool untersucht Ihren Code auf potentielle Kompatibilitätsrisiken oder die Verwendung veralteter APIs.    
[Framework Analyzer](framework-analyzer.md): Dieses Analysetool untersucht Ihren Code, um sicherzustellen, dass dieser die Richtlinien für .NET Framework-Anwendungen befolgt. Diese Regeln umfassen mehrere sicherheitsbasierte Empfehlungen.
