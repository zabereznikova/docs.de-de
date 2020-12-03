---
title: 'NETSDK1059: Projekt enthält veraltetes CLI-Tool für .NET'
description: Hier erfahren Sie, wie Sie das Problem beheben, wenn ein Projekt ein veraltetes CLI-Tool für .NET enthält.
author: sfoslund
ms.topic: error-reference
ms.date: 10/09/2020
f1_keywords:
- NETSDK1059
ms.openlocfilehash: b80f42495e1aff8d37008946f10f68c195d5a9ec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713118"
---
# <a name="netsdk1059-project-contains-obsolete-net-cli-tool"></a><span data-ttu-id="db55e-103">NETSDK1059: Projekt enthält veraltetes CLI-Tool für .NET</span><span class="sxs-lookup"><span data-stu-id="db55e-103">NETSDK1059: Project contains obsolete .NET CLI tool</span></span>

<span data-ttu-id="db55e-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.1.100 SDK und höher</span><span class="sxs-lookup"><span data-stu-id="db55e-104">**This article applies to:** ✔️ .NET Core 2.1.100 SDK and later versions</span></span>

<span data-ttu-id="db55e-105">Wenn das .NET SDK die Warnung NETSDK1059 ausgibt, enthält Ihr Projekt ein veraltetes CLI-Tool für .NET.</span><span class="sxs-lookup"><span data-stu-id="db55e-105">When the .NET SDK issues warning NETSDK1059, your project contains an obsolete .NET CLI tool.</span></span> <span data-ttu-id="db55e-106">Seit .NET Core 2.1 sind diese Tools im .NET SDK enthalten, und im Projekt muss nicht explizit darauf verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="db55e-106">As of .NET Core 2.1, these tools are included in the .NET SDK and do not need to be explicitly referenced by the project.</span></span> <span data-ttu-id="db55e-107">Weitere Informationen zur Migration zu .NET Core 2.1 finden Sie [hier](https://aka.ms/dotnetclitools-in-box).</span><span class="sxs-lookup"><span data-stu-id="db55e-107">More information for migrating to .NET Core 2.1 can be found [here](https://aka.ms/dotnetclitools-in-box).</span></span>
