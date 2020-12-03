---
title: 'NETSDK1013: Der TargetFramework-Wert wurde nicht erkannt.'
description: Bestimmen und Festlegen eines gültigen TargetFramework-Werts
author: marcpop
ms.topic: error-reference
ms.date: 10/9/2020
f1_keywords:
- NETSDK1013
ms.openlocfilehash: 915ac22ad822d17c082498b469acbfb3f1a93efc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717869"
---
# <a name="netsdk1013-the-targetframework-value-was-not-recognized"></a>NETSDK1013: Der TargetFramework-Wert wurde nicht erkannt.

**Dieser Artikel gilt für:** ✔️ .NET Core 3.1.100 SDK und höher

Das SDK versucht die Werte, die in der Projektdatei für `<TargetFramework>` oder `<TargetFrameworks>` bereitgestellt werden, in einen bekannten Wert zu analysieren.  Wenn der Wert nicht erkannt wird, kann der Wert `TargetFrameworkIdentifier` oder `TargetFrameworkVersion` auf eine leere Zeichenfolge oder `Unsupported` festgelegt werden.

Überprüfen Sie die Schreibweise des Werts `TargetFramework` aus der Liste der [unterstützten Frameworks](../../../standard/frameworks.md), um dieses Problem zu lösen.
Sie können die Eigenschaften `TargetFrameworkIdentifier` und `TargetFrameworkVersion` auch direkt in der Projektdatei festlegen.

```xml
<PropertyGroup Condition="'$(TargetFrameworkIdentifier)' == ''">
  <TargetFrameworkIdentifier>.NETCOREAPP</TargetFrameworkIdentifier>
  <TargetFrameworkVersion>3.1</TargetFrameworkVersion>
</PropertyGroup>
```
