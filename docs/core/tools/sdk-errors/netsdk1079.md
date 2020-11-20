---
title: 'NETSDK1079: Das Paket „Microsoft.AspNetCore.All“ wird nicht unterstützt, wenn .NET Core 3.0 oder höher als Zielversion verwendet wird.'
description: Auflösen der Migration von Microsoft.AspNetCore.App
author: dsplaisted
ms.topic: error-reference
ms.date: 10/09/2020
f1_keywords:
- NETSDK1079
ms.openlocfilehash: e0b7aba909dbd2931f755238a2de2418d294751d
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94445677"
---
# <a name="netsdk1079-the-microsoftaspnetcoreall-package-is-not-supported-when-targeting-net-core-30-or-higher"></a><span data-ttu-id="79149-103">NETSDK1079: Das Paket „Microsoft.AspNetCore.All“ wird nicht unterstützt, wenn .NET Core 3.0 oder höher als Zielversion verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="79149-103">NETSDK1079: The Microsoft.AspNetCore.All package is not supported when targeting .NET Core 3.0 or higher.</span></span>

<span data-ttu-id="79149-104">**Dieser Artikel gilt für:** ✔️ .NET Core SDK 3.1.100 und höher</span><span class="sxs-lookup"><span data-stu-id="79149-104">**This article applies to:** ✔️ .NET Core SDK 3.1.100 and later versions</span></span>

<span data-ttu-id="79149-105">Diese Fehlermeldung wird möglicherweise angezeigt, wenn:</span><span class="sxs-lookup"><span data-stu-id="79149-105">You may receive this error message when:</span></span>

- <span data-ttu-id="79149-106">Sie ein ASP.NET Core-Projekt von .NET Core 2.2 oder früher auf .NET Core 3.0 oder höher neu zuweisen.</span><span class="sxs-lookup"><span data-stu-id="79149-106">You retarget an ASP.NET Core project from .NET Core 2.2 or earlier to .NET Core 3.0 or later.</span></span>
- <span data-ttu-id="79149-107">das Projekt das Paket „Microsoft.AspNetCore.All“ verwendet.</span><span class="sxs-lookup"><span data-stu-id="79149-107">The project uses the Microsoft.AspNetCore.All package.</span></span>

<span data-ttu-id="79149-108">Entfernen Sie `PackageReference` für Microsoft.AspNetCore.All.</span><span class="sxs-lookup"><span data-stu-id="79149-108">Remove the `PackageReference` for Microsoft.AspNetCore.All.</span></span>  <span data-ttu-id="79149-109">Möglicherweise müssen Sie auch Paketverweise für Pakete hinzufügen, auf die von Microsoft.AspNetCore.All verwiesen wird, die aber nicht im freigegebenen ASP.NET Core-Framework enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="79149-109">You may also need to add package references for packages that were referenced from Microsoft.AspNetCore.All but are not included in the ASP.NET Core shared framework.</span></span>  <span data-ttu-id="79149-110">Diese Pakete sind hier aufgeführt: [Migrieren von Microsoft.AspNetCore.All zu Microsoft.AspNetCore.App](/aspnet/core/fundamentals/metapackage#migrating-from-microsoftaspnetcoreall-to-microsoftaspnetcoreapp)</span><span class="sxs-lookup"><span data-stu-id="79149-110">These packages are listed here: [Migrating from Microsoft.AspNetCore.All to Microsoft.AspNetCore.App](/aspnet/core/fundamentals/metapackage#migrating-from-microsoftaspnetcoreall-to-microsoftaspnetcoreapp).</span></span>

<span data-ttu-id="79149-111">Weitere Informationen finden Sie unter [Migrieren von ASP.NET Core 2.2 zu 3.0](/aspnet/core/migration/22-to-30).</span><span class="sxs-lookup"><span data-stu-id="79149-111">See also [Migrate from ASP.NET Core 2.2 to 3.0](/aspnet/core/migration/22-to-30)</span></span>
