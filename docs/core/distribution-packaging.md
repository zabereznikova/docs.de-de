---
title: Verpacken einer Verteilung von .NET Core
description: Erfahren Sie, wie Sie .NET Core für die Verteilung verpacken, benennen und mit einer Versionsnummer versehen.
author: tmds
ms.date: 10/09/2019
ms.openlocfilehash: 3324a6a151fc6dc46a8f13ea17c89da99d108d82
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/11/2020
ms.locfileid: "88062885"
---
# <a name="net-core-distribution-packaging"></a>Verpacken einer Verteilung von .NET Core

Da .NET Core auf immer mehr Plattformen verfügbar wird, ist es hilfreich zu erfahren, wie man es verpackt, benennt und mit einer Versionsnummer versieht. Auf diese Weise kann mithilfe von Paketverwaltern eine konsistente Benutzererfahrung sichergestellt werden, unabhängig davon, wo Benutzer .NET ausführen. Dieser Artikel ist für Benutzer hilfreich, die

- versuchen, .NET Core von der Quelle aus zu erstellen.
- Änderungen an der .NET Core-CLI vornehmen möchten, die sich auf das resultierende Layout oder die erzeugten Pakete auswirken könnten.

## <a name="disk-layout"></a>Datenträgerlayout

.NET Core besteht aus mehreren Komponenten, die im Dateisystem folgendermaßen angeordnet sind:

```
{dotnet_root}                                     (*)
├── dotnet                       (1)
├── LICENSE.txt                  (8)
├── ThirdPartyNotices.txt        (8)
├── host                                          (*)
│   └── fxr                                       (*)
│       └── <fxr version>        (2)
├── sdk                                           (*)
│   ├── <sdk version>            (3)
│   └── NuGetFallbackFolder      (4)              (*)
├── packs                                         (*)
│   ├── Microsoft.AspNetCore.App.Ref              (*)
│   │   └── <aspnetcore ref version>     (11)
│   ├── Microsoft.NETCore.App.Ref                 (*)
│   │   └── <netcore ref version>        (12)
│   ├── Microsoft.NETCore.App.Host.<rid>          (*)
│   │   └── <apphost version>            (13)
│   ├── Microsoft.WindowsDesktop.App.Ref          (*)
│   │   └── <desktop ref version>        (14)
│   └── NETStandard.Library.Ref                   (*)
│       └── <netstandard version>        (15)
├── shared                                        (*)
│   ├── Microsoft.NETCore.App                     (*)
│   │   └── <runtime version>     (5)
│   ├── Microsoft.AspNetCore.App                  (*)
│   │   └── <aspnetcore version>  (6)
│   ├── Microsoft.AspNetCore.All                  (*)
│   │   └── <aspnetcore version>  (6)
│   └── Microsoft.WindowsDesktop.App              (*)
│       └── <desktop app version> (7)
└── templates                                     (*)
│   └── <templates version>      (17)
/
├── etc/dotnet
│       └── install_location     (16)
├── usr/share/man/man1
│       └── dotnet.1.gz          (9)
└── usr/bin
        └── dotnet               (10)
```

- (1) **dotnet**: Der Host (auch bekannt als „Muxer“) führt zwei unterschiedliche Rollen aus: das Aktivieren einer Runtime, um eine Anwendung zu starten, und das Aktivieren eines SDK, um Befehle an dieses weiterzuleiten. Der Host ist eine native ausführbare Datei (`dotnet.exe`).

Es gibt nur einen Host, die meisten anderen Komponenten befinden sich jedoch in Verzeichnissen mit Versionsangabe (2, 3, 5, 6). Das bedeutet, dass auf dem System mehrere Versionen vorhanden sein können, da sie nebeneinander installiert werden können.

- (2) **host/fxr/\<fxr version>** : Enthält die vom Host verwendete Frameworkauflösungslogik. Der Host verwendet die neueste installierte hostfxr-Version. „hostfxr“ ist für die Auswahl der geeigneten Runtime beim Ausführen einer .NET Core-Anwendung zuständig. Eine Anwendung, die für .NET Core 2.0.0 erstellt wurde, verwendet beispielsweise die Runtime 2.0.5, wenn sie verfügbar ist. Ebenso wählt „hostfxr“ während der Entwicklung das geeignete SDK aus.

- (3) **sdk/\<sdk version>** : Bei dem SDK (auch „die Tools“) handelt es sich um mehrere verwaltete Tools, die zum Schreiben und Erstellen von .NET Core-Bibliotheken und -Anwendungen verwendet werden. Das SDK enthält die .NET Core-CLI, die verwalteten Sprachcompiler, MSBuild und zugehörige Buildtasks und -ziele, NuGet, neue Projektvorlagen usw.

- (4) **sdk/NuGetFallbackFolder** enthält einen Cache der NuGet-Pakete, die von einem SDK während der Wiederherstellung verwendet werden, etwa bei der Ausführung von `dotnet restore` oder `dotnet build`. Dieser Ordner wird nur vor .NET Core 3.0 verwendet. Er kann nicht aus der Quelle erstellt werden, da er vorgefertigte binäre Ressourcen aus `nuget.org` enthält.

