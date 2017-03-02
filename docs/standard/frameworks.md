---
title: Frameworks und Ziele
description: "Erläutert die Konzepte von Framework abzielt, beim Schreiben von Code für .NET."
keywords: .NET, .NET Core
author: richlander
ms.author: mairaw
ms.date: 09/19/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 6ef56a2e-593d-497b-925a-1e25bb6df2e6
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: f0c1987f46bd3715c54e270c15eea4b8ee7b67e6
ms.lasthandoff: 03/02/2017

---

# <a name="frameworks-and-targets"></a>Frameworks und Ziele

Das .NET-Ökosystem basiert auf dem Konzept der Frameworks. Frameworks definieren die API, die Sie für eine bestimmte Plattform verwenden können. Das .NET Framework 4.6 ist eine solche Plattform. Frameworks werden in Visual Studio und anderen IDEs und Editoren verwendet, um Ihnen den richtigen Satz an APIs zur Verfügung zu stellen. Sie werden auch in NuGet für die Erzeugung und die Nutzung von NuGet-Paketen verwendet, um sicherzustellen, dass Sie die richtigen Pakete (und zugrunde liegenden Assets) für das gewünschte Framework erzeugen und verwenden. Sie können sich Frameworks als eine der wichtigsten Währungen im .NET-Ökosystem vorstellen. Das Konzept stellt ordnungsgemäße Einrichtung sicher, damit @System.MissingMethodException und ähnliche Ausnahmen weder Ihnen noch Ihren Kunden zur Laufzeit begegnen.

## <a name="framework-versions"></a>Framework-Versionen

Die unten stehende Tabelle gibt an, welche Frameworks Sie verwenden können, wie auf die Frameworks verwiesen wird und welche Version der [.NET-Standardbibliothek](library.md) von den Frameworks implementiert wird.

| Framework | Letzte Version | Zielframeworkmoniker (Target Framework Moniker, TFM) | Kompakter Zielframeworkmoniker (Target Framework Moniker, TFM) | .NET-Standardversion | Metapaket |
|:--------: | :--: | :--: | :--: | :--: | :--: | :--: |
| .NET-Standard | 1.6 | .NETStandard,Version=1.6 | netstandard1.6 | Nicht zutreffend | [NETStandard.Library](https://www.nuget.org/packages/NETStandard.Library)|
| .NET Core-Anwendung | 1.0.1 | .NETCoreApp,Version=1.0 | netcoreapp1.0 | 1.6 | [Microsoft.NETCore.App](https://www.nuget.org/packages/Microsoft.NETCore.App)|
| .NET Framework | 4.6.2 | .NETFramework,Version=4.6.2 | net462 | 1.5 | Nicht zutreffend |

> [!NOTE]
> Diese Frameworkversionen sind die neuesten stabilen Versionen. Möglicherweise gibt es auch Vorabversionen, die in dieser Tabelle nicht beschrieben werden.

## <a name="writing-about-frameworks"></a>Verweisen auf Frameworks

Es gibt verschiedene Möglichkeiten, schriftlich auf Frameworks zu verweisen. Die meisten werden in dieser Dokumentation verwendet. Die Methoden werden unten beschrieben, sowohl als Legende zum Verständnis der Dokumentation als auch als Leitfaden zur Verwendung in anderen Dokumenten.

Als Beispiel dient .NET Framework 4.6.1. Folgende Formen können verwendet werden:

**Verweisen auf ein Produkt**

Sie können auf eine .NET-Plattform oder -Laufzeit verweisen.

- „.NET Framework 4.6.1“

**Verweisen auf ein Framework**

Sie können mithilfe der langen oder kurzen Form des Zielframeworkmonikers auf ein Framework oder eine Frameworkzielplattform verweisen. Beide sind im Allgemeinen gleichermaßen gültig.

- `.NETFramework,Version=4.6.1`
- `net461`

**Verweisen auf eine Frameworkfamilie**

Sie können mithilfe der langen oder kurzen Form der Framework-ID auf eine Frameworkfamilie verweisen. Beide sind im Allgemeinen gleichermaßen gültig.

- `.NETFramework`
- `net`

