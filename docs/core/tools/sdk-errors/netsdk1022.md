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
# <a name="netsdk1022-duplicate-items-were-included"></a><span data-ttu-id="eb918-103">NETSDK1022: Doppelte Elemente wurden eingeschlossen</span><span class="sxs-lookup"><span data-stu-id="eb918-103">NETSDK1022: Duplicate items were included.</span></span>

<span data-ttu-id="eb918-104">**Dieser Artikel gilt für:** ✔️ .NET 2.1.100 SDK und höhere Versionen</span><span class="sxs-lookup"><span data-stu-id="eb918-104">**This article applies to:** ✔️ .NET 2.1.100 SDK and later versions</span></span>

<span data-ttu-id="eb918-105">Ab Visual Studio 2017/MSBuild-Version 15.3 schließt das .NET SDK standardmäßig automatisch Elemente aus dem Projektverzeichnis ein.</span><span class="sxs-lookup"><span data-stu-id="eb918-105">Starting in Visual Studio 2017 / MSBuild version 15.3, the .NET SDK automatically includes items from the project directory by default.</span></span>  <span data-ttu-id="eb918-106">Dazu gehören `Compile`- und `Content`-Ziele.</span><span class="sxs-lookup"><span data-stu-id="eb918-106">This includes `Compile` and `Content` targets.</span></span>  <span data-ttu-id="eb918-107">Dadurch sollte Ihre Projektdatei bereinigt und die vorliegende Komplexität beseitigt werden.</span><span class="sxs-lookup"><span data-stu-id="eb918-107">This should greatly clean up your project file and reduce the complexity you have there.</span></span>

<span data-ttu-id="eb918-108">Sie können das alte Verhalten wiederherstellen, indem Sie die richtige Eigenschaft auf FALSE festlegen.</span><span class="sxs-lookup"><span data-stu-id="eb918-108">You can revert to the earlier behavior by setting the correct property to false.</span></span>

<span data-ttu-id="eb918-109">Beispiel für `Compile`-Elemente:</span><span class="sxs-lookup"><span data-stu-id="eb918-109">Example for `Compile` items:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```
