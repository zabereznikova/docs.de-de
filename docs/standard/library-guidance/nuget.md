---
title: NuGet für .NET-Bibliotheken
description: Best Practices für die Paketerstellung mit NuGet für .NET-Bibliotheken
author: jamesnk
ms.author: mairaw
ms.date: 01/15/2019
ms.openlocfilehash: 9288bf440692302c3a0b1954236540af6363f367
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775311"
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

## <a name="package-dependencies"></a>Paketabhängigkeiten

Abhängigkeiten von NuGet-Paketen werden im Artikel [Abhängigkeiten](./dependencies.md) ausführlich erläutert.

## <a name="important-nuget-package-metadata"></a>Wichtige Metadaten von NuGet-Paketen

Ein NuGet-Paket unterstützt viele [Metadateneigenschaften](/nuget/reference/nuspec). Die folgende Tabelle enthält die wichtigsten Metadaten, die jedes Paket auf NuGet.org bereitstellen sollte:

| MSBuild-Eigenschaftenname              | NUSPEC-Name              | BESCHREIBUNG  |
| ---------------------------------- | ------------------------ | ------------ |
| `PackageId`                        | `id`                       | Der Paketbezeichner. Ein Präfix aus dem Bezeichner kann reserviert werden, wenn es die [Kriterien](/nuget/reference/id-prefix-reservation) erfüllt. |
| `PackageVersion`                   | `version`                  | Die NuGet-Paketversion. Weitere Informationen finden Sie unter [NuGet-Paketversion](./versioning.md#nuget-package-version).             |
| `Title`                            | `title`                    | Ein benutzerfreundlicher Pakettitel. Er entspricht standardmäßig `PackageId`.             |
| `Description`                      | `description`              | Eine ausführliche Beschreibung des Pakets, die in der Benutzeroberfläche angezeigt wird.             |
| `Authors`                          | `authors`                  | Eine durch Trennzeichen getrennte Liste von Paketerstellern, die den Profilnamen auf nuget.org entspricht.             |
| `PackageTags`                      | `tags`                     | Eine durch Leerzeichen getrennte Liste von Tags und Schlüsselwörtern, die das Paket beschreiben. Tags werden bei der Suche nach Paketen verwendet.             |
| `PackageIconUrl`                   | `iconUrl`                  | Eine URL für ein Bild, das als Symbol für das Paket verwendet wird. Es muss sich um eine HTTPS-URL handeln, und das Bild muss die Maße 64x64 sowie einen transparenten Hintergrund haben.             |
| `PackageProjectUrl`                | `projectUrl`               | Eine URL für die Projekthomepage oder das Quellrepository.             |
| `PackageLicenseExpression`         | `license`                  | Die [SPDX-ID](https://spdx.org/licenses/) der Projektlizenz. Nur OSI- und FSF-genehmigte Lizenzen können eine ID verwenden. Andere Lizenzen sollten `PackageLicenseFile` verwenden. Erfahren Sie mehr über [`license`-Metadaten](/nuget/reference/nuspec#license). |

> [!IMPORTANT]
> Ein Projekt ohne Lizenz unterliegt standardmäßig [exklusivem Copyright](https://choosealicense.com/no-permission/), sodass es nicht rechtmäßig von anderen Benutzern verwendet werden kann.

**✔️ Wählen** Sie einen NuGet-Paketnamen mit einem Präfix aus, das den [Kriterien](/nuget/reference/id-prefix-reservation) der NuGet-Präfixreservierung entspricht.

**✔️ Verwenden** Sie einen HTTPS-Hypertextverweis für Ihr Paketsymbol.

> Websites wie NuGet.org werden mit aktiviertem HTTPS ausgeführt, und die Anzeige eines Nicht-HTTPS-Bildes generiert eine Warnung vor gemischten Inhalten.

**✔️ Verwenden** Sie ein Paketsymbolbild, das 64x64 groß ist und einen transparenten Hintergrund für die ideale Darstellung hat.

**✔️ Richten** Sie [SourceLink](./sourcelink.md) ein, um Ihren Assemblys und dem NuGet-Paket Metadaten der Quellcodeverwaltung hinzuzufügen.

> SourceLink fügt dem NuGet-Paket automatisch `RepositoryUrl`- und `RepositoryType`-Metadaten hinzu. SourceLink fügt auch Informationen zum genauen Quellcode hinzu, mit dem das Paket erstellt wurde. Beispielsweise wird einem Paket, das aus einem Git-Repository erstellt wurde, der Commithash als Metadaten hinzugefügt.

## <a name="pre-release-packages"></a>Vorabversionen von Paketen

NuGet-Pakete mit einem Versionssuffix gelten als [Vorabversion](/nuget/create-packages/prerelease-packages). Standardmäßig zeigt die Benutzeroberfläche des NuGet-Paket-Managers stabile Versionen an, es sei denn, ein Benutzer veröffentlicht Pakete vorab – Vorabversionspakete eignen sich ideal für eingeschränkte Benutzertests.

```xml
<PackageVersion>1.0.1-beta1</PackageVersion>
```

> [!NOTE]
> Ein stabiles Paket kann nicht von einem Vorabversionspaket abhängen. Sie müssen entweder Ihr eigenes Paket vorab veröffentlichen oder eine ältere stabile Version verwenden.

![Vorabrelease der NuGet-Paketabhängigkeit](./media/nuget/nuget-prerelease-package.png "Vorabrelease der NuGet-Paketabhängigkeit")

**✔️ Veröffentlichen** Sie ein Vorabversionspaket für Tests und Vorschauen.

**✔️ Veröffentlichen** Sie ein stabiles Paket, wenn es fertig ist, sodass andere stabile Pakete es referenzieren können.

## <a name="symbol-packages"></a>Symbolpakete

Symboldateien (`*.pdb`) werden vom .NET-Compiler neben Assemblys erstellt. Symboldateien ordnen Ausführungsstandorte dem ursprünglichen Quellcode zu, sodass Sie den Quellcode bei der Ausführung mit einem Debugger durchgehen können. NuGet unterstützt das [Generieren eines separaten Symbolpakets (`*.snupkg`)](/nuget/create-packages/symbol-packages-snupkg) mit Symboldateien neben dem Hauptpaket mit .NET-Assemblys. Die Idee von Symbolpaketen ist, dass sie auf einem Symbolserver gehostet und nur bei Bedarf von einem Tool wie Visual Studio heruntergeladen werden.

NuGet.org hostet sein eigenes [Symbolserverrepository](/nuget/create-packages/symbol-packages-snupkg#nugetorg-symbol-server). Entwickler können die auf dem NuGet.org-Symbolserver veröffentlichten Symbole verwenden, indem sie ihren [-Symbolquellen in Visual Studio](/visualstudio/debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger) `https://symbols.nuget.org/download/symbols` hinzufügen.

> [!IMPORTANT]
> Der NuGet.org-Symbolserver unterstützt nur die neuen [portierbaren Symboldateien](https://github.com/dotnet/core/blob/master/Documentation/diagnostics/portable_pdb.md) (`*.pdb`), die von SDK-Projekten erstellt wurden.
>
> Entwickler benötigen Visual Studio 2017 Version 15.9 oder höher, um beim Debuggen einer .NET-Bibliothek den NuGet.org-Symbolserver zu verwenden.

Eine Alternative zum Erstellen eines Symbolpakets ist das Einbetten von Symboldateien in das NuGet-Hauptpaket. Das NuGet-Hauptpaket ist zwar größer, doch da die Symboldateien eingebettet sind, müssen Entwickler den NuGet.org-Symbolserver nicht konfigurieren. Wenn Sie Ihr NuGet-Paket mit einem SDK-Projekt erstellen, können Sie Symboldateien einbetten, indem Sie die Eigenschaft `AllowedOutputExtensionsInPackageBuildOutputFolder` festlegen:

```xml
<Project Sdk="Microsoft.NET.Sdk">
 <PropertyGroup>
    <!-- Include symbol files (*.pdb) in the built .nupkg -->
    <AllowedOutputExtensionsInPackageBuildOutputFolder>$(AllowedOutputExtensionsInPackageBuildOutputFolder);.pdb</AllowedOutputExtensionsInPackageBuildOutputFolder>
  </PropertyGroup>
</Project>
```

Der Nachteil von eingebetteten Symboldateien ist, dass sie die Paketgröße für .NET-Bibliotheken, die mit SDK-Projekten kompiliert wurden, um etwa 30 % erhöhen. Wenn die Paketgröße ein Problem darstellt, sollten Sie Symbole stattdessen in einem Symbolpaket veröffentlichen.

**✔️ Überlegen** Sie sich, ob Sie Symbole als Symbolpaket (`*.snupkg`) auf NuGet.org veröffentlichen möchten

> Mit Symbolpaketen (`*.snupkg`) erhalten Entwickler eine gute abrufbare Debugfunktion, ohne dass die Größe des Hauptpakets und die Wiederherstellungsleistung für diejenigen, die das NuGet-Paket nicht debuggen möchten, beeinträchtigt wird.
>
> Der Nachteil ist, dass Benutzer möglicherweise den NuGet-Symbolserver in ihrer IDE finden und konfigurieren müssen (einmalige Konfiguration), um Symboldateien abzurufen. In Version 16.1 von Visual Studio 2019 wurde der Symbolserver von nuget.org der Liste der Standardsymbolserver hinzugefügt.

>[!div class="step-by-step"]
>[Zurück](strong-naming.md)
>[Weiter](dependencies.md)
