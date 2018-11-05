---
title: NuGet für .NET-Bibliotheken
description: Best Practices für die Paketerstellung mit NuGet für .NET-Bibliotheken
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 479d1786c232ef1f843877169954e847453681c9
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185619"
---
# <a name="nuget"></a>NuGet

NuGet ist ein Paket-Manager für das .NET-Ökosystem und das primäre System, mit dem Entwickler Open Source-Bibliotheken von .NET untersuchen und abrufen. [NuGet.org](https://www.nuget.org/) ist ein kostenloser Dienst von Microsoft zum Hosten von NuGet-Paketen und der primäre Host für öffentliche NuGet-Pakete. Sie können damit auch Veröffentlichungen in benutzerdefinierten NuGet-Diensten wie [MyGet](https://www.myget.org/) und [Azure Artifacts](https://azure.microsoft.com/services/devops/artifacts/) ausführen.

![NuGet](./media/nuget/nuget-logo.png "NuGet")

## <a name="create-a-nuget-package"></a>Erstellen eines NuGet-Pakets

Ein NuGet-Paket (`*.nupkg`) ist eine ZIP-Datei, die .NET-Assemblys und zugehörige Metadaten enthält.

Sie haben im Wesentlichen zwei Optionen, ein NuGet-Paket zu erstellen. Der neuere und empfohlene Ansatz ist die Paketerstellung aus einem Projekt im SDK-Stil (Projektdatei, deren Inhalt mit `<Project Sdk="Microsoft.NET.Sdk">` beginnt). Assemblys und Ziele werden dem Paket automatisch hinzugefügt und die restlichen Metadaten werden der MSBuild-Datei hinzugefügt, z.B. Paketname und Versionsnummer. Die Kompilierung mit dem Befehl [`dotnet pack`](../../core/tools/dotnet-pack.md) gibt anstelle von Assemblys eine `*.nupkg`-Datei aus.

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

Der ältere Ansatz zum Erstellen eines NuGet-Pakets erfordert eine `*.nuspec`-Datei und das Befehlszeilentool `nuget.exe`. Mit einer NUSPEC-Datei haben Sie umfangreiche Kontrolle, doch Sie müssen sorgfältig angeben, welche Assemblys und Ziele in das endgültige NuGet-Paket aufgenommen werden. Achten Sie darauf, dass Ihnen keine Fehler unterlaufen, und dass Sie nicht vergessen, die NUSPEC-Datei zu aktualisieren, nachdem Sie Änderungen vorgenommen haben. Der Vorteil einer NUSPEC-Datei ist, dass Sie mit ihr NuGet-Pakete für Frameworks erstellen können, die noch keine im SDK-Projektdatei unterstützen.

**✔️ Verwenden** Sie eine SDK-Projektdatei zum Erstellen des NuGet-Pakets.

**✔️ Richten** Sie SourceLink ein, um Ihren Assemblys und dem NuGet-Paket Metadaten der Quellcodeverwaltung hinzuzufügen.

## <a name="package-dependencies"></a>Paketabhängigkeiten

Abhängigkeiten von NuGet-Paketen werden im Artikel [Abhängigkeiten](./dependencies.md) ausführlich erläutert.

## <a name="important-nuget-package-metadata"></a>Wichtige Metadaten von NuGet-Paketen

Ein NuGet-Paket unterstützt viele [Metadateneigenschaften](/nuget/reference/nuspec). Die folgende Tabelle enthält die wichtigsten Metadaten, die jedes Open Source-Projekt bereitstellen sollte:

| MSBuild-Eigenschaftenname              | NUSPEC-Name              | Beschreibung   |
| ---------------------------------- | ------------------------ | ------------ |
| `PackageId`                        | `id`                       | Der Paketbezeichner. Ein Präfix aus dem Bezeichner kann reserviert werden, wenn es die [Kriterien](/nuget/reference/id-prefix-reservation) erfüllt. |
| `PackageVersion`                   | `version`                  | Die NuGet-Paketversion. Weitere Informationen finden Sie unter [NuGet-Paketversion](./versioning.md#nuget-package-version).             |
| `Title`                            | `title`                    | Ein benutzerfreundlicher Pakettitel. Er entspricht standardmäßig `PackageId`.             |
| `Description`                      | `description`              | Eine ausführliche Beschreibung des Pakets, die in der Benutzeroberfläche angezeigt wird.             |
| `Authors`                          | `authors`                  | Eine durch Trennzeichen getrennte Liste von Paketerstellern, die den Profilnamen auf nuget.org entspricht.             |
| `PackageTags`                      | `tags`                     | Eine durch Leerzeichen getrennte Liste von Tags und Schlüsselwörtern, die das Paket beschreiben. Tags werden bei der Suche nach Paketen verwendet.             |
| `PackageIconUrl`                   | `iconUrl`                  | Eine URL für ein Bild, das als Symbol für das Paket verwendet wird. Es muss sich um eine HTTPS-URL handeln, und das Bild muss die Maße 64x64 sowie einen transparenten Hintergrund haben.             |
| `PackageProjectUrl`                | `projectUrl`               | Eine URL für die Projekthomepage oder das Quellrepository.             |
| `PackageLicenseUrl`                | `licenseUrl`               | Eine URL für die Projektlizenz. Es kann die URL zur Datei `LICENSE` in der Quellcodeverwaltung sein.             |

**✔️ Wählen** Sie einen NuGet-Paketnamen mit einem Präfix aus, das den [Kriterien](/nuget/reference/id-prefix-reservation) der NuGet-Präfixreservierung entspricht.

**✔️ Verwenden** Sie die `LICENSE`-Datei in der Quellcodeverwaltung als `LicenseUrl`. Beispiel: [LICENSE.md](https://github.com/JamesNK/Newtonsoft.Json/blob/c4af75c8e91ca0d75aa6c335e8c106780c4f7712/LICENSE.md).

> [!IMPORTANT]
> Ein Projekt ohne Lizenz unterliegt standardmäßig [exklusivem Copyright](https://choosealicense.com/no-permission/), sodass es nicht von anderen Benutzern verwendet werden kann.

**✔️ Verwenden** Sie einen HTTPS-Hypertextverweis für Ihr Paketsymbol.

> Websites wie NuGet.org werden mit aktiviertem HTTPS ausgeführt, und die Anzeige eines Nicht-HTTPS-Bildes generiert eine Warnung vor gemischten Inhalten.

**✔️ Verwenden** Sie ein Paketsymbolbild, das 64x64 groß ist und einen transparenten Hintergrund für die ideale Darstellung hat.

## <a name="pre-release-packages"></a>Vorabversionen von Paketen

NuGet-Pakete mit einem Versionssuffix gelten als [Vorabversion](/nuget/create-packages/prerelease-packages). Standardmäßig zeigt die Benutzeroberfläche des NuGet-Paket-Managers stabile Versionen an, es sei denn, ein Benutzer veröffentlicht Pakete vorab – Vorabversionspakete eignen sich ideal für eingeschränkte Benutzertests.

```xml
<PackageVersion>1.0.1-beta1</PackageVersion>
```

> [!NOTE]
> Ein stabiles Paket kann nicht von einem Vorabversionspaket abhängen. Sie müssen entweder Ihr eigenes Paket vorab veröffentlichen oder eine ältere stabile Version verwenden.

![NuGet-Vorabversions-Paketabhängigkeit](./media/nuget/nuget-prerelease-package.png "NuGet-Vorabversions-Paketabhängigkeit")

**✔️ Veröffentlichen** Sie ein Vorabversionspaket für Tests und Vorschauen.

**✔️ Veröffentlichen** Sie ein stabiles Paket, wenn es fertig ist, sodass andere stabile Pakete es referenzieren können.

## <a name="symbol-packages"></a>Symbolpakete

Symboldateien (`*.pdb`) werden vom .NET-Compiler neben Assemblys erstellt. Symboldateien ordnen Ausführungsstandorte dem ursprünglichen Quellcode zu, sodass Sie den Quellcode bei der Ausführung mit einem Debugger durchgehen können. NuGet unterstützt das [Generieren eines separaten Symbolpakets](/nuget/create-packages/symbol-packages) mit Symboldateien neben dem Hauptpaket mit .NET-Assemblys. Die Idee von Symbolpaketen ist, dass sie auf einem Symbolserver gehostet und nur bei Bedarf von einem Tool wie Visual Studio heruntergeladen werden.

Derzeit unterstützt der öffentliche Haupthost für Symbole – [SymbolSource](http://www.symbolsource.org/) – nicht die neuen [portablen Symboldateien](https://github.com/dotnet/core/blob/master/Documentation/diagnostics/portable_pdb.md) (`*.pdb`), die von SDK-Projekten erstellt wurden. Das bedeutet, Symbolpakete sind nicht nützlich. Bis es einen empfohlenen Host für Symbolpakete gibt, können Symboldateien in das Hauptpaket von NuGet eingebettet werden. Wenn Sie Ihr NuGet-Paket mit einem SDK-Projekt erstellen, können Sie Symboldateien einbetten, indem Sie die Eigenschaft `AllowedOutputExtensionsInPackageBuildOutputFolder` festlegen: 

```xml
<Project Sdk="Microsoft.NET.Sdk">
 <PropertyGroup>
    <!-- Include symbol files (*.pdb) in the built .nupkg -->
    <AllowedOutputExtensionsInPackageBuildOutputFolder>$(AllowedOutputExtensionsInPackageBuildOutputFolder);.pdb</AllowedOutputExtensionsInPackageBuildOutputFolder>
  </PropertyGroup>
</Project>
```

**✔️ Betten** Sie Symboldateien in das NuGet-Hauptpaket ein.

**❌ Erstellen** Sie kein Symbolpaket mit Symboldateien.

>[!div class="step-by-step"]
[Zurück](./strong-naming.md)
[Weiter](./dependencies.md)
