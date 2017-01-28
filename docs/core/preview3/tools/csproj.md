---
title: CSPROJ-Referenz | .NET Core SDK
description: "Erfahren Sie mehr über die Unterschiede zwischen vorhandenen CSPROJ-Dateien und CSPROJ-Dateien von .NET Core"
keywords: Referenz, CSPROJ, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 10/12/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: bdc29497-64f2-4d11-a21b-4097e0bdf5c9
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 1a0178cc5763f06213d45b9b3826c56ce970776c

---

# <a name="additions-to-csproj-format-for-net-core"></a>Erweiterungen des CSPROJ-Formats für .NET Core

In diesem Dokument werden die Änderungen erläutert, die an CSPROJ-Dateien beim Wechsel von „project.json“ zu CSPROJ und [MSBuild](https://github.com/Microsoft/MSBuild) hinzugefügt wurden. In diesem Dokument werden **nur die Änderungen an nicht zum Kern gehörenden CSPROJ-Dateien** dargestellt. Weitere Informationen über die allgemeine Projektdateisyntax und eine Referenz finden Sie in der Dokumentation zur [MSBuild-Projektdatei](). 

> ![HINWEIS]: Dieses Dokument wird in Zukunft erweitert, prüfen Sie es daher bitte auf weitere Ergänzungen. 

## <a name="additions"></a>Erweiterungen

### <a name="packagereference"></a>PackageReference
Gibt eine NuGet-Abhängigkeit im Projekt an. Das `Include`-Attribut gibt die Paket-ID an. 

```xml
<PackageReference Include="<package-id>">
    <Version></Version>
    <PrivateAssets></PrivateAssets>
    <IncludeAssets></IncludeAssets>
    <ExcludeAssets></ExcludeAssets>
</PackageReference>
```

#### <a name="version"></a>Version
`<Version>` gibt die Version des wiederherzustellenden Pakets an. Das Element berücksichtigt die Regeln für das NuGet-Versionsschema.

#### <a name="includeassets"></a>IncludeAssets
Das untergeordnete `<IncludeAssets>`-Element gibt an, welche Objekte, die zum vom übergeordneten `<PackageReference>`-Element angegebenen Paket gehören, genutzt werden sollen. 

Das Element kann einen oder mehrere der folgenden Werte enthalten:

* Compile – gibt an, ob die Inhalte des Ordners „lib“ zum Kompilieren verfügbar sind
* Runtime – gibt an, ob die Inhalte des Ordners „runtime“ verteilt werden
* ContentFiles – gibt an, ob die Inhalte des Ordners „contentfiles“ verwendet werden
* Build – gibt an, ob die Eigenschaften/Ziele im Ordner „build“ verwendet werden
* Native – gibt an, ob die Inhalte der nativen Objekte für die Runtime in den Ausgabeordner kopiert werden
* Analyzers – gibt an, ob Analysen verwendet werden

Alternativ kann das Element Folgendes enthalten:

* None – keines dieser Objekte wird verwendet
* All – alle diese Objekte werden verwendet

#### <a name="excludeassets"></a>ExcludeAssets
Das untergeordnete `<ExcludeAssets>`-Element gibt an, welche Objekte, die zum vom übergeordneten `<PackageReference>`-Element angegebenen Paket gehören, nicht genutzt werden sollen.

Das Element kann einen oder mehrere der folgenden Werte enthalten:

* Compile – gibt an, ob die Inhalte des Ordners „lib“ zum Kompilieren verfügbar sind
* Runtime – gibt an, ob die Inhalte des Ordners „runtime“ verteilt werden
* ContentFiles – gibt an, ob die Inhalte des Ordners „contentfiles“ verwendet werden
* Build – gibt an, ob die Eigenschaften/Ziele im Ordner „build“ verwendet werden
* Native – gibt an, ob die Inhalte der nativen Objekte für die Runtime in den Ausgabeordner kopiert werden
* Analyzers – gibt an, ob Analysen verwendet werden

Alternativ kann das Element Folgendes enthalten:

* None – keines dieser Objekte wird verwendet
* All – alle diese Objekte werden verwendet

#### <a name="privateassets"></a>PrivateAssets
Das untergeordnete `<PrivateAssets>`-Element gibt an, welche Objekte, die zum vom übergeordneten `<PackageReference>`-Element angegebenen Paket gehören, genutzt werden sollen. Sie sollen aber nicht an das nächste Projekt übertragen werden. 

> [!NOTE]
> Dies ist eine neue Bezeichnung für das `SuppressParent`-Element von project.json/xproj. 

Das Element kann einen oder mehrere der folgenden Werte enthalten:

* Compile – gibt an, ob die Inhalte des Ordners „lib“ zum Kompilieren verfügbar sind
* Runtime – gibt an, ob die Inhalte des Ordners „runtime“ verteilt werden
* ContentFiles – gibt an, ob die Inhalte des Ordners „contentfiles“ verwendet werden
* Build – gibt an, ob die Eigenschaften/Ziele im Ordner „build“ verwendet werden
* Native – gibt an, ob die Inhalte der nativen Objekte für die Runtime in den Ausgabeordner kopiert werden
* Analyzers – gibt an, ob Analysen verwendet werden

Alternativ kann das Element Folgendes enthalten:

* None – keines dieser Objekte wird verwendet
* All – alle diese Objekte werden verwendet

### <a name="dotnetclitoolreference"></a>DotnetCliToolReference
Das `<DotnetCliToolReference>`-Element gibt das CLI-Tool an, das der Benutzer im Kontext des Projekts wiederherstellen möchte. Es ist ein Ersatz für den `tools`-Knoten in `project.json`. 

#### <a name="version"></a>Version
`<Version>` gibt die Version des wiederherzustellenden Pakets an. Das Element berücksichtigt die Regeln für das NuGet-Versionsschema.

### <a name="runtimeidentifiers"></a>RuntimeIdentifiers
Das `<RuntimeIdentifiers>`-Element ermöglicht die Angabe einer durch Semikolons getrennten Liste von [Runtime-IDs](../../rid-catalog.md) für das Projekt. Diese ermöglichen das Veröffentlichen eigenständiger Bereitstellungen. 




<!--HONumber=Jan17_HO3-->


