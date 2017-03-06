---
title: global.json-Referenz | Microsoft-Dokumentation
description: Global.json-Referenz
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 11/02/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 96102f96-d403-4385-8ef6-5d80e406eb0c
translationtype: Human Translation
ms.sourcegitcommit: 796df1549a7553aa93158598d62338c02d4df73e
ms.openlocfilehash: b814bfc79c2fcd0fd15b9494c18c6d0443a70fb1

---

# <a name="globaljson-reference-net-core-tools-rc4"></a>global.json-Referenz (.NET Core Tools RC4)

> [!WARNING]
> Dieses Thema gilt für .NET Core Tools RC4. Das Thema [global.json-Referenz](../../tools/global-json.md) gilt für .NET Core Preview 2-Tools.

Die Datei „global.json“ ist weiterhin in den Befehlszeilentools von .NET Core RC4 vorhanden. Ihr Hauptzweck ist allerdings nicht das Definieren von Lösungsmetadaten wie in früheren Versionen, sondern das Zulassen der Wahl der CLI-Version, die über die `sdk`-Eigenschaft verwendet wird. 

In dieser Referenz wird dies berücksichtigt. 

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


<!--HONumber=Feb17_HO2-->


