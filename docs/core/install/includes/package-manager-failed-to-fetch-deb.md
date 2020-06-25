---
ms.openlocfilehash: 15418d1ac3ade6a0fa35ca61a02134e20af1baea
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602741"
---

<span data-ttu-id="783e2-101">Beim Installieren des .NET Core-Pakets wird möglicherweise ein Fehler wie `Failed to fetch ... File has unexpected size ... Mirror sync in progress?` angezeigt.</span><span class="sxs-lookup"><span data-stu-id="783e2-101">While installing the .NET Core package, you may see an error similar to `Failed to fetch ... File has unexpected size ... Mirror sync in progress?`.</span></span> <span data-ttu-id="783e2-102">Dieser Fehler kann bedeuten, dass ein Upgrade des Paketfeeds für .NET Core mit neueren Paketversionen durchgeführt wird und Sie den Vorgang zu einem späteren Zeitpunkt wiederholen sollten.</span><span class="sxs-lookup"><span data-stu-id="783e2-102">This error could mean that the package feed for .NET Core is being upgraded with newer package versions, and that you should try again later.</span></span> <span data-ttu-id="783e2-103">Während eines Upgrades darf der Paketfeed maximal 30 Minuten nicht verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="783e2-103">During an upgrade, the package feed shouldn't be unavailable for more than 30 minutes.</span></span> <span data-ttu-id="783e2-104">Wenn dieser Fehler länger als 30 Minuten auftritt, melden Sie ein Issue auf <https://github.com/dotnet/core/issues>.</span><span class="sxs-lookup"><span data-stu-id="783e2-104">If you continually receive this error for more than 30 minutes, please file an issue at <https://github.com/dotnet/core/issues>.</span></span>
