---
title: 'NETSDK1073: FrameworkReference wurde nicht erkannt'
description: Hier erfahren Sie, wie Sie das Problem beheben, wenn FrameworkReference nicht gefunden werden kann.
author: marcpopMSFT
ms.topic: error-reference
ms.date: 10/9/2020
f1_keywords:
- NETSDK1073
ms.openlocfilehash: 2b2dbf2a0d3e13dca4fe634529b7951f2333ce28
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713027"
---
# <a name="netsdk1073-the-frameworkreference-was-not-recognized"></a><span data-ttu-id="58ecb-103">NETSDK1073: FrameworkReference wurde nicht erkannt</span><span class="sxs-lookup"><span data-stu-id="58ecb-103">NETSDK1073: The FrameworkReference was not recognized</span></span>

<span data-ttu-id="58ecb-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.1.100 SDK und höher</span><span class="sxs-lookup"><span data-stu-id="58ecb-104">**This article applies to:** ✔️ .NET Core 2.1.100 SDK and later versions</span></span>

<span data-ttu-id="58ecb-105">Dieser Fehler bedeutet in der Regel, dass es eine bestimmte FrameworkReference-Version gibt, die vom SDK nicht gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="58ecb-105">This error typically means there is a version of a particular FrameworkReference that the SDK cannot find.</span></span> <span data-ttu-id="58ecb-106">Versuchen Sie, die Ordner *obj* und *bin* zu löschen und `dotnet restore` auszuführen, um die aktuellen Zielversionen noch mal herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="58ecb-106">Try deleting your *obj* and *bin* folders and running `dotnet restore` to redownload the latest targeting packs.</span></span>

<span data-ttu-id="58ecb-107">Alternativ könnte es ein Problem mit Ihrer Installation geben. Sorgen Sie also dafür, dass Sie die aktuelle Version von .NET und von Visual Studio verwenden.</span><span class="sxs-lookup"><span data-stu-id="58ecb-107">Alternatively, there could be an issue with your install, so ensure you're on the latest versions of .NET and Visual Studio</span></span>
