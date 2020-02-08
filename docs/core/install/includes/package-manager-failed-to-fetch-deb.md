---
ms.openlocfilehash: 98ec28fc1f91512a61f64a36f7749379e864fea1
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920654"
---

<span data-ttu-id="8daac-101">Beim Installieren des .NET Core-Pakets wird möglicherweise ein Fehler wie `Failed to fetch ... File has unexpected size ... Mirror sync in progress?` angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8daac-101">While installing the .NET Core package, you may see an error similar to `Failed to fetch ... File has unexpected size ... Mirror sync in progress?`.</span></span> <span data-ttu-id="8daac-102">Allgemein gesagt, bedeutet dieser Fehler, dass ein Upgrade des Paketfeeds für .NET Core mit neueren Paketversionen durchgeführt wird, und dass Sie den Vorgang zu einem späteren Zeitpunkt wiederholen sollten.</span><span class="sxs-lookup"><span data-stu-id="8daac-102">Generally speaking, this error means that the package feed for .NET Core is being upgraded with newer package versions, and that you should try again later.</span></span> <span data-ttu-id="8daac-103">Während eines Upgrades sollte der Paketfeed maximal 30 Minuten lang nicht verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="8daac-103">During an upgrade, the package feed should not be unavailable for more than 30 minutes.</span></span> <span data-ttu-id="8daac-104">Wenn dieser Fehler länger als 30 Minuten auftritt, melden Sie ein Issue auf <https://github.com/dotnet/core/issues>.</span><span class="sxs-lookup"><span data-stu-id="8daac-104">If you continually receive this error for more than 30 minutes, please file an issue at <https://github.com/dotnet/core/issues>.</span></span>
