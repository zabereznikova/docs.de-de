---
ms.openlocfilehash: 1c9c899d77dd69e185281d98bfec18ce73d80815
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032586"
---
### <a name="kestrel-empty-https-assembly-removed"></a><span data-ttu-id="08aca-101">Kestrel: Leere HTTPS-Assembly wurde entfernt.</span><span class="sxs-lookup"><span data-stu-id="08aca-101">Kestrel: Empty HTTPS assembly removed</span></span>

<span data-ttu-id="08aca-102">Die Assembly <xref:Microsoft.AspNetCore.Server.Kestrel.Https?displayProperty=fullName> wurde entfernt.</span><span class="sxs-lookup"><span data-stu-id="08aca-102">The assembly <xref:Microsoft.AspNetCore.Server.Kestrel.Https?displayProperty=fullName> has been removed.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="08aca-103">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="08aca-103">Version introduced</span></span>

<span data-ttu-id="08aca-104">3.0</span><span class="sxs-lookup"><span data-stu-id="08aca-104">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="08aca-105">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="08aca-105">Reason for change</span></span>

<span data-ttu-id="08aca-106">In ASP.NET Core 2.1 wurde der Inhalt von `Microsoft.AspNetCore.Server.Kestrel.Https` nach <xref:Microsoft.AspNetCore.Server.Kestrel.Core?displayProperty=fullName> verschoben.</span><span class="sxs-lookup"><span data-stu-id="08aca-106">In ASP.NET Core 2.1, the contents of `Microsoft.AspNetCore.Server.Kestrel.Https` were moved to <xref:Microsoft.AspNetCore.Server.Kestrel.Core?displayProperty=fullName>.</span></span> <span data-ttu-id="08aca-107">Diese Änderung wurde ohne Breaking Change mithilfe von `[TypeForwardedTo]`-Attributen durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="08aca-107">This change was done in a non-breaking way using `[TypeForwardedTo]` attributes.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="08aca-108">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="08aca-108">Recommended action</span></span>

- <span data-ttu-id="08aca-109">In Bibliotheken, die auf `Microsoft.AspNetCore.Server.Kestrel.Https` 2.0 verweisen, sollten alle ASP.NET Core-Abhängigkeiten auf 2.1 oder höher aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="08aca-109">Libraries referencing `Microsoft.AspNetCore.Server.Kestrel.Https` 2.0 should update all ASP.NET Core dependencies to 2.1 or later.</span></span> <span data-ttu-id="08aca-110">Andernfalls können sie beim Laden in eine ASP.NET Core 3.0-App unterbrochen werden.</span><span class="sxs-lookup"><span data-stu-id="08aca-110">Otherwise, they may break when loaded into an ASP.NET Core 3.0 app.</span></span>
- <span data-ttu-id="08aca-111">In Apps und Bibliotheken, die auf ASP.NET Core 2.1 und höher abzielen, sollten alle direkten Verweise auf das NuGet-Paket `Microsoft.AspNetCore.Server.Kestrel.Https` entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="08aca-111">Apps and libraries targeting ASP.NET Core 2.1 and later should remove any direct references to the `Microsoft.AspNetCore.Server.Kestrel.Https` NuGet package.</span></span>

#### <a name="category"></a><span data-ttu-id="08aca-112">Kategorie</span><span class="sxs-lookup"><span data-stu-id="08aca-112">Category</span></span>

<span data-ttu-id="08aca-113">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="08aca-113">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="08aca-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="08aca-114">Affected APIs</span></span>

<span data-ttu-id="08aca-115">Keine</span><span class="sxs-lookup"><span data-stu-id="08aca-115">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
