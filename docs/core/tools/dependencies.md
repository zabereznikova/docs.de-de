---
title: Verwalten von Abhängigkeiten in .NET Core
description: In diesem Artikel wird erläutert, wie Projektabhängigkeiten für eine .NET Core-Anwendung verwaltet werden.
no-loc:
- dotnet add package
- dotnet remove package
- dotnet list package
ms.topic: how-to
ms.date: 02/25/2020
ms.openlocfilehash: 2aeedb56f774b51076764c2772eb02b2fa095d92
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/11/2020
ms.locfileid: "88062859"
---
# <a name="manage-dependencies-in-net-core-applications"></a>Verwalten von Abhängigkeiten in .NET Core-Anwendungen

In diesem Artikel wird erläutert, wie Abhängigkeiten durch Bearbeitung der Projektdatei oder mithilfe der CLI hinzugefügt oder entfernt werden.

## <a name="the-packagereference-element"></a>Das \<PackageReference>-Element

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

* [Paketverweise in Projektdateien](../project-sdk/msbuild-props.md#reference-properties-and-items)
* [dotnet list package-Befehl](dotnet-list-package.md)
