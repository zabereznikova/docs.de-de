---
ms.openlocfilehash: 3bb59ba23214f67100d3a78bb689c941b2d187e6
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506965"
---

<span data-ttu-id="36cb2-101">Beim Installieren des .NET-Pakets wird möglicherweise eine Fehlermeldung wie `Failed to fetch ... File has unexpected size ... Mirror sync in progress?` angezeigt.</span><span class="sxs-lookup"><span data-stu-id="36cb2-101">While installing the .NET package, you may see an error similar to `Failed to fetch ... File has unexpected size ... Mirror sync in progress?`.</span></span> <span data-ttu-id="36cb2-102">Diese kann bedeuten, dass der Paketfeed für .NET mit neueren Paketversionen aktualisiert wird und Sie den Vorgang zu einem späteren Zeitpunkt wiederholen sollten.</span><span class="sxs-lookup"><span data-stu-id="36cb2-102">This error could mean that the package feed for .NET is being upgraded with newer package versions, and that you should try again later.</span></span> <span data-ttu-id="36cb2-103">Während eines Upgrades darf der Paketfeed maximal 30 Minuten nicht verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="36cb2-103">During an upgrade, the package feed shouldn't be unavailable for more than 30 minutes.</span></span> <span data-ttu-id="36cb2-104">Wenn dieser Fehler länger als 30 Minuten auftritt, melden Sie ein Issue auf <https://github.com/dotnet/core/issues>.</span><span class="sxs-lookup"><span data-stu-id="36cb2-104">If you continually receive this error for more than 30 minutes, please file an issue at <https://github.com/dotnet/core/issues>.</span></span>
