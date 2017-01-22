---
title: "Verwalten von Abhängigkeiten in .NET Core Preview 3-Tools"
description: "Mit Preview 3 werden Änderungen bei der Verwaltung von Abhängigkeiten eingeführt"
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
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 9e715fa49391e239f8a51fc987807cfab8ba95c4

---

# <a name="managing-dependencies-in-net-core-preview-3-tooling"></a>Verwalten von Abhängigkeiten in .NET Core Preview 3-Tools

Mit dem Wechsel von .NET Core-Projekten von „project.json“ zu CSPROJ und MSBuild wurde auch beträchtlicher Aufwand betrieben, der zu einer Vereinheitlichung der Projektdateien und Objekte geführt hat, sodass Abhängigkeiten nachverfolgt werden können. Bei .NET Core-Projekten ist dies mit der Verwendung von „project.json“ vergleichbar. Es gibt keine separate JSON- oder XML-Datei, die NuGet-Abhängigkeiten nachverfolgt. Mit dieser Änderung haben wir auch eine andere Art von *Verweis* in die CSPROJ-Syntax eingeführt: `<PackageReference>`. 

In diesem Dokument wird der neue Verweistyp beschrieben. Es wird außerdem gezeigt, wie mit diesem neuen Verweistyp eine Paketabhängigkeit zum Projekt hinzugefügt wird. 

## <a name="the-new-packagereference-element"></a>Das neue <PackageReference>-Element
`<PackageReference>` weist die folgende grundlegende Struktur auf:

```xml
<PackageReference Include="PACKAGE_ID">
    <Version>PACKAGE_VERSION</Version>
</PackageReference>
```

Wenn Sie mit MSBuild vertraut sind, kommt es Ihnen durch bereits vorhandene [Verweistypen]() bekannt vor. Der Schlüssel ist die `Include`-Anweisung, mit der die Paket-ID angegeben wird, die Sie dem Projekt hinzufügen möchten. Das untergeordnete `<Version>`-Element gibt die abzurufende Version an. Die Versionen werden gemäß den [NuGet-Versionsregeln](https://docs.nuget.org/ndocs/create-packages/dependency-versions#version-ranges) angegeben.  

> [!NOTE]
> Wenn Ihnen die allgemeine `csproj`-Syntax noch unbekannt ist, können Sie sich mithilfe der [Dokumentation zu MSBuild-Projektverweisen]() damit vertraut machen.  

Beim Hinzufügen einer Abhängigkeit, die nur für ein bestimmtes Ziel verfügbar ist, werden keine Bedingungen verwenden:

```xml
<PackageReference Include="PACKAGE_ID" Condition="'$(TargetFramework)' == 'netcoreapp1.0'">
    <Version>PACKAGE_VERSION</Version>
</PackageReference>
```

Der obige Code bedeutet, dass die Abhängigkeit nur gültig ist, wenn der Build für das angegebene Ziel erstellt wird. `$(TargetFramework)` in der Bedingung ist eine MSBuild-Eigenschaft, die im Projekt festgelegt wird. Bei den gängigsten .NET Core-Anwendungen ist dies nicht erforderlich. 

## <a name="adding-a-dependency-to-your-project"></a>Hinzufügen einer Abhängigkeit zu Ihrem Projekt
Es ist einfach, eine Abhängigkeit zu Ihrem Projekt hinzuzufügen. Im folgenden Beispiel wird das Hinzufügen der Json.NET-Version `9.0.1` zu Ihrem Projekt veranschaulicht. Natürlich gilt dies für alle anderen NuGet-Abhängigkeiten. 

Wenn Sie Ihre Projektdatei öffnen, sehen Sie zwei oder mehr `<ItemGroup>`-Knoten. Sie werden feststellen, dass einer der Knoten bereits `<PackageReference>`-Elemente aufweist. Sie können Ihre neue Abhängigkeit zu diesem Knoten hinzufügen oder eine neue erstellen. Sie können frei entscheiden, da das Ergebnis gleich sein wird. 

In diesem Beispiel verwenden wir die Standardvorlage, die von `dotnet new` abgelegt wird. Dies ist eine einfache Konsolenanwendung. Wenn wir das Projekt öffnen, suchen wir zuerst nach `<ItemGroup>` mit dem bereits vorhandenen `<PackageReference>`-Element. Wir fügen dann Folgendes hinzu:

```xml
<PackageReference Include="Newtonsoft.Json">
    <Version>9.0.1</Version>
</PackageReference>
```
Anschließend speichern wir das Projekt und führen den Befehl `dotnet restore` aus, um die Abhängigkeit zu installieren. 

Das vollständige Projekt sieht folgendermaßen aus:

```xml
<Project ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" />
  
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.0</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <Compile Include="**\*.cs" />
    <EmbeddedResource Include="**\*.resx" />
  </ItemGroup>

  <ItemGroup>
    <PackageReference Include="Microsoft.NETCore.App">
      <Version>1.0.1</Version>
    </PackageReference>
    <PackageReference Include="Newtonsoft.Json">
        <Version>9.0.1</Version>
    </PackageReference>
    <PackageReference Include="Microsoft.NET.Sdk">
      <Version>1.0.0-alpha-20161104-2</Version>
      <PrivateAssets>All</PrivateAssets>
    </PackageReference>
  </ItemGroup>
  
  <Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />
</Project>
```

## <a name="removing-a-dependency-from-the-project"></a>Entfernen einer Abhängigkeit aus dem Projekt
Das Entfernen einer Abhängigkeit aus der Projektdatei bedeutet einfach, `<PackageReference>` aus der Projektdatei zu entfernen. 





<!--HONumber=Jan17_HO3-->


