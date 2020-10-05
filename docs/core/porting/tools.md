---
title: Tools für das Portieren zu .NET Core
description: Erfahren Sie mehr über einige der Tools, die Sie zum Portieren zu .NET Core verwenden können.
author: cartermp
ms.date: 05/03/2020
ms.openlocfilehash: b8678ec72fe5d910d5f8cff4768106e7496f9276
ms.sourcegitcommit: 1274a1a4a4c7e2eaf56b38da76ef7cec789726ef
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2020
ms.locfileid: "91406127"
---
# <a name="tools-to-help-with-porting-to-net-core"></a>Tools für das Portieren zu .NET Core

Die folgenden, in diesem Artikel aufgeführten Tools können sich beim Portieren als nützlich erweisen:

- [.NET Portability Analyzer:](../../standard/analyzers/portability-analyzer.md) eine Toolkette, mit der ein Bericht darüber generiert werden kann, wie portabel Ihr Code zwischen .NET Framework und .NET Core ist:
  - Als [Befehlszeilentool](https://github.com/Microsoft/dotnet-apiport/releases)
  - Als [Visual Studio-Erweiterung](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)
- [Das Analysetool für Plattformkompatibilität](../../standard/analyzers/platform-compat-analyzer.md): ein Roslyn-Analysetool, das Entwicklern mitteilt, wenn sie plattformspezifische APIs von Aufrufsites verwenden, bei denen die API möglicherweise nicht verfügbar ist.
- [Das .NET API-Analysetool](../../standard/analyzers/api-analyzer.md): ein Roslyn-Analyzer, mit dem in plattformübergreifenden Apps und Bibliotheken Probleme mit der Plattformkompatibilität erkannt werden.
- [try-convert](https://www.nuget.org/packages/try-convert/): Ein globales .NET Core-Tool, das ein Projekt oder eine ganze Projektmappe in das .NET SDK konvertieren kann, einschließlich des Verschiebens von Desktop-Apps in .NET Core. Es wird nicht empfohlen, wenn Sie einen komplizierteren Build eingerichtet haben (z. B. benutzerdefinierte Aufgaben, Ziele oder Importe), und viele Projekttypen kommen dafür nicht infrage, die mit .NET Core nicht kompatibel sind.
