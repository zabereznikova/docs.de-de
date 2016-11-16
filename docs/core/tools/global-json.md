---
title: Global.json-Referenz | .NET Core
description: Global.json-Referenz
keywords: .NET, .NET Core
author: aL3891
ms.author: mairaw
manager: wpickett
ms.date: 11/02/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: e1ac9659-425f-4486-a376-c12ca942ead8
translationtype: Human Translation
ms.sourcegitcommit: 6f3a46284bd5820520739577919fa202f5b784d7
ms.openlocfilehash: 2353a22ea41c3fbf5700ba40da5cdb89b5bf2872

---

# <a name="globaljson-reference"></a>Global.json-Referenz

Die global.json-Datei wird für Projekte unter .NET Core verwendet, um Lösungsmetadaten zu definieren. Diese Datei wird verwendet, wenn der [dotnet-restore](dotnet-restore.md)-Befehl aufgerufen wird, um die Abhängigkeiten eines .NET Core-Projekts wiederherzustellen.
In diesem Referenzthema finden Sie die Liste der Eigenschaften, die Sie in der Datei „global.json“ definieren können.

## <a name="projects"></a>Projekte
Typ: Zeichenfolge[]

Gibt an, in welchen Ordnern das Buildsystem beim Auflösen von Abhängigkeiten nach Projekten suchen sollte. Das Buildsystem sucht nur nach untergeordneten Ordnern der obersten Ebene.

Beispiel:

```json
{
    "projects": [ "src", "test" ]
}
```

## <a name="packages"></a>Pakete
Typ: Zeichenfolge

Der Speicherort zum Speichern von Paketen.

Beispiel:
```json
{
    "packages": "packages-dir"
}
```

## <a name="sdk"></a>SDK
Typ: Objekt

Gibt Informationen über das SDK an.

### <a name="version"></a>version
Typ: Zeichenfolge

Die Version des zu verwendenden SDKs.

Beispiel:

```json
{
    "sdk": {
        "version": "1.0.0-preview2-003121"
    }
}
```



<!--HONumber=Nov16_HO1-->


