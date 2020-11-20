---
ms.openlocfilehash: 8c05af045d2d9666b20f36e36c68cc853f906eae
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506857"
---

<span data-ttu-id="c0d95-101">Beim Installieren des .NET-Pakets wird möglicherweise ein Fehler wie `signature verification failed for file 'repomd.xml' from repository 'packages-microsoft-com-prod'` angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c0d95-101">While installing the .NET package, you may see an error similar to `signature verification failed for file 'repomd.xml' from repository 'packages-microsoft-com-prod'`.</span></span> <span data-ttu-id="c0d95-102">Dieser Fehler bedeutet, dass ein Upgrade des Paketfeeds für .NET mit neueren Paketversionen durchgeführt wird, und dass Sie den Vorgang zu einem späteren Zeitpunkt wiederholen sollten.</span><span class="sxs-lookup"><span data-stu-id="c0d95-102">Generally speaking, this error means that the package feed for .NET is being upgraded with newer package versions, and that you should try again later.</span></span> <span data-ttu-id="c0d95-103">Während eines Upgrades sollte der Paketfeed maximal 2 Stunden lang nicht verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="c0d95-103">During an upgrade, the package feed should not be unavailable for more than 2 hours.</span></span> <span data-ttu-id="c0d95-104">Wenn dieser Fehler länger als 2 Stunden auftritt, melden Sie ein Issue auf <https://github.com/dotnet/core/issues>.</span><span class="sxs-lookup"><span data-stu-id="c0d95-104">If you continually receive this error for more than 2 hours, please file an issue at <https://github.com/dotnet/core/issues>.</span></span>
