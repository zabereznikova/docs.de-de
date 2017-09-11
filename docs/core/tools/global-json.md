---
title: Global.json-Referenz
description: "Weitere Informationen finden Sie im Schema für die globale JSON-Datei, die das Festlegen der .NET Core-Toolsversion zulässt."
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 04/05/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 96102f96-d403-4385-8ef6-5d80e406eb0c
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ffa97164736fc7f3edc450682d23bdf499b6eb34
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="globaljson-reference"></a><span data-ttu-id="fcd65-104">Global.json-Referenz</span><span class="sxs-lookup"><span data-stu-id="fcd65-104">global.json reference</span></span>

<span data-ttu-id="fcd65-105">Die *global.json*-Datei ermöglicht die Auswahl der .NET Core-Toolversionen, die über die `sdk`-Eigenschaft verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fcd65-105">The *global.json* file allows selection of the .NET Core tools version being used through the `sdk` property.</span></span>

<span data-ttu-id="fcd65-106">.NET Core-CLI-Tools suchen nach dieser Datei im aktuellen Arbeitsverzeichnis (das nicht unbedingt das gleiche wie das Projektverzeichnis ist) oder in einem der übergeordneten Verzeichnissen.</span><span class="sxs-lookup"><span data-stu-id="fcd65-106">.NET Core CLI tools look for this file in the current working directory (which isn't necessarily the same as the project directory) or one of its parent directories.</span></span>

## <a name="sdk"></a><span data-ttu-id="fcd65-107">SDK</span><span class="sxs-lookup"><span data-stu-id="fcd65-107">sdk</span></span>
<span data-ttu-id="fcd65-108">Typ: Objekt</span><span class="sxs-lookup"><span data-stu-id="fcd65-108">Type: Object</span></span>

<span data-ttu-id="fcd65-109">Gibt Informationen über das SDK an.</span><span class="sxs-lookup"><span data-stu-id="fcd65-109">Specifies information about the SDK.</span></span>

### <a name="version"></a><span data-ttu-id="fcd65-110">version</span><span class="sxs-lookup"><span data-stu-id="fcd65-110">version</span></span>
<span data-ttu-id="fcd65-111">Typ: Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="fcd65-111">Type: String</span></span>

<span data-ttu-id="fcd65-112">Die Version des zu verwendenden SDKs.</span><span class="sxs-lookup"><span data-stu-id="fcd65-112">The version of the SDK to use.</span></span>

<span data-ttu-id="fcd65-113">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="fcd65-113">For example:</span></span>

```json
{
  "sdk": {
    "version": "1.0.0-preview2-003121"
  }
}
```

