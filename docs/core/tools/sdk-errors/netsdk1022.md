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
# <a name="netsdk1022-duplicate-items-were-included"></a><span data-ttu-id="f38bc-103">NETSDK1022: Doppelte Elemente wurden eingeschlossen</span><span class="sxs-lookup"><span data-stu-id="f38bc-103">NETSDK1022: Duplicate items were included.</span></span>

<span data-ttu-id="f38bc-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.1.100 SDK und höhere Versionen</span><span class="sxs-lookup"><span data-stu-id="f38bc-104">**This article applies to:** ✔️ .NET Core 2.1.100 SDK and later versions</span></span>

<span data-ttu-id="f38bc-105">Ab Visual Studio 2017/MSBuild-Version 15.3 schließt das .NET SDK standardmäßig automatisch Elemente aus dem Projektverzeichnis ein.</span><span class="sxs-lookup"><span data-stu-id="f38bc-105">Starting in Visual Studio 2017 / MSBuild version 15.3, the .NET SDK automatically includes items from the project directory by default.</span></span>  <span data-ttu-id="f38bc-106">Dazu gehören `Compile`- und `Content`-Ziele.</span><span class="sxs-lookup"><span data-stu-id="f38bc-106">This includes `Compile` and `Content` targets.</span></span>  <span data-ttu-id="f38bc-107">Dadurch sollte Ihre Projektdatei bereinigt und die vorliegende Komplexität beseitigt werden.</span><span class="sxs-lookup"><span data-stu-id="f38bc-107">This should greatly clean up your project file and reduce the complexity you have there.</span></span>

<span data-ttu-id="f38bc-108">Sie können das alte Verhalten wiederherstellen, indem Sie die richtige Eigenschaft auf FALSE festlegen.</span><span class="sxs-lookup"><span data-stu-id="f38bc-108">You can revert to the earlier behavior by setting the correct property to false.</span></span>

<span data-ttu-id="f38bc-109">Beispiel für `Compile`-Elemente:</span><span class="sxs-lookup"><span data-stu-id="f38bc-109">Example for `Compile` items:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```
