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
# <a name="netsdk1013-the-targetframework-value-was-not-recognized"></a><span data-ttu-id="39e54-103">NETSDK1013: Der TargetFramework-Wert wurde nicht erkannt.</span><span class="sxs-lookup"><span data-stu-id="39e54-103">NETSDK1013: The TargetFramework value was not recognized</span></span>

<span data-ttu-id="39e54-104">**Dieser Artikel gilt für:** ✔️ .NET 3.1.100 SDK und höher</span><span class="sxs-lookup"><span data-stu-id="39e54-104">**This article applies to:** ✔️ .NET 3.1.100 SDK and later versions</span></span>

<span data-ttu-id="39e54-105">Das SDK versucht die Werte, die in der Projektdatei für `<TargetFramework>` oder `<TargetFrameworks>` bereitgestellt werden, in einen bekannten Wert zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="39e54-105">The SDK tries to parse the values provided in the project file for `<TargetFramework>` or `<TargetFrameworks>` into a well known value.</span></span>  <span data-ttu-id="39e54-106">Wenn der Wert nicht erkannt wird, kann der Wert `TargetFrameworkIdentifier` oder `TargetFrameworkVersion` auf eine leere Zeichenfolge oder `Unsupported` festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="39e54-106">If the value is not recognized, the `TargetFrameworkIdentifier` or `TargetFrameworkVersion` value may be set to an empty string or `Unsupported`.</span></span>

<span data-ttu-id="39e54-107">Überprüfen Sie die Schreibweise des Werts `TargetFramework` aus der Liste der [unterstützten Frameworks](../../../standard/frameworks.md), um dieses Problem zu lösen.</span><span class="sxs-lookup"><span data-stu-id="39e54-107">To resolve this, check the spelling of your `TargetFramework` value from the list of [supported frameworks](../../../standard/frameworks.md).</span></span>
<span data-ttu-id="39e54-108">Sie können die Eigenschaften `TargetFrameworkIdentifier` und `TargetFrameworkVersion` auch direkt in der Projektdatei festlegen.</span><span class="sxs-lookup"><span data-stu-id="39e54-108">You can also set the `TargetFrameworkIdentifier` and `TargetFrameworkVersion` properties directly in your project file.</span></span>

```xml
<PropertyGroup Condition="'$(TargetFrameworkIdentifier)' == ''">
  <TargetFrameworkIdentifier>.NETCOREAPP</TargetFrameworkIdentifier>
  <TargetFrameworkVersion>3.1</TargetFrameworkVersion>
</PropertyGroup>
```
