---
title: Übersicht über .NET Core
description: Hier lernen Sie Merkmale und Zusammensetzung von .NET Core kennen und vergleichen .NET Core mit anderen .NET-Implementierungen.
ms.date: 03/26/2020
ms.openlocfilehash: e99939cf85cc441fd473e4d033e22b1a5d053638
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90539007"
---
# <a name="net-core-overview"></a>Übersicht über .NET Core

> [!div class="button"]
> [.NET Core herunterladen](https://dotnet.microsoft.com/download)

.NET Core weist folgende Merkmale auf:

- **Plattformübergreifend:** Ist unter den [Betriebssystemen](https://github.com/dotnet/core/blob/master/os-lifecycle-policy.md) Windows, macOS und Linux lauffähig.
- **Open Source:** Das .NET Core-Framework ist ein [Open Source](https://github.com/dotnet/core)-Framework, das MIT- und Apache 2-Lizenzen verwendet. .NET Core ist ein [.NET Foundation](https://dotnetfoundation.org/)-Projekt.
- **Modern:** Es implementiert moderne Paradigmen, z. B. asynchrone Programmierung, Muster, die mithilfe von Strukturen das Kopieren verhindern, und Ressourcenkontrolle für Container.
- **Leistung:**  Es bietet [hohe Leistung](https://devblogs.microsoft.com/dotnet/performance-improvements-in-net-core-3-0/) mit Features wie [intrinsische Hardwarefunktionen](https://devblogs.microsoft.com/dotnet/hardware-intrinsics-in-net-core/), [mehrstufige Kompilierung](https://github.com/dotnet/coreclr/blob/master/Documentation/design-docs/tiered-compilation.md) und [Span\<T>](../standard/memory-and-spans/index.md).
- **Umgebungsübergreifende Konsistenz:** Führt Ihren Code unter unterschiedlichen Betriebssystemen und Architekturen (z. B. x64, x86 und ARM) mit demselben Verhalten aus.
- **Befehlszeilentools:**  Umfasst benutzerfreundliche Befehlszeilentools, die Sie für die lokale Entwicklung und für Continuous Integration verwenden können.
- **Flexible Bereitstellung:** Sie können .NET Core in Ihre App einbinden oder parallel installieren (benutzer- oder systemweite Installation). Kann mit [Docker-Containern](docker/introduction.md) verwendet werden.

## <a name="languages"></a>Sprachen

[C#](../csharp/index.yml), [Visual Basic](../visual-basic/index.yml) und [F#](../fsharp/index.yml) können verwendet werden, um Anwendungen und Bibliotheken für .NET Core zu schreiben. Diese Sprachen können Sie in Ihren bevorzugten Text-Editoren oder integrierten Entwicklungsumgebungen (IDE, Integrated Development Environment) wie den folgenden verwenden:

- [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)
- [Visual Studio Code](https://code.visualstudio.com/download)

Die Editor-Integration wird zum Teil durch die Mitwirkenden der [OmniSharp](https://www.omnisharp.net/)- und [Ionide](https://ionide.io)-Projekte ermöglicht.

## <a name="apis"></a>APIs

.NET Core macht Frameworks zum Entwickeln jeder Art von App verfügbar:

* Cloud-Apps mit [ASP.NET Core](/aspnet/core/)
* Mobile Apps mit [Xamarin](/xamarin)
* IoT-Apps mit [System.Device.GPIO](/archive/msdn-magazine/2019/august/net-core-cross-platform-iot-programming-with-net-core-3-0)
* Windows-Client-Apps mit [WPF](../desktop-wpf/overview/index.md) und Windows Forms
* Machine Learning mit [ML.NET](../machine-learning/index.yml)

Viele der enthaltenen APIs unterstützen allgemeine Anforderungen:

- Primitive Typen wie <xref:System.Boolean?displayProperty=nameWithType> und <xref:System.Int32?displayProperty=nameWithType>.
- Sammlungen, z.B. <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> und <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType>.
- Hilfstypen, z.B. <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> und <xref:System.IO.FileStream?displayProperty=nameWithType>.
- Datentypen, z. B. <xref:System.Data.DataSet?displayProperty=nameWithType> und <xref:System.Data.Entity.DbSet?displayProperty=nameWithType>.
- Hochleistungstypen, z. B. <xref:System.Span%601?displayProperty=nameWithType>, <xref:System.Numerics.Vector?displayProperty=nameWithType> und [Pipelines](../standard/io/pipelines.md).

Durch die Implementierung der [.NET Standard](../standard/net-standard.md)-Spezifikation ist .NET Core mit .NET Framework und Mono-APIs kompatibel.

## <a name="composition"></a>Aufbau

.NET Core umfasst folgende Bestandteile:

- Eine [.NET Core-Runtime](https://github.com/dotnet/runtime/tree/master/src/coreclr), die ein Typsystem, eine Funktion zum Laden von Assemblys, einen Garbage Collector, natives Interop und andere grundlegende Dienste bereitstellt. [.NET Core-Frameworkbibliotheken](https://github.com/dotnet/runtime/tree/master/src/libraries) stellen primitive Datentypen, Typen zur Anwendungsgestaltung und grundlegende Hilfsprogramme bereit.
- Die [ASP.NET Core-Runtime](https://github.com/dotnet/aspnetcore), die ein Framework zum Erstellen moderner, cloudbasierter Apps mit Internetanbindung bietet, wie etwa Web-Apps, IoT-Apps und mobile Back-Ends.
- Das [.NET Core SDK](https://github.com/dotnet/sdk) und die Sprachcompiler ([Roslyn](https://github.com/dotnet/roslyn) und [F#](https://github.com/microsoft/visualfsharp)), die Funktionen für .NET Core-Entwickler bereitstellen.
- Der [dotnet-Befehl](./tools/dotnet.md), der zum Starten von .NET Core-Anwendungen und CLI-Befehlen verwendet wird. Er wählt und hostet die Runtime, stellt eine Richtlinie zum Laden der Assembly bereit und startet die Apps und Tools.

### <a name="open-source"></a>Quelle öffnen

[.NET Core](about.md) ist eine universelle [Open Source](https://github.com/dotnet/runtime/blob/master/LICENSE.TXT)-Entwicklungsplattform. Sie können .NET Core-Apps für Windows, macOS und Linux für x64-, x86-, ARM32- und ARM64-Prozessoren erstellen. Es werden Frameworks und APIs für die [Cloud](/aspnet/core/), für [IoT](/archive/msdn-magazine/2019/august/net-core-cross-platform-iot-programming-with-net-core-3-0), für [Clientbenutzeroberflächen](../desktop-wpf/overview/index.md) und für [Machine Learning](../machine-learning/index.yml) bereitgestellt.

## <a name="support"></a>Support

.NET Core wird von [Microsoft auf Windows, macOS und Linux unterstützt](https://dotnet.microsoft.com/platform/support/policy). Es wird regelmäßig im Hinblick auf Sicherheit und Qualität aktualisiert (jeden 2. Dienstag des Monats).

Binäre .NET Core-Distributionen von Microsoft werden auf von Microsoft verwalteten Servern in Azure entwickelt und getestet und entsprechen den Best Practices von Microsoft in Bezug auf Entwicklung und Sicherheit.

[Red Hat unterstützt .NET Core](https://developers.redhat.com/topics/dotnet/) auf Red Hat Enterprise Linux 7 (RHEL). Red Hat erstellt .NET Core aus einer Quelle und stellt es in den [Red Hat Software Collections](https://developers.redhat.com/products/softwarecollections/overview/) zur Verfügung. Red Hat und Microsoft arbeiten eng zusammen, um sicherzustellen, dass .NET Core ebenso auf RHEL funktioniert.

[Tizen unterstützt .NET Core](https://developer.tizen.org/development/training/.net-application) auf Tizen-Plattformen.
