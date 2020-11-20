---
title: 'NETSDK1022: Doppelte Elemente wurden eingeschlossen'
description: Hier erfahren Sie, wie Sie das Problem doppelter eingeschlossener Elemente basierend auf standardmäßig eingeschlossenen Elementen beheben.
author: marcpopMSFT
ms.topic: error-reference
ms.date: 10/9/2020
f1_keywords:
- NETSDK1022
ms.openlocfilehash: bc803f5316bf09c12c563f1a63b8385d1be4e9ce
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506635"
---
# <a name="netsdk1022-duplicate-items-were-included"></a>NETSDK1022: Doppelte Elemente wurden eingeschlossen

**Dieser Artikel gilt für:** ✔️ .NET 2.1.100 SDK und höhere Versionen

Ab Visual Studio 2017/MSBuild-Version 15.3 schließt das .NET SDK standardmäßig automatisch Elemente aus dem Projektverzeichnis ein.  Dazu gehören `Compile`- und `Content`-Ziele.  Dadurch sollte Ihre Projektdatei bereinigt und die vorliegende Komplexität beseitigt werden.

Sie können das alte Verhalten wiederherstellen, indem Sie die richtige Eigenschaft auf FALSE festlegen.

Beispiel für `Compile`-Elemente:

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```
