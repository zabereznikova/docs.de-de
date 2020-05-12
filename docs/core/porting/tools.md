---
title: Tools für das Portieren zu .NET Core
description: Erfahren Sie mehr über einige der Tools, die Sie zum Portieren zu .NET Core verwenden können.
author: cartermp
ms.date: 05/03/2020
ms.openlocfilehash: d0cf0abf206950beb34556ca3ba7243d8cad241e
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795585"
---
# <a name="tools-to-help-with-porting-to-net-core"></a>Tools für das Portieren zu .NET Core

Die folgenden, in diesem Artikel aufgeführten Tools können sich beim Portieren als nützlich erweisen:

- [.NET Portability Analyzer:](../../standard/analyzers/portability-analyzer.md) eine Toolkette, mit der ein Bericht darüber generiert werden kann, wie portabel Ihr Code zwischen .NET Framework und .NET Core ist:
  - Als [Befehlszeilentool](https://github.com/Microsoft/dotnet-apiport/releases)
  - Als [Visual Studio-Erweiterung](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)
- [.NET API-Analysetool:](../../standard/analyzers/api-analyzer.md) Hierbei handelt es sich um ein Roslyn-Analysetool, das potenzielle Kompatibilitätsrisiken für C#-APIs auf verschiedenen Plattformen erkennt und Aufrufe an veraltete APIs ermittelt.
- [try-convert](https://www.nuget.org/packages/try-convert/): Ein globales .NET Core-Tool, das ein Projekt oder eine ganze Projektmappe in das .NET SDK konvertieren kann, einschließlich des Verschiebens von Desktop-Apps in .NET Core. Es wird nicht empfohlen, wenn Sie einen komplizierteren Build eingerichtet haben (z. B. benutzerdefinierte Aufgaben, Ziele oder Importe), und viele Projekttypen kommen dafür nicht infrage, die mit .NET Core nicht kompatibel sind.
