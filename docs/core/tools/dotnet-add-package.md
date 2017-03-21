---
title: Paketbefehl dotnet-add | Microsoft-Dokumentation
description: "Der Paketbefehl „dotnet-add“ bietet eine praktische Option zum Hinzufügen von NuGet-Paketverweisen zu einem Projekt."
keywords: dotnet-add, CLI, CLI-Befehl, .NET Core
author: spboyer
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 88e0da69-a5ea-46cc-8b46-5493242b7af9
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 806f4383452cb250f302dc30ab2d59f7e4772026
ms.lasthandoff: 03/07/2017

---
# <a name="dotnet-add-package"></a>Paket dotnet-add

## <a name="name"></a>Name

`dotnet-add package`: Fügt einen Paketverweis zu einer Projektdatei hinzu.

## <a name="synopsis"></a>Übersicht

```
dotnet add [project] package <package_name> [-v|--version] [-f|--framework] [-n|--no-restore] [-s|--source] [--package-directory]
dotnet add package [-h|--help]
```

## <a name="description"></a>Beschreibung

Der `dotnet add package`-Befehl bietet eine praktische Option zum Hinzufügen von Paketverweisen zu einer Projektdatei. Nach dem Ausführen des Befehls wird die Kompatibilität überprüft, um sicherzustellen, dass das Paket, das hinzugefügt wird, mit allen Frameworks im Projekt kompatibel ist. Wenn die Überprüfung erfolgreich ist, wird [wiederherstellen](dotnet-restore.md) ausgeführt und das `<PackageReference>`-Fragment in der Projektdatei hinzugefügt.

Beispielsweise wird durch Hinzufügen von `Newtonsoft.Json` auf *ToDo.csproj* eine Ausgabe ähnlich der folgenden erzeugt:

```
Microsoft (R) Build Engine version 15.1.545.13942
Copyright (C) Microsoft Corporation. All rights reserved.

  Writing /var/folders/gj/1mgg_4jx7mbdqbhw1kgcpcjr0000gn/T/tmpm0kTMD.tmp
info : Adding PackageReference for package 'Newtonsoft.Json' into project 'ToDo.csproj'.
log  : Restoring packages for ToDo.csproj...
info :   GET https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json
info :   OK https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json 119ms
info :   GET https://api.nuget.org/v3-flatcontainer/newtonsoft.json/9.0.1/newtonsoft.json.9.0.1.nupkg
info :   OK https://api.nuget.org/v3-flatcontainer/newtonsoft.json/9.0.1/newtonsoft.json.9.0.1.nupkg 27ms
info : Package 'Newtonsoft.Json' is compatible with all the specified frameworks in project 'ToDo.csproj'.
info : PackageReference for package 'Newtonsoft.Json' version '9.0.1' added to file 'ToDo.csproj'.
```

Die *ToDo.csproj*-Datei enthält nun ein [`<PackageReference>`](https://docs.microsoft.com/nuget/consume-packages/package-references-in-project-files)-Fragment für das verwiesene Paket.

```xml
<PackageReference Include="Newtonsoft.Json">
  <Version>9.0.1</Version>
</PackageReference>
```

## <a name="arguments"></a>Argumente

`project`

Auszuführende Projektdatei. Wenn keine angegeben ist, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.

`package_name`

Hinzuzufügender Paketverweis.

## <a name="options"></a>Optionen

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

`-v|--version <VERSION>`

Die Version des Pakets.

`-f|--framework <FRAMEWORK>`

Fügt Paketverweise nur hinzu, wenn auf ein bestimmtes Framework abgezielt wird.

`-n|--no-restore`

Fügt Paketverweise hinzu, ohne eine Vorschau der Wiederherstellung und eine Kompatibilitätsüberprüfung durchzuführen.

`-s|--source <SOURCE>`

Verwendet eine bestimmte NuGet-Paketquelle, die während des Wiederherstellungsvorgangs zu verwenden ist.

`--package-directory <PACKAGE_DIRECTORY>`

Stellt das Paket im angegebenen Verzeichnis wieder her.

## <a name="examples"></a>Beispiele

Fügen Sie das `Newtonsoft.Json`-NuGet-Pakets zu einem Projekt hinzu:

`dotnet add package Newtonsoft.Json`

Fügen Sie eine bestimmte Version eines Pakets zu einem Projekt hinzu:

`dotnet add ToDo.csproj package Microsoft.Azure.DocumentDB.Core -v 1.0.0`

Fügen Sie ein Paket mit einer bestimmten NuGet-Quelle hinzu:

`dotnet add package Microsoft.AspNetCore.StaticFiles -s https://dotnet.myget.org/F/dotnet-core/api/v3/index.json`

