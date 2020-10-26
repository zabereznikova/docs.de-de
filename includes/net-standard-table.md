---
ms.openlocfilehash: 72b371dc2a6475efa2e0353f87dbdfa96c4c7c0e
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050394"
---
| .NET-Standard              | [1.0]  | [1.1]  | [1.2] | [1.3] | [1.4] | [1.5]              | [1.6]              | [2.0]               | [2.1] |
|----------------------------|--------|--------|-------|-------|-------|--------------------|--------------------|---------------------|---------------------
| .NET Core und .NET 5       | 1.0    | 1.0    | 1.0   | 1.0   | 1.0   | 1.0                | 1.0                | 2.0                 | 3.0 |
| .NET Framework <sup>1</sup>| 4.5    | 4.5    | 4.5.1 | 4.6   | 4.6.1 | 4.6.1 <sup>2</sup> | 4.6.1 <sup>2</sup> | 4.6.1 <sup>2</sup>  | Nicht zutreffend<sup>3</sup> |
| Mono                       | 4.6    | 4.6    | 4.6   | 4.6   | 4.6   | 4.6                | 4.6                | 5.4                 | 6.4 |
| Xamarin.iOS                | 10.0   | 10.0   | 10.0  | 10.0  | 10.0  | 10.0               | 10.0               | 10.14               | 12.16 |
| Xamarin.Mac                | 3.0    | 3.0    | 3.0   | 3.0   | 3.0   | 3.0                | 3.0                | 3.8                 | 5.16 |
| Xamarin.Android            | 7.0    | 7.0    | 7.0   | 7.0   | 7.0   | 7.0                | 7.0                | 8.0                 | 10.0 |
| Universelle Windows-Plattform | 10.0   | 10.0   | 10.0  | 10.0  | 10.0  | 10.0.16299         | 10.0.16299         | 10.0.16299          | Wird nachgeliefert. |
| Unity                      | 2018.1 | 2018.1 | 2018.1| 2018.1| 2018.1| 2018.1             |  2018.1            | 2018.1              | Wird nachgeliefert. |

<sup>1 Die für .NET Frameworks aufgeführten Versionen gelten für das .NET Core 2.0 SDK und höhere Versionen des Tools. Ältere Versionen haben eine andere Zuordnung für .NET Standard 1.5 und höher verwendet. Sie können [Tools für .NET Core-Tools für Visual Studio 2015 herunterladen](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md), falls Sie kein Upgrade auf Visual Studio 2017 oder eine höhere Version durchführen können.</sup>

<sup>2 Die hier aufgelisteten Versionen stellen die Regeln dar, die von NuGet verwendet werden, um zu bestimmen, ob eine vorhandene .NET Standard-Bibliothek anwendbar ist. Zwar sieht NuGet die .NET-Standards 1.5 bis 2.0 als durch .NET Framework 4.6.1 unterstützt an, jedoch treten verschiedene Probleme mit der Nutzung von .NET Standard-Bibliotheken auf, die für diese Versionen aus .NET Framework 4.6.1-Projekten erstellt wurden. Für .NET Framework-Projekte, die auf diese Bibliotheken angewiesen sind, empfehlen wir, ein Upgrade des Projekts auf die Zielplattform .NET Framework 4.7.2 oder höher durchzuführen.</sup>

<sup>3 .NET Standard 2.1 wird von .NET Framework nicht unterstützt. Weitere Informationen finden Sie in der [Ankündigung von .NET Standard 2.1](https://devblogs.microsoft.com/dotnet/announcing-net-standard-2-1/).</sup>

- Die Spalten stellen die .NET Standard-Versionen dar. Jede Zelle enthält einen Link zu einem Dokument, im dem die APIs angegeben sind, die in dieser Version von .NET Standard hinzugefügt wurden.
- Die Zeilen stellen die verschiedenen .NET-Implementierungen dar.
- Die Versionsnummer in jeder Zelle gibt an, welche Version der Implementierung Sie *mindestens* benötigen, um diese Version von .NET Standard als Ziel zu setzen.
- Eine interaktive Tabelle finden Sie unter [.NET Standard-Versionen](https://dotnet.microsoft.com/platform/dotnet-standard#versions).

[1.0]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard1.0.md
[1.1]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard1.1.md
[1.2]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard1.2.md
[1.3]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard1.3.md
[1.4]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard1.4.md
[1.5]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard1.5.md
[1.6]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard1.6.md
[2.0]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard2.0.md
[2.1]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard2.1.md
