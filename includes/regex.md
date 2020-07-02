---
ms.openlocfilehash: b893966ceb65246ed6a7d214011b17ca14c50d5a
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85802849"
---

> [!WARNING]
> <span data-ttu-id="210dd-101">Übergeben Sie ein Timeout, wenn Sie <xref:System.Text.RegularExpressions> zum Verarbeiten nicht vertrauenswürdiger Eingaben verwenden.</span><span class="sxs-lookup"><span data-stu-id="210dd-101">When using <xref:System.Text.RegularExpressions> to process untrusted input, pass a timeout.</span></span> <span data-ttu-id="210dd-102">Ein böswilliger Benutzer kann Eingaben für `RegularExpressions` angeben, um einen [Denial-of-Service-Angriff](https://www.us-cert.gov/ncas/tips/ST04-015) durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="210dd-102">A malicious user can provide input to `RegularExpressions` causing a [Denial-of-Service attack](https://www.us-cert.gov/ncas/tips/ST04-015).</span></span> <span data-ttu-id="210dd-103">ASP.NET Core-Framework-APIs, die `RegularExpressions` verwenden, übergeben ein Timeout.</span><span class="sxs-lookup"><span data-stu-id="210dd-103">ASP.NET Core framework APIs that use `RegularExpressions` pass a timeout.</span></span>
