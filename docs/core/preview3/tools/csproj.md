---
title: CSPROJ-Referenz | .NET Core SDK
description: "Erfahren Sie mehr über die Unterschiede zwischen vorhandenen CSPROJ-Dateien und CSPROJ-Dateien von .NET Core"
keywords: Referenz, CSPROJ, .NET Core
author: blackdwarf
ms.author: mairaw
manager: wpickett
ms.date: 10/12/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: bdc29497-64f2-4d11-a21b-4097e0bdf5c9
translationtype: Human Translation
ms.sourcegitcommit: 1a84c694945fe0c77468eb77274ab46618bccae6
ms.openlocfilehash: af32bc592762d7e8cb4e3b180656d9c3464df4a5

---

<a name="additions-to-csproj-format-for-net-core"></a>Erweiterungen des CSPROJ-Formats für .NET Core
----------------------------------------

# <a name="overview"></a>Übersicht 
In diesem Dokument werden die Änderungen erläutert, die an CSPROJ-Dateien beim Wechsel von „project.json“ zu CSPROJ und [MSBuild](https://github.com/Microsoft/MSBuild) hinzugefügt wurden. In diesem Dokument werden **nur die Änderungen an nicht zum Kern gehörenden CSPROJ-Dateien** dargestellt. Weitere Informationen über die allgemeine Projektdateisyntax und eine Referenz finden Sie in der Dokumentation zur [MSBuild-Projektdatei](). 

> **Hinweis:** Dieses Dokument wird in Zukunft erweitert, prüfen Sie es daher bitte auf weitere Ergänzungen. 

# <a name="additions"></a>Erweiterungen

## <a name="packagereference"></a>PackageReference
Gibt eine NuGet-Abhängigkeit im Projekt an. Das `Include`-Attribut gibt die Paket-ID an. 

```xml
<PackageReference Include="<package-id>">
    <Version></Version>
    <PrivateAssets></PrivateAssets>
    <IncludeAssets></IncludeAssets>
    <ExcludeAssets></ExcludeAssets>
</PackageReference>
```

### <a name="version"></a>Version
`<Version>` gibt die Version des wiederherzustellenden Pakets an. Das Element berücksichtigt die Regeln für das NuGet-Versionsschema.

### <a name="includeassets"></a>IncludeAssets
Das untergeordnete `<IncludeAssets>`-Element gibt an, welche Objekte, die zum vom übergeordneten `<PackageReference>`-Element angegebenen Paket gehören, genutzt werden sollen. 

Das Element kann einen oder mehrere der folgenden Werte enthalten:

* Compile – Gibt an, ob die Inhalte des Ordners „lib“ zum Kompilieren verfügbar sind
* Runtime – Gibt an, ob die Inhalte des Ordners „runtime“ verteilt werden
* ContentFiles – Gibt an, ob die Inhalte des Ordners „contentfiles“ verwendet werden
* Build – Gibt an, ob die Eigenschaften/Ziele im Ordner „build“ verwendet werden
* Native – Gibt an, ob die Inhalte der nativen Objekte für die Runtime in den Ausgabeordner kopiert werden
* Analyzers – Gibt an, ob Analysen verwendet werden

Alternativ kann das Element Folgendes enthalten:

* None – Keines dieser Objekte wird verwendet
* All – Alle dieser Objekte werden verwendet

### <a name="excludeassets"></a>ExcludeAssets
Das untergeordnete `<ExcluseAssets>`-Element gibt an, welche Objekte, die zum vom übergeordneten `<PackageReference>`-Element angegebenen Paket gehören, nicht genutzt werden sollen.

Das Element kann einen oder mehrere der folgenden Werte enthalten:

* Compile – Gibt an, ob die Inhalte des Ordners „lib“ zum Kompilieren verfügbar sind
* Runtime – Gibt an, ob die Inhalte des Ordners „runtime“ verteilt werden
* ContentFiles – Gibt an, ob die Inhalte des Ordners „contentfiles“ verwendet werden
* Build – Gibt an, ob die Eigenschaften/Ziele im Ordner „build“ verwendet werden
* Native – Gibt an, ob die Inhalte der nativen Objekte für die Runtime in den Ausgabeordner kopiert werden
* Analyzers – Gibt an, ob Analysen verwendet werden

Alternativ kann das Element Folgendes enthalten:

* None – Keines dieser Objekte wird verwendet
* All – Alle dieser Objekte werden verwendet

### <a name="privateassets"></a>PrivateAssets
Das untergeordnete `<PrivateAssets>`-Element gibt an, welche Objekte, die zum vom übergeordneten `<PackageReference>`-Element angegebenen Paket gehören, genutzt werden sollen. Sie sollen aber nicht an das nächste Projekt übertragen werden. 

> **Hinweis:** Dies ist eine neue Bezeichnung für das `SupressParent`-Element von project.json/xproj. 

Das Element kann einen oder mehrere der folgenden Werte enthalten:

* Compile – Gibt an, ob die Inhalte des Ordners „lib“ zum Kompilieren verfügbar sind
* Runtime – Gibt an, ob die Inhalte des Ordners „runtime“ verteilt werden
* ContentFiles – Gibt an, ob die Inhalte des Ordners „contentfiles“ verwendet werden
* Build – Gibt an, ob die Eigenschaften/Ziele im Ordner „build“ verwendet werden
* Native – Gibt an, ob die Inhalte der nativen Objekte für die Runtime in den Ausgabeordner kopiert werden
* Analyzers – Gibt an, ob Analysen verwendet werden

Alternativ kann das Element Folgendes enthalten:

* None – Keines dieser Objekte wird verwendet
* All – Alle dieser Objekte werden verwendet

## <a name="dotnetclitoolreference"></a>DotnetCliToolReference
Das `<DotnetCliToolReference>`-Element gibt das CLI-Tool an, das der Benutzer im Kontext des Projekts wiederherstellen möchte. Es ist ein Ersatz für den `tools`-Knoten in `project.json`. 

### <a name="version"></a>Version
`<Version>` gibt die Version des wiederherzustellenden Pakets an. Das Element berücksichtigt die Regeln für das NuGet-Versionsschema.

## <a name="runtimeidentifiers"></a>RuntimeIdentifiers
Das `<RuntimeIdentifiers>`-Element ermöglicht die Angabe einer durch Semikolons getrennten Liste von [Runtime-IDs](../../rid-catalog.md) für das Projekt. Diese ermöglichen das Veröffentlichen eigenständiger Bereitstellungen. 




<!--HONumber=Nov16_HO3-->


