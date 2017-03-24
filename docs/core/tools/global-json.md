---
title: global.json-Referenz | Microsoft-Dokumentation
description: Global.json-Referenz
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/06/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 96102f96-d403-4385-8ef6-5d80e406eb0c
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 253b8642ae6fc5308d47552e9addfdbed6813ff1
ms.lasthandoff: 03/07/2017

---

# <a name="globaljson-reference"></a>Global.json-Referenz

Die global.json-Datei ermöglicht die Auswahl der .NET Core-Toolversionen, die über die `sdk`-Eigenschaft verwendet werden. 

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
