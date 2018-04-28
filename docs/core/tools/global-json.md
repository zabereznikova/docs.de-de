---
title: Global.json-Referenz
description: Weitere Informationen finden Sie im Schema für die globale JSON-Datei, die das Festlegen der .NET Core-Toolsversion zulässt.
author: blackdwarf
ms.author: mairaw
ms.date: 04/05/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.workload:
- dotnetcore
ms.openlocfilehash: ac53a899e76c99527f2670d0a6bed3f8cc6ce31f
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="globaljson-reference"></a><span data-ttu-id="b8480-103">Global.json-Referenz</span><span class="sxs-lookup"><span data-stu-id="b8480-103">global.json reference</span></span>

<span data-ttu-id="b8480-104">Die *global.json*-Datei ermöglicht die Auswahl der .NET Core-Toolversionen, die über die `sdk`-Eigenschaft verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b8480-104">The *global.json* file allows selection of the .NET Core tools version being used through the `sdk` property.</span></span>

<span data-ttu-id="b8480-105">.NET Core-CLI-Tools suchen nach dieser Datei im aktuellen Arbeitsverzeichnis (das nicht unbedingt das gleiche wie das Projektverzeichnis ist) oder in einem der übergeordneten Verzeichnissen.</span><span class="sxs-lookup"><span data-stu-id="b8480-105">.NET Core CLI tools look for this file in the current working directory (which isn't necessarily the same as the project directory) or one of its parent directories.</span></span>

## <a name="sdk"></a><span data-ttu-id="b8480-106">SDK</span><span class="sxs-lookup"><span data-stu-id="b8480-106">sdk</span></span>
<span data-ttu-id="b8480-107">Typ: Objekt</span><span class="sxs-lookup"><span data-stu-id="b8480-107">Type: Object</span></span>

<span data-ttu-id="b8480-108">Gibt Informationen über das SDK an.</span><span class="sxs-lookup"><span data-stu-id="b8480-108">Specifies information about the SDK.</span></span>

### <a name="version"></a><span data-ttu-id="b8480-109">Version</span><span class="sxs-lookup"><span data-stu-id="b8480-109">version</span></span>
<span data-ttu-id="b8480-110">Typ: Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="b8480-110">Type: String</span></span>

<span data-ttu-id="b8480-111">Die Version des zu verwendenden SDKs.</span><span class="sxs-lookup"><span data-stu-id="b8480-111">The version of the SDK to use.</span></span>

<span data-ttu-id="b8480-112">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b8480-112">For example:</span></span>

```json
{
  "sdk": {
    "version": "1.0.0-preview2-003121"
  }
}
```
