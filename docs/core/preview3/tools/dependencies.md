---
title: "Verwalten von Abhängigkeiten in .NET Core-Tools | Microsoft-Dokumentation"
description: "Erläutert, wie Abhängigkeiten mit den .NET Core-Tools verwaltet werden können."
keywords: CLI, Erweiterbarkeit, benutzerdefinierte Befehle, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 11/12/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 74b87cdb-a244-4c13-908c-539118bfeef9
translationtype: Human Translation
ms.sourcegitcommit: 796df1549a7553aa93158598d62338c02d4df73e
ms.openlocfilehash: cef45d986eb9c4a84a03ee942c29a327c23cabf3

---

# <a name="managing-dependencies-in-net-core-rc4-tooling"></a>Verwalten von Abhängigkeiten in .NET Core RC&4;-Tools

[!INCLUDE[preview-warning](../../../includes/warning.md)]

Mit dem Wechsel von .NET Core-Projekten von „project.json“ zu CSPROJ und MSBuild wurde auch beträchtlicher Aufwand betrieben, der zu einer Vereinheitlichung der Projektdatei und Objekte geführt hat, sodass Abhängigkeiten nachverfolgt werden können. Bei .NET Core-Projekten ist dies mit der Verwendung von „project.json“ vergleichbar. Es gibt keine separate JSON- oder XML-Datei, die NuGet-Abhängigkeiten nachverfolgt. Mit dieser Änderung haben wir auch eine andere Art von *Verweis* in die CSPROJ-Syntax eingeführt: `<PackageReference>`. 

In diesem Dokument wird der neue Verweistyp beschrieben. Es wird außerdem gezeigt, wie mit diesem neuen Verweistyp eine Paketabhängigkeit zum Projekt hinzugefügt wird. 

## <a name="the-new-packagereference-element"></a>Das neue <PackageReference>-Element
`<PackageReference>` weist die folgende grundlegende Struktur auf:

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

Wenn Sie mit MSBuild vertraut sind, kommt es Ihnen durch bereits vorhandene Verweistypen bekannt vor. Der Schlüssel ist die `Include`-Anweisung, mit der die Paket-ID angegeben wird, die Sie dem Projekt hinzufügen möchten. Das untergeordnete `<Version>`-Element gibt die abzurufende Version an. Die Versionen werden gemäß den [NuGet-Versionsregeln](https://docs.microsoft.com/nuget/create-packages/dependency-versions#version-ranges) angegeben.

> [!NOTE]
> Wenn Ihnen die allgemeine `csproj`-Syntax noch unbekannt ist, finden Sie weitere Informationen in der Dokumentation zu [MSBuild-Projektverweisen](https://docs.microsoft.com/visualstudio/msbuild/msbuild-project-file-schema-reference).  

Beim Hinzufügen einer Abhängigkeit, die nur für ein bestimmtes Ziel verfügbar ist, werden Bedingungen wie im folgenden Beispiel verwendet:

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp1.0'" />
```

Der obige Code bedeutet, dass die Abhängigkeit nur gültig ist, wenn der Build für das angegebene Ziel erstellt wird. `$(TargetFramework)` in der Bedingung ist eine MSBuild-Eigenschaft, die im Projekt festgelegt wird. Bei den gängigsten .NET Core-Anwendungen ist dies nicht erforderlich. 

## <a name="adding-a-dependency-to-your-project"></a>Hinzufügen einer Abhängigkeit zu Ihrem Projekt
Es ist einfach, eine Abhängigkeit zu Ihrem Projekt hinzuzufügen. Im folgenden Beispiel wird das Hinzufügen der Json.NET-Version `9.0.1` zu Ihrem Projekt veranschaulicht. Natürlich gilt dies für alle anderen NuGet-Abhängigkeiten. 

Wenn Sie Ihre Projektdatei öffnen, sehen Sie zwei oder mehr `<ItemGroup>`-Knoten. Sie werden feststellen, dass einer der Knoten bereits `<PackageReference>`-Elemente aufweist. Sie können Ihre neue Abhängigkeit zu diesem Knoten hinzufügen oder eine neue erstellen. Sie können frei entscheiden, da das Ergebnis gleich sein wird. 

In diesem Beispiel verwenden wir die Standardvorlage, die von `dotnet new` abgelegt wird. Dies ist eine einfache Konsolenanwendung. Wenn wir das Projekt öffnen, suchen wir zuerst nach `<ItemGroup>` mit dem bereits vorhandenen `<PackageReference>`-Element. Wir fügen dann Folgendes hinzu:

```xml
<PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
```
Anschließend speichern wir das Projekt und führen den Befehl `dotnet restore` aus, um die Abhängigkeit zu installieren. 

Das vollständige Projekt sieht folgendermaßen aus:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.0</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
  </ItemGroup>
</Project>
```

## <a name="removing-a-dependency-from-the-project"></a>Entfernen einer Abhängigkeit aus dem Projekt
Das Entfernen einer Abhängigkeit aus der Projektdatei bedeutet einfach, `<PackageReference>` aus der Projektdatei zu entfernen.


<!--HONumber=Feb17_HO2-->


