---
ms.openlocfilehash: b893966ceb65246ed6a7d214011b17ca14c50d5a
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85802849"
---

> [!WARNING]
> Übergeben Sie ein Timeout, wenn Sie <xref:System.Text.RegularExpressions> zum Verarbeiten nicht vertrauenswürdiger Eingaben verwenden. Ein böswilliger Benutzer kann Eingaben für `RegularExpressions` angeben, um einen [Denial-of-Service-Angriff](https://www.us-cert.gov/ncas/tips/ST04-015) durchzuführen. ASP.NET Core-Framework-APIs, die `RegularExpressions` verwenden, übergeben ein Timeout.
