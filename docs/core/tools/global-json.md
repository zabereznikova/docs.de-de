---
title: global.json-Referenz | Microsoft-Dokumentation
description: Global.json-Referenz
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 04/05/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 96102f96-d403-4385-8ef6-5d80e406eb0c
ms.translationtype: Human Translation
ms.sourcegitcommit: ec7028d43e7236056e5a53160f6017edadfec8c2
ms.openlocfilehash: a35938d355cb86205e9c822736862298508cf861
ms.contentlocale: de-de
ms.lasthandoff: 04/06/2017

---

# <a name="globaljson-reference"></a>Global.json-Referenz

Die *global.json*-Datei ermöglicht die Auswahl der .NET Core-Toolversionen, die über die `sdk`-Eigenschaft verwendet werden.

.NET Core-CLI-Tools suchen nach dieser Datei im aktuellen Arbeitsverzeichnis (das nicht unbedingt das gleiche wie das Projektverzeichnis ist) oder in einem der übergeordneten Verzeichnissen.

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

