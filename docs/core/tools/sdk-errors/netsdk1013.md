---
title: 'NETSDK1013: Der TargetFramework-Wert wurde nicht erkannt.'
description: Bestimmen und Festlegen eines gültigen TargetFramework-Werts
author: marcpop
ms.topic: error-reference
ms.date: 10/9/2020
f1_keywords:
- NETSDK1013
ms.openlocfilehash: bcaed878b663f8bc957e8469ffd78caa9babf710
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94445675"
---
# <a name="netsdk1013-the-targetframework-value-was-not-recognized"></a>NETSDK1013: Der TargetFramework-Wert wurde nicht erkannt.

**Dieser Artikel gilt für:** ✔️ .NET 3.1.100 SDK und höher

Das SDK versucht die Werte, die in der Projektdatei für `<TargetFramework>` oder `<TargetFrameworks>` bereitgestellt werden, in einen bekannten Wert zu analysieren.  Wenn der Wert nicht erkannt wird, kann der Wert `TargetFrameworkIdentifier` oder `TargetFrameworkVersion` auf eine leere Zeichenfolge oder `Unsupported` festgelegt werden.

Überprüfen Sie die Schreibweise des Werts `TargetFramework` aus der Liste der [unterstützten Frameworks](../../../standard/frameworks.md), um dieses Problem zu lösen.
Sie können die Eigenschaften `TargetFrameworkIdentifier` und `TargetFrameworkVersion` auch direkt in der Projektdatei festlegen.

```xml
<PropertyGroup Condition="'$(TargetFrameworkIdentifier)' == ''">
  <TargetFrameworkIdentifier>.NETCOREAPP</TargetFrameworkIdentifier>
  <TargetFrameworkVersion>3.1</TargetFrameworkVersion>
</PropertyGroup>
```
