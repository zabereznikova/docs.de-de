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
ms.sourcegitcommit: 1a84c694945fe0c77468eb77274ab46618bccae6
ms.openlocfilehash: 281f1b717a0e220e533078e973711977617a1401

---

# <a name="globaljson-reference"></a>Global.json-Referenz

Die Datei „global.json“ ist in .NET Core Command Line Preview 3 weiterhin vorhanden. Ihr Hauptzweck ist allerdings nicht das Definieren von Lösungsmetadaten wie in früheren Versionen, sondern das Zulassen der Wahl der CLI-Version, die über die `sdk`-Eigenschaft verwendet wird. 

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



<!--HONumber=Nov16_HO3-->


