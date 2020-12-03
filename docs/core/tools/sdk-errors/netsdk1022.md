---
title: 'NETSDK1022: Doppelte Elemente wurden eingeschlossen'
description: Hier erfahren Sie, wie Sie das Problem doppelter eingeschlossener Elemente basierend auf standardmäßig eingeschlossenen Elementen beheben.
author: marcpopMSFT
ms.topic: error-reference
ms.date: 10/9/2020
f1_keywords:
- NETSDK1022
ms.openlocfilehash: c2bdbbb5503e5e4f6e6826f95f5a2cb08c908ceb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717868"
---
# <a name="netsdk1022-duplicate-items-were-included"></a>NETSDK1022: Doppelte Elemente wurden eingeschlossen

**Dieser Artikel gilt für:** ✔️ .NET Core 2.1.100 SDK und höhere Versionen

Ab Visual Studio 2017/MSBuild-Version 15.3 schließt das .NET SDK standardmäßig automatisch Elemente aus dem Projektverzeichnis ein.  Dazu gehören `Compile`- und `Content`-Ziele.  Dadurch sollte Ihre Projektdatei bereinigt und die vorliegende Komplexität beseitigt werden.

Sie können das alte Verhalten wiederherstellen, indem Sie die richtige Eigenschaft auf FALSE festlegen.

Beispiel für `Compile`-Elemente:

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```
