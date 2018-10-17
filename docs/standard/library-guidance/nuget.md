---
title: Bibliotheken von NuGet und .NET
description: Empfehlungen für bewährte Methoden für die paketerstellung mit NuGet Bibliotheken für .NET.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: d0ea462a7f52dd9a6b2f14be9ed5770160bf66b1
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2018
ms.locfileid: "49374492"
---
# <a name="nuget"></a>NuGet

NuGet ist ein Paket-Manager für das Ökosystem von .NET und der primären Entwickler ermitteln und Abrufen von .NET Open Source-Bibliotheken. ["NuGet.org"](https://www.nuget.org/), ein kostenloser Dienst, der von Microsoft bereitgestellt werden, für das Hosten von NuGet-Pakete, ist der primäre Host für Öffentliche NuGet-Pakete, aber Sie können in benutzerdefinierten NuGet-Dienste wie Veröffentlichen [MyGet](https://www.myget.org/) und [Azure-Artefakte ](https://azure.microsoft.com/services/devops/artifacts/).

![NuGet](./media/nuget/nuget-logo.png "NuGet")

## <a name="create-a-nuget-package"></a>Erstellen Sie ein NuGet-Paket

Ein NuGet-Paket (`*.nupkg`) ist eine Zipdatei, .NET-Assemblys und zugehörige Metadaten enthält.

Es gibt zwei Hauptmethoden zum Erstellen eines NuGet-Pakets. Die neuere und empfohlene Möglichkeit zum Erstellen eines Pakets aus einem Projekt von SDK-Stil ist (die Projektdatei, deren Inhalt beginnt mit `<Project Sdk="Microsoft.NET.Sdk">`). Assemblys und Ziele werden automatisch auf das Paket hinzugefügt, und verbleibende Metadaten die MSBuild-Datei, z. B. Name und Version Paket hinzugefügt wird. Beim Kompilieren mit der [ `dotnet pack` ](../../core/tools/dotnet-pack.md) Befehl Ausgaben eine `*.nupkg` Datei statt Assemblys.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
    <AssemblyName>Contoso.Api</AssemblyName>
    <PackageVersion>1.1.0</PackageVersion>
    <Authors>John Doe</Authors>
  </PropertyGroup>
</Project>
```

Die ältere Möglichkeit zum Erstellen eines NuGet-Pakets ein `*.nuspec` Datei und die `nuget.exe` -Befehlszeilentool. Eine Nuspec-Datei bietet Ihnen eine bessere Kontrolle, aber Sie müssen sorgfältig angeben, welche Assemblys und die Ziele in das endgültige NuGet-Paket eingeschlossen werden sollen. Es ist einfach, ein Fehler unterläuft oder für eine Person vergessen, die NuSpec-Datei zu aktualisieren, wenn Sie Änderungen vornehmen. Der Vorteil einer NuSpec-Datei ist, können Sie sie NuGet-Pakete für Frameworks, die noch keine SDK-Stil-Projektdatei bieten erstellen.

**✔️ GGF.** verwenden eine SDK-Stil-Projektdatei das NuGet-Paket zu erstellen.

**✔️ GGF.** SourceLink einrichten, Datenquellen-Steuerelement-Metadaten für Ihre Assemblys und NuGet-Paket hinzufügen.

## <a name="package-dependencies"></a>Paketabhängigkeiten

NuGet-paketabhängigkeiten werden detailliert in die [Abhängigkeiten](./dependencies.md) Artikel.

## <a name="important-nuget-package-metadata"></a>Wichtige NuGet-Paketmetadaten

Ein NuGet-Paket unterstützt viele [Metadateneigenschaften](/nuget/reference/nuspec). Die folgende Tabelle enthält die coremetadaten, die alle Open Source-Projekt bereitgestellt werden sollen:

| MSBuild-Eigenschaftenname              | NuSpec-name              | Beschreibung  |
| ---------------------------------- | ------------------------ | ------------ |
| `PackageId`                        | `id`                       | Der paketbezeichner. Ein Präfix aus einem Bezeichner reserviert werden kann, wenn er erfüllt die [Kriterien](/nuget/reference/id-prefix-reservation). |
| `PackageVersion`                   | `version`                  | NuGet-Paket-Version. Weitere Informationen finden Sie unter [NuGet-Paketversion](./versioning.md#nuget-package-version).             |
| `Title`                            | `title`                    | Ein Benutzerfreundlicher Titel des Pakets. Wird standardmäßig die `PackageId`.             |
| `Description`                      | `description`              | Eine lange Beschreibung des Pakets in der Benutzeroberfläche angezeigt werden soll.             |
| `Authors`                          | `authors`                  | Eine durch Trennzeichen getrennte Liste der paketautoren, die mit Profilnamen unter nuget.org.             |
| `PackageTags`                      | `tags`                     | Eine durch Leerzeichen getrennte Liste von Tags und Schlüsselwörtern, die das Paket beschreiben. Tags werden verwendet, bei der Suche nach Paketen.             |
| `PackageIconUrl`                   | `iconUrl`                  | Eine URL für ein Bild, das als Symbol für das Paket verwendet werden soll. Die URL muss HTTPS sein und das Image 64 x 64 und einen transparenten Hintergrund.             |
| `PackageProjectUrl`                | `projectUrl`               | Eine URL für das projektrepository Homepage oder Quelle.             |
| `PackageLicenseUrl`                | `licenseUrl`               | Eine URL mit der Projektlizenz. Ist der URL, die `LICENSE` Datei in der quellcodeverwaltung.             |

**✔️ GGF.** Auswählen eines NuGet-Paket mit einem Präfix, die NuGets-präfixreservierung erfüllt [Kriterien](/nuget/reference/id-prefix-reservation).

**✔️ GGF.** mithilfe der `LICENSE` Datei in der quellcodeverwaltung als die `LicenseUrl`. Z. B. [LICENSE.md](https://github.com/JamesNK/Newtonsoft.Json/blob/c4af75c8e91ca0d75aa6c335e8c106780c4f7712/LICENSE.md).

> [!IMPORTANT]
> Ein Projekt, das nicht standardmäßig eine Lizenz [exklusive Copyright](https://choosealicense.com/no-permission/), kann für andere Personen zu verwenden.

**Führen Sie ✔️** verwenden eine HTTPS-Href auf Ihr Symbol "Paket".

> Führen Sie Websites wie "NuGet.org" mit HTTPS-tauglich und Anzeigen eines nicht-HTTPS-Images wird eine Warnung zu gemischte Inhalte erstellt.

**Führen Sie ✔️** verwenden Sie ein Image der Paket-Symbol, das ist 64 x 64 und verfügt über einen transparenten Hintergrund zur besseren Lesbarkeit.

## <a name="pre-release-packages"></a>Vorabversionen von Paketen

NuGet-Pakete mit einem Versionssuffix gelten [Vorabversion](/nuget/create-packages/prerelease-packages). Standardmäßig zeigt das NuGet-Paket-Manager-UI stabilen Releases, wenn ein Benutzer "OPTS"-in Vorabversionen von Paketen, ausführenden Vorabversionen von Paketen ideal für Benutzer mit beschränkten Rechten zu testen.

```xml
<PackageVersion>1.0.1-beta1</PackageVersion>
```

> [!NOTE]
> Stabiles Paket kann nicht für ein vorab veröffentlichtes Paket abhängig sind. Sie müssen stellen Ihr eigenes Paket Vorabversion oder hängen von einer älteren stabile Version.

![NuGet-Vorabversionen-paketabhängigkeit](./media/nuget/nuget-prerelease-package.png "vorabversionspakets NuGet-Abhängigkeit")

**Führen Sie ✔️** veröffentlichen Sie ein vorab veröffentlichtes Paket testen, und beim Testversand, experimentieren.

**Führen Sie ✔️** stabiles Paket veröffentlichen, wenn die kann jetzt also andere stabile Pakete darauf verweisen können.

## <a name="symbol-packages"></a>Symbolpakete

NuGet unterstützt [generieren ein separates Symbolpaket](/nuget/create-packages/symbol-packages) mit PDB-Dateien zusammen mit das Hauptpaket, die mit .NET Assemblys zu debuggen. Die Idee von Symbolpaketen ist sie auf einem Symbolserver gehostet werden und werden nur von einem Tool wie Visual Studio bei Bedarf heruntergeladen.

Derzeit öffentliche Haupthost für Symbole - [SymbolSource](http://www.symbolsource.org/) -bietet keine Unterstützung der portablen PDB-Dateien erstellt der Formatvorlage für SDK Projekte und Symbolpakete nicht nützlich sind.

**✔️ GGF.** Einbetten von PDB-Dateien in das Haupt-NuGet-Paket.

**❌ Vermeiden** erstellen ein Symbolpaket, die PDB-Dateien enthält.

>[!div class="step-by-step"]
[Zurück](./strong-naming.md)
[Weiter](./dependencies.md)
