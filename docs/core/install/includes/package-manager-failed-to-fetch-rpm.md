---
ms.openlocfilehash: 96f3ef0160144322f77413995c842b745bb5bb1e
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920736"
---

<span data-ttu-id="39eca-101">Beim Installieren des .NET Core-Pakets wird möglicherweise ein Fehler wie `signature verification failed for file 'repomd.xml' from repository 'packages-microsoft-com-prod'` angezeigt.</span><span class="sxs-lookup"><span data-stu-id="39eca-101">While installing the .NET Core package, you may see an error similar to `signature verification failed for file 'repomd.xml' from repository 'packages-microsoft-com-prod'`.</span></span> <span data-ttu-id="39eca-102">Allgemein gesagt, bedeutet dieser Fehler, dass ein Upgrade des Paketfeeds für .NET Core mit neueren Paketversionen durchgeführt wird, und dass Sie den Vorgang zu einem späteren Zeitpunkt wiederholen sollten.</span><span class="sxs-lookup"><span data-stu-id="39eca-102">Generally speaking, this error means that the package feed for .NET Core is being upgraded with newer package versions, and that you should try again later.</span></span> <span data-ttu-id="39eca-103">Während eines Upgrades sollte der Paketfeed maximal 2 Stunden lang nicht verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="39eca-103">During an upgrade, the package feed should not be unavailable for more than 2 hours.</span></span> <span data-ttu-id="39eca-104">Wenn dieser Fehler länger als 2 Stunden auftritt, melden Sie ein Issue auf <https://github.com/dotnet/core/issues>.</span><span class="sxs-lookup"><span data-stu-id="39eca-104">If you continually receive this error for more than 2 hours, please file an issue at <https://github.com/dotnet/core/issues>.</span></span>
