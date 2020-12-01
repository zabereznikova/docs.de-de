---
ms.openlocfilehash: 31e7f84a787d255a474f4c2b1fa3068903dbed52
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032533"
---
### <a name="http-headernames-constants-changed-to-static-readonly"></a><span data-ttu-id="542c9-101">HTTP: HeaderNames-Konstanten wurden in „static readonly“ geändert.</span><span class="sxs-lookup"><span data-stu-id="542c9-101">HTTP: HeaderNames constants changed to static readonly</span></span>

<span data-ttu-id="542c9-102">Ab ASP.NET Core 3.0 Preview 5 wurden die Felder in <xref:Microsoft.Net.Http.Headers.HeaderNames?displayProperty=fullName> von `const` in `static readonly` geändert.</span><span class="sxs-lookup"><span data-stu-id="542c9-102">Starting in ASP.NET Core 3.0 Preview 5, the fields in <xref:Microsoft.Net.Http.Headers.HeaderNames?displayProperty=fullName> changed from `const` to `static readonly`.</span></span>

<span data-ttu-id="542c9-103">Weitere Informationen finden Sie unter [dotnet/aspnetcore#9514](https://github.com/dotnet/aspnetcore/issues/9514).</span><span class="sxs-lookup"><span data-stu-id="542c9-103">For discussion, see [dotnet/aspnetcore#9514](https://github.com/dotnet/aspnetcore/issues/9514).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="542c9-104">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="542c9-104">Version introduced</span></span>

<span data-ttu-id="542c9-105">3.0</span><span class="sxs-lookup"><span data-stu-id="542c9-105">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="542c9-106">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="542c9-106">Old behavior</span></span>

<span data-ttu-id="542c9-107">Diese Felder waren `const`.</span><span class="sxs-lookup"><span data-stu-id="542c9-107">These fields used to be `const`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="542c9-108">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="542c9-108">New behavior</span></span>

<span data-ttu-id="542c9-109">Diese Felder sind nun `static readonly`.</span><span class="sxs-lookup"><span data-stu-id="542c9-109">These fields are now `static readonly`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="542c9-110">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="542c9-110">Reason for change</span></span>

<span data-ttu-id="542c9-111">Die Änderung hat folgende Gründe:</span><span class="sxs-lookup"><span data-stu-id="542c9-111">The change:</span></span>

* <span data-ttu-id="542c9-112">Sie verhindert, dass die Werte über Assemblygrenzen hinweg eingebettet werden, sodass bei Bedarf Korrekturen an Werten möglich sind.</span><span class="sxs-lookup"><span data-stu-id="542c9-112">Prevents the values from being embedded across assembly boundaries, allowing for value corrections as needed.</span></span>
* <span data-ttu-id="542c9-113">Sie ermöglicht schnellere Überprüfungen der Verweisgleichheit.</span><span class="sxs-lookup"><span data-stu-id="542c9-113">Enables faster reference equality checks.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="542c9-114">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="542c9-114">Recommended action</span></span>

<span data-ttu-id="542c9-115">Kompilieren Sie mit 3.0 neu.</span><span class="sxs-lookup"><span data-stu-id="542c9-115">Recompile against 3.0.</span></span> <span data-ttu-id="542c9-116">Sie müssen Quellcode ändern, der diese Felder auf folgende Weise verwendet:</span><span class="sxs-lookup"><span data-stu-id="542c9-116">Source code using these fields in the following ways can no longer do so:</span></span>

* <span data-ttu-id="542c9-117">Als unzulässiges Attributargument</span><span class="sxs-lookup"><span data-stu-id="542c9-117">As an attribute argument</span></span>
* <span data-ttu-id="542c9-118">Als einen `case` in einer `switch`-Anweisung</span><span class="sxs-lookup"><span data-stu-id="542c9-118">As a `case` in a `switch` statement</span></span>
* <span data-ttu-id="542c9-119">Beim Definieren einer anderen `const`</span><span class="sxs-lookup"><span data-stu-id="542c9-119">When defining another `const`</span></span>

<span data-ttu-id="542c9-120">Um diesen Breaking Change zu umgehen, verwenden Sie selbst definierte Headernamenkonstanten oder Zeichenfolgenliterale.</span><span class="sxs-lookup"><span data-stu-id="542c9-120">To work around the breaking change, switch to using self-defined header name constants or string literals.</span></span>

#### <a name="category"></a><span data-ttu-id="542c9-121">Kategorie</span><span class="sxs-lookup"><span data-stu-id="542c9-121">Category</span></span>

<span data-ttu-id="542c9-122">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="542c9-122">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="542c9-123">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="542c9-123">Affected APIs</span></span>

<xref:Microsoft.Net.Http.Headers.HeaderNames?displayProperty=fullName>

<!-- 

#### Affected APIs

`T:Microsoft.Net.Http.Headers.HeaderNames`

-->
