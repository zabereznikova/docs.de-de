---
title: Verwalten von Abhängigkeiten in .NET Core-Tools
description: Erläutert, wie Abhängigkeiten mit den .NET Core-Tools verwaltet werden können.
ms.date: 03/06/2017
ms.openlocfilehash: 916daca0240c10dc63ca96048590a426bc51d450
ms.sourcegitcommit: feb42222f1430ca7b8115ae45e7a38fc4a1ba623
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/02/2020
ms.locfileid: "76965619"
---
# <a name="manage-dependencies-with-net-core-sdk-10"></a>Verwalten von Abhängigkeiten mit .NET Core SDK 1.0

Mit dem Wechsel von .NET Core-Projekten von „project.json“ zu „csproj“ und MSBuild wurde auch ein beträchtlicher Aufwand betrieben, der zu einer Vereinheitlichung der Projektdatei und Objekte geführt hat, sodass Abhängigkeiten nachverfolgt werden können. Bei .NET Core-Projekten ist dies mit der Verwendung von „project.json“ vergleichbar. Es gibt keine separate JSON- oder XML-Datei, die NuGet-Abhängigkeiten nachverfolgt. Mit dieser Änderung haben wir auch eine andere Art von *Verweis* in die CSPROJ-Syntax eingeführt: `<PackageReference>`.

In diesem Dokument wird der neue Verweistyp beschrieben. Es wird außerdem gezeigt, wie mit diesem neuen Verweistyp eine Paketabhängigkeit zum Projekt hinzugefügt wird.

## <a name="the-new-packagereference-element"></a>Das neue \<PackageReference>-Element

`<PackageReference>` weist die folgende grundlegende Struktur auf:

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

Wenn Sie mit MSBuild vertraut sind, kommt es Ihnen durch bereits vorhandene Verweistypen bekannt vor. Der Schlüssel ist die `Include`-Anweisung, mit der die Paket-ID angegeben wird, die Sie dem Projekt hinzufügen möchten. Das untergeordnete `<Version>`-Element gibt die abzurufende Version an. Die Versionen werden gemäß den [NuGet-Versionsregeln](/nuget/create-packages/dependency-versions#version-ranges) angegeben.

> [!NOTE]
> Wenn Ihnen die Projektdateisyntax noch unbekannt ist, finden Sie weitere Informationen in der Dokumentation zu [MSBuild-Projektverweisen](/visualstudio/msbuild/msbuild-project-file-schema-reference).

Verwenden Sie wie im folgenden Beispiel gezeigt Bedingungen, um eine Abhängigkeit hinzuzufügen, die nur in einem bestimmten Ziel verfügbar ist:

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp2.1'" />
```

Die Abhängigkeit ist nur dann gültig, wenn der Build für das angegebene Ziel erstellt wird. `$(TargetFramework)` in der Bedingung ist eine MSBuild-Eigenschaft, die im Projekt festgelegt wird. Bei den gängigsten .NET Core-Anwendungen ist dies nicht erforderlich.

## <a name="add-a-dependency-to-the-project"></a>Hinzufügen einer Abhängigkeit zum Projekt

Es ist einfach, eine Abhängigkeit zu Ihrem Projekt hinzuzufügen. Im folgenden Beispiel wird das Hinzufügen der Json.NET-Version `9.0.1` zu Ihrem Projekt veranschaulicht. Natürlich gilt dies für alle anderen NuGet-Abhängigkeiten.

Ihre Projektdatei verfügt über zwei oder mehr `<ItemGroup>`-Knoten. Einer der Knoten weist bereits `<PackageReference>`-Elemente auf. Sie können Ihre neue Abhängigkeit zu diesem Knoten hinzufügen oder einen neuen Knoten erstellen. Das Ergebnis dieser beiden Optionen ist gleich.

Das folgende Beispiel verwendet die Standardvorlage, die von `dotnet new console` erstellt wird. Dies ist eine einfache Konsolenanwendung. Wenn Sie das Projekt öffnen, sehen Sie die `<ItemGroup>` mit dem bereits vorhandenen `<PackageReference>`-Element. Fügen Sie Folgendes hinzu:

```xml
<PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
```

Anschließend speichern Sie das Projekt und führen den Befehl `dotnet restore` aus, um die Abhängigkeit zu installieren.

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

Das vollständige Projekt sieht folgendermaßen aus:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
  </ItemGroup>
</Project>
```

## <a name="remove-a-dependency-from-the-project"></a>Entfernen einer Abhängigkeit aus dem Projekt

Das Entfernen einer Abhängigkeit aus der Projektdatei bedeutet einfach, `<PackageReference>` aus der Projektdatei zu entfernen.
