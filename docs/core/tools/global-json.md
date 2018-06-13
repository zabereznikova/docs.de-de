---
title: Global.json-Referenz
description: Weitere Informationen finden Sie im Schema für die globale JSON-Datei, die das Festlegen der .NET Core-Toolsversion zulässt.
author: blackdwarf
ms.author: mairaw
ms.date: 04/05/2017
ms.openlocfilehash: 7479774c7b9cdda233cf32d791c16e7fc6d733a8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33209969"
---
# <a name="globaljson-reference"></a><span data-ttu-id="000f2-103">Global.json-Referenz</span><span class="sxs-lookup"><span data-stu-id="000f2-103">global.json reference</span></span>

<span data-ttu-id="000f2-104">Die *global.json*-Datei ermöglicht die Auswahl der .NET Core-Toolversionen, die über die `sdk`-Eigenschaft verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="000f2-104">The *global.json* file allows selection of the .NET Core tools version being used through the `sdk` property.</span></span>

<span data-ttu-id="000f2-105">.NET Core-CLI-Tools suchen nach dieser Datei im aktuellen Arbeitsverzeichnis (das nicht unbedingt das gleiche wie das Projektverzeichnis ist) oder in einem der übergeordneten Verzeichnissen.</span><span class="sxs-lookup"><span data-stu-id="000f2-105">.NET Core CLI tools look for this file in the current working directory (which isn't necessarily the same as the project directory) or one of its parent directories.</span></span>

## <a name="sdk"></a><span data-ttu-id="000f2-106">SDK</span><span class="sxs-lookup"><span data-stu-id="000f2-106">sdk</span></span>
<span data-ttu-id="000f2-107">Typ: Objekt</span><span class="sxs-lookup"><span data-stu-id="000f2-107">Type: Object</span></span>

<span data-ttu-id="000f2-108">Gibt Informationen über das SDK an.</span><span class="sxs-lookup"><span data-stu-id="000f2-108">Specifies information about the SDK.</span></span>

### <a name="version"></a><span data-ttu-id="000f2-109">Version</span><span class="sxs-lookup"><span data-stu-id="000f2-109">version</span></span>
<span data-ttu-id="000f2-110">Typ: Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="000f2-110">Type: String</span></span>

<span data-ttu-id="000f2-111">Die Version des zu verwendenden SDKs.</span><span class="sxs-lookup"><span data-stu-id="000f2-111">The version of the SDK to use.</span></span>

<span data-ttu-id="000f2-112">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="000f2-112">For example:</span></span>

```json
{
  "sdk": {
    "version": "1.0.0-preview2-003121"
  }
}
```
