---
title: Die auf Roslyn basierenden Analysetools – .NET
description: Erfahren Sie mehr zu auf Roslyn basierenden Analysetools, die Probleme erkennen und Problembehebungen vorschlagen.
author: billwagner
ms.author: wiwagn
ms.date: 01/24/2018
ms.technology: dotnet-standard
ms.openlocfilehash: 436cfb3904f0891f8c18bb5890563a13d65e2d1c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "62003053"
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

* [API Analyzer](api-analyzer.md): Dieses Analysetool untersucht Ihren Code auf potentielle Kompatibilitätsrisiken oder die Verwendung veralteter APIs.
* [Framework Analyzer](framework-analyzer.md): Dieses Analysetool untersucht Ihren Code, um sicherzustellen, dass dieser die Richtlinien für .NET Framework-Anwendungen befolgt. Diese Regeln umfassen mehrere sicherheitsbasierte Empfehlungen.
* [.NET Portability Analyzer](portability-analyzer.md): Dieses Analysetool untersucht, wie hoch der Aufwand ist, um Ihre Anwendung mit anderen .NET-Implementierungen und -Profilen, wie z.B. .NET Core, .NET Standard, UWP und Xamarin für iOS, Android und Mac, kompatibel zu machen.
