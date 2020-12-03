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
# <a name="netsdk1013-the-targetframework-value-was-not-recognized"></a><span data-ttu-id="aff82-103">NETSDK1013: Der TargetFramework-Wert wurde nicht erkannt.</span><span class="sxs-lookup"><span data-stu-id="aff82-103">NETSDK1013: The TargetFramework value was not recognized</span></span>

<span data-ttu-id="aff82-104">**Dieser Artikel gilt für:** ✔️ .NET Core 3.1.100 SDK und höher</span><span class="sxs-lookup"><span data-stu-id="aff82-104">**This article applies to:** ✔️ .NET Core 3.1.100 SDK and later versions</span></span>

<span data-ttu-id="aff82-105">Das SDK versucht die Werte, die in der Projektdatei für `<TargetFramework>` oder `<TargetFrameworks>` bereitgestellt werden, in einen bekannten Wert zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="aff82-105">The SDK tries to parse the values provided in the project file for `<TargetFramework>` or `<TargetFrameworks>` into a well known value.</span></span>  <span data-ttu-id="aff82-106">Wenn der Wert nicht erkannt wird, kann der Wert `TargetFrameworkIdentifier` oder `TargetFrameworkVersion` auf eine leere Zeichenfolge oder `Unsupported` festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="aff82-106">If the value is not recognized, the `TargetFrameworkIdentifier` or `TargetFrameworkVersion` value may be set to an empty string or `Unsupported`.</span></span>

<span data-ttu-id="aff82-107">Überprüfen Sie die Schreibweise des Werts `TargetFramework` aus der Liste der [unterstützten Frameworks](../../../standard/frameworks.md), um dieses Problem zu lösen.</span><span class="sxs-lookup"><span data-stu-id="aff82-107">To resolve this, check the spelling of your `TargetFramework` value from the list of [supported frameworks](../../../standard/frameworks.md).</span></span>
<span data-ttu-id="aff82-108">Sie können die Eigenschaften `TargetFrameworkIdentifier` und `TargetFrameworkVersion` auch direkt in der Projektdatei festlegen.</span><span class="sxs-lookup"><span data-stu-id="aff82-108">You can also set the `TargetFrameworkIdentifier` and `TargetFrameworkVersion` properties directly in your project file.</span></span>

```xml
<PropertyGroup Condition="'$(TargetFrameworkIdentifier)' == ''">
  <TargetFrameworkIdentifier>.NETCOREAPP</TargetFrameworkIdentifier>
  <TargetFrameworkVersion>3.1</TargetFrameworkVersion>
</PropertyGroup>
```