Der Ordner **shared** enthält Frameworks. Ein gemeinsames (shared) Framework stellt einen Satz Bibliotheken an einem zentralen Speicherort bereit, sodass diese von verschiedenen Anwendungen verwendet werden können.

- (5) **shared/Microsoft.NETCore.App/\<runtime version>** : Dieses Framework enthält die .NET-Runtime und die unterstützenden verwalteten Bibliotheken.

- (6) **shared/Microsoft.AspNetCore.{App,All}/\<aspnetcore version>** : Enthält die ASP.NET Core-Bibliotheken. Die Bibliotheken unter `Microsoft.AspNetCore.App` werden im Rahmen des .NET Core-Projekts entwickelt und unterstützt. Die Bibliotheken unter `Microsoft.AspNetCore.All` sind ein übergeordnetes Set, das auch Drittanbieterbibliotheken enthält.

- (7) **shared/Microsoft.Desktop.App/\<desktop app version>** : Enthält die Windows-Desktopbibliotheken. Dies ist nur in Windows enthalten, und nicht in anderen Plattformen.

- (8) **LICENSE.txt,ThirdPartyNotices.txt**: Dies sind die .NET Core-Lizenzen und die Lizenzen von Drittanbieterbibliotheken, die in .NET Core jeweils verwendet werden.

- (9, 10) **dotnet.1.gz, dotnet**: `dotnet.1.gz` ist die dotnet-Handbuchseite. `dotnet` ist eine symbolische Verknüpfung mit dem Dotnet-Host (1). Diese Dateien werden zur Systemintegration an bekannten Speicherorten installiert.

- (11,12) **Microsoft.NETCore.App.Ref,Microsoft.AspNetCore.App.Ref** beschreibt jeweils die API einer `x.y`-Version von .NET Core und ASP.NET Core. Diese Pakete werden bei der Kompilierung für diese Zielversionen verwendet.

- (13) **Microsoft.NETCore.App.Host.\<rid>** : Enthält eine native Binärdatei für die Plattform `rid`. Diese Binärdatei ist eine Vorlage für das Kompilieren einer .NET Core-Anwendung in eine native Binärdatei für diese Plattform.

- (14) **Microsoft.WindowsDesktop.App.Ref** beschreibt die API der `x.y`-Version von Windows-Desktopanwendungen. Diese Dateien werden beim Kompilieren für dieses Ziel verwendet. Dies wird nur unter Windows bereitgestellt, und nicht für andere Plattformen.

- (15) **NETStandard.Library.Ref** beschreibt die NetStandard-API `x.y`. Diese Dateien werden beim Kompilieren für dieses Ziel verwendet.

- (16) **/etc/dotnet/install_location** ist eine Datei, die den vollständigen Pfad für `{dotnet_root}` enthält. Der Pfad kann mit einem Zeilenvorschubzeichen enden. Es ist nicht erforderlich, diese Datei hinzuzufügen, wenn `/usr/share/dotnet` das Stammverzeichnis ist.

- (17) **templates** enthält die Vorlagen, die vom SDK verwendet werden. Beispielsweise ermittelt `dotnet new` Projektvorlagen in diesem Ordner.

Die mit `(*)` markierten Ordner werden von mehreren Paketen verwendet. Einige Paketformate (z.B. `rpm`) erfordern eine besondere Verarbeitung solcher Ordner. Der Paketmaintainer muss dafür Sorge tragen.

## <a name="recommended-packages"></a>Empfohlene Pakete

Die .NET Core-Versionierung basiert auf dem Versionsnummernmuster `[major].[minor]` der Runtimekomponente.
Die SDK-Version verwendet das gleiche `[major].[minor]`-Muster und weist eine unabhängige `[patch]`-Zeichenfolge auf, die die Feature- und Patchsemantik für das SDK kombiniert.
Zum Beispiel: Die SDK-Version 2.2.302 ist das zweite Patchrelease des dritten Featurerelease des SDK, das die Runtimeversion 2.2 unterstützt. Weitere Informationen zur Funktionsweise der Versionsverwaltung finden Sie unter [.NET Core-Versionskontrolle: Übersicht](./versions/index.md).

Einige Pakete enthalten einen Teil der Versionsnummer im Namen. Dies ermöglicht Ihnen, eine bestimmte Version zu installieren.
Der Rest der Version ist im Versionsnamen nicht enthalten. Dies ermöglicht dem Paket-Manager des Betriebssystems, die Pakete zu aktualisieren (z.B. durch automatisches Installieren von Sicherheitsfixes). Unterstützte Paket-Manager sind Linux-spezifisch.

Im Folgenden werden die empfohlenen Pakete aufgeführt:

