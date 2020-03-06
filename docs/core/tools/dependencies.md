---
title: Verwalten von Abhängigkeiten in .NET Core
description: In diesem Artikel wird erläutert, wie Projektabhängigkeiten für eine .NET Core-Anwendung verwaltet werden.
no-loc:
- dotnet add package
- dotnet remove package
- dotnet list package
ms.date: 02/25/2020
ms.openlocfilehash: 367be7eb04d58bffc0846de1d035a5801e8d9376
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157244"
---
# <a name="manage-dependencies-in-net-core-applications"></a>Verwalten von Abhängigkeiten in .NET Core-Anwendungen

In diesem Artikel wird erläutert, wie Abhängigkeiten durch Bearbeitung der Projektdatei oder mithilfe der CLI hinzugefügt oder entfernt werden.

## <a name="the-packagereference-element"></a>Das Element \<PackageReference>

Das Projektdateielement `<PackageReference>` weist die folgende Struktur auf:

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

Das Attribut `Include` gibt die ID des Pakets an, das zum Projekt hinzugefügt werden soll. Das `Version`-Attribut gibt die abzurufende Version an. Versionen werden gemäß der [NuGet-Versionsregeln](/nuget/create-packages/dependency-versions#version-ranges) angegeben.

> [!NOTE]
> Wenn Sie nicht mit der Projektdateisyntax vertraut sind, finden Sie weitere Informationen in der [Referenz zu MSBuild-Projekten](/visualstudio/msbuild/msbuild-project-file-schema-reference).

Verwenden Sie wie im folgenden Beispiel gezeigt Bedingungen, um eine Abhängigkeit hinzuzufügen, die nur in einem bestimmten Ziel verfügbar ist:

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp2.1'" />
```

Die Abhängigkeit im obigen Beispiel ist nur dann gültig, wenn der Build für das angegebene Ziel erstellt wird. `$(TargetFramework)` in der Bedingung ist eine MSBuild-Eigenschaft, die im Projekt festgelegt wird. Bei den gängigsten .NET Core-Anwendungen ist dies nicht erforderlich.

## <a name="add-a-dependency-by-editing-the-project-file"></a>Hinzufügen einer Abhängigkeit durch Bearbeiten der Projektdatei

Fügen Sie ein `<PackageReference>`-Element in ein `<ItemGroup>`-Element ein, um eine Abhängigkeit hinzuzufügen. Sie können zu einem vorhandenen `<ItemGroup>`-Element hinzufügen oder ein neues erstellen. Im folgenden Beispiel wird das Standard-Konsolenanwendungsprojekt verwendet, das von `dotnet new console` erstellt wird:

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Microsoft.EntityFrameworkCore" Version="3.1.2" />
  </ItemGroup>

</Project>
```

## <a name="add-a-dependency-by-using-the-cli"></a>Hinzufügen einer Abhängigkeit mithilfe der CLI

Führen Sie den Befehl [dotnet add package](dotnet-add-package.md) wie im folgenden Beispiel gezeigt aus, um eine Abhängigkeit hinzuzufügen:

```dotnetcli
dotnet add package Microsoft.EntityFrameworkCore
```

## <a name="remove-a-dependency-by-editing-the-project-file"></a>Entfernen einer Abhängigkeit durch Bearbeiten der Projektdatei

Entfernen Sie das jeweilige `<PackageReference>`-Element aus der Projektdatei, um eine Abhängigkeit zu entfernen.

## <a name="remove-a-dependency-by-using-the-cli"></a>Entfernen einer Abhängigkeit mithilfe der CLI

Führen Sie den Befehl [dotnet remove package](dotnet-remove-package.md) wie im folgenden Beispiel gezeigt aus, um eine Abhängigkeit zu entfernen:

```dotnetcli
dotnet remove package Microsoft.EntityFrameworkCore
```

## <a name="see-also"></a>Siehe auch

* [NuGet-Pakete in Projektdateien](../project-sdk/msbuild-props.md#nuget-packages)
* [dotnet list package-Befehl](dotnet-remove-package.md)