- `dotnet-sdk-[major].[minor]`: installiert das neueste SDK für eine spezifische Runtime.
  - **Version:** \<sdk version>
  - **Beispiel:** dotnet-sdk-2.1
  - **Enthält:** (3), (4)
  - **Abhängigkeiten:** `dotnet-runtime-[major].[minor]`, `aspnetcore-runtime-[major].[minor]`, `dotnet-targeting-pack-[major].[minor]`, `aspnetcore-targeting-pack-[major].[minor]`, `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`, `dotnet-apphost-pack-[major].[minor]`, `dotnet-templates-[major].[minor]`

- `aspnetcore-runtime-[major].[minor]`: installiert eine spezifische ASP.NET Core-Runtime.
  - **Version:** \<aspnetcore runtime version>
  - **Beispiel:** aspnetcore-runtime-2.1
  - **Enthält:** (6)
  - **Abhängigkeiten:** `dotnet-runtime-[major].[minor]`

- `dotnet-runtime-deps-[major].[minor]` _(Optional):_ Installiert die Abhängigkeiten zum Ausführen eigenständiger Anwendungen.
  - **Version:** \<runtime version>
  - **Beispiel:** dotnet-runtime-deps-2.1
  - **Abhängigkeiten:** _Verteilungsspezifische Abhängigkeiten_

- `dotnet-runtime-[major].[minor]`: installiert eine spezifische Runtime
  - **Version:** \<runtime version>
  - **Beispiel:** dotnet-runtime-2.1
  - **Enthält:** (5)
  - **Abhängigkeiten:** `dotnet-hostfxr-[major].[minor]`, `dotnet-runtime-deps-[major].[minor]`

- `dotnet-hostfxr-[major].[minor]`: Abhängigkeit
  - **Version:** \<runtime version>
  - **Beispiel:** dotnet-hostfxr-3.0
  - **Enthält:** (2)
  - **Abhängigkeiten:** `dotnet-host`

- `dotnet-host`: Abhängigkeit
  - **Version:** \<runtime version>
  - **Beispiel:** dotnet-host
  - **Enthält:** (1),(8),(9),(10),(16)

- `dotnet-apphost-pack-[major].[minor]`: Abhängigkeit
  - **Version:** \<runtime version>
  - **Enthält:** (13)

- `dotnet-targeting-pack-[major].[minor]`: ermöglicht eine ältere Runtime als Ziel.
  - **Version:** \<runtime version>
  - **Enthält:** (12)

- `aspnetcore-targeting-pack-[major].[minor]`: ermöglicht eine ältere Runtime als Ziel.
  - **Version:** \<aspnetcore runtime version>
  - **Enthält:** (11)

- `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`: ermöglicht eine NetStandard-Zielversion
  - **Version:** \<sdk version>
  - **Enthält:** (15)

- `dotnet-templates-[major].[minor]`
  - **Version:** \<sdk version>
  - **Enthält:** (15)

Für `dotnet-runtime-deps-[major].[minor]` ist ein Verständnis der _distributionsspezifischen Abhängigkeiten_ erforderlich. Da das Buildsystem der Verteilung dies möglicherweise automatisch ableiten kann, ist das Paket optional. In diesem Falle werden diese Abhängigkeiten direkt zum `dotnet-runtime-[major].[minor]`-Paket hinzugefügt.

Wenn Paketinhalte sich in einem Ordner mit Versionsangabe befinden, stimmt der Paketname `[major].[minor]` mit der Ordnernamen mit Versionsangabe überein. Für alle Pakete (außer `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`) stimmt dieser auch mit der .NET Core-Version überein.

Abhängigkeiten zwischen Paketen sollten eine _identische oder höhere_ erforderliche Version verwenden. `dotnet-sdk-2.2:2.2.401` erfordert beispielsweise `aspnetcore-runtime-2.2 >= 2.2.6`. Dies ermöglicht es dem Benutzer, für seine Installation ein Upgrade mithilfe eines Stammpakets (z.B. `dnf update dotnet-sdk-2.2`) durchzuführen.

Für die meisten Verteilungen müssen alle Artefakte aus der Quelle erstellt werden. Dies wirkt sich auf die Pakete aus:

- Die Drittanbieterbibliotheken unter `shared/Microsoft.AspNetCore.All` können nicht einfach aus der Quelle erstellt werden. Daher ist dieser Ordner im `aspnetcore-runtime`-Paket nicht enthalten.

- Der `NuGetFallbackFolder` wird mithilfe von binären Artefakten aus `nuget.org` aufgefüllt. Der Ordner sollte leer bleiben.

Möglicherweise stellen mehrere `dotnet-sdk`-Pakete die gleichen Dateien für den `NuGetFallbackFolder` bereit. Um Probleme mit dem Paket-Manager zu vermeiden, sollten diese Dateien identisch sein (Prüfsumme, Änderungsdatum usw.).

## <a name="building-packages"></a>Erstellen von Paketen

Das Repository [dotnet/source-build](https://github.com/dotnet/source-build) stellt Anweisungen zum Erstellen eines Quell-Tarballs des .NET Core SDK und aller zugehörigen Komponenten bereit. Die Ausgabe des source-build-Repositorys entspricht der Anordnung, die im ersten Abschnitt dieses Artikels beschrieben wurde.
