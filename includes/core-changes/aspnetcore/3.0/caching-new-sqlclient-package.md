---
ms.openlocfilehash: 771238c53dc97f4cf4068968f3c68500ba9f87da
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032483"
---
### <a name="caching-microsoftextensionscachingsqlserver-uses-new-sqlclient-package"></a><span data-ttu-id="cb1ca-101">Zwischenspeicherung: Microsoft.Extensions.Caching.SqlServer verwendet neues Paket SqlClient.</span><span class="sxs-lookup"><span data-stu-id="cb1ca-101">Caching: Microsoft.Extensions.Caching.SqlServer uses new SqlClient package</span></span>

<span data-ttu-id="cb1ca-102">Das Paket `Microsoft.Extensions.Caching.SqlServer` verwendet anstelle des Pakets `System.Data.SqlClient` das neue Paket `Microsoft.Data.SqlClient`.</span><span class="sxs-lookup"><span data-stu-id="cb1ca-102">The `Microsoft.Extensions.Caching.SqlServer` package will use the new `Microsoft.Data.SqlClient` package instead of `System.Data.SqlClient` package.</span></span> <span data-ttu-id="cb1ca-103">Diese Änderung kann zu geringfügigen Breaking Changes beim Verhalten führen.</span><span class="sxs-lookup"><span data-stu-id="cb1ca-103">This change could cause slight behavioral breaking changes.</span></span> <span data-ttu-id="cb1ca-104">Weitere Informationen finden Sie unter [Introducing the new Microsoft.Data.SqlClient](https://devblogs.microsoft.com/dotnet/introducing-the-new-microsoftdatasqlclient/) (Vorstellung des neuen Microsoft.Data.SqlClient).</span><span class="sxs-lookup"><span data-stu-id="cb1ca-104">For more information, see [Introducing the new Microsoft.Data.SqlClient](https://devblogs.microsoft.com/dotnet/introducing-the-new-microsoftdatasqlclient/).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="cb1ca-105">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="cb1ca-105">Version introduced</span></span>

<span data-ttu-id="cb1ca-106">3.0</span><span class="sxs-lookup"><span data-stu-id="cb1ca-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="cb1ca-107">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="cb1ca-107">Old behavior</span></span>

<span data-ttu-id="cb1ca-108">Das Paket `Microsoft.Extensions.Caching.SqlServer` hat das Paket `System.Data.SqlClient` verwendet.</span><span class="sxs-lookup"><span data-stu-id="cb1ca-108">The `Microsoft.Extensions.Caching.SqlServer` package used the `System.Data.SqlClient` package.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="cb1ca-109">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="cb1ca-109">New behavior</span></span>

<span data-ttu-id="cb1ca-110">`Microsoft.Extensions.Caching.SqlServer` verwendet jetzt das Paket `Microsoft.Data.SqlClient`.</span><span class="sxs-lookup"><span data-stu-id="cb1ca-110">`Microsoft.Extensions.Caching.SqlServer` is now using the `Microsoft.Data.SqlClient` package.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="cb1ca-111">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="cb1ca-111">Reason for change</span></span>

<span data-ttu-id="cb1ca-112">`Microsoft.Data.SqlClient` ist ein neues Paket, das aus `System.Data.SqlClient` erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="cb1ca-112">`Microsoft.Data.SqlClient` is a new package that is built off of `System.Data.SqlClient`.</span></span> <span data-ttu-id="cb1ca-113">Es enthält ab sofort alle neuen Funktionen.</span><span class="sxs-lookup"><span data-stu-id="cb1ca-113">It's where all new feature work will be done from now on.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="cb1ca-114">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="cb1ca-114">Recommended action</span></span>

<span data-ttu-id="cb1ca-115">Kunden müssen sich um diesen Breaking Change nur kümmern, wenn sie die vom Paket `Microsoft.Extensions.Caching.SqlServer` zurückgegebenen Typen verwendet und in `System.Data.SqlClient`-Typen umgewandelt haben.</span><span class="sxs-lookup"><span data-stu-id="cb1ca-115">Customers shouldn't need to worry about this breaking change unless they were using types returned by the `Microsoft.Extensions.Caching.SqlServer` package and casting them to `System.Data.SqlClient` types.</span></span> <span data-ttu-id="cb1ca-116">Wenn z. B. eine `DbConnection` in den [alten SqlConnection-Typ](xref:System.Data.SqlClient.SqlConnection) umgewandelt wurde, muss die Umwandlung in den neuen `Microsoft.Data.SqlClient.SqlConnection`-Typ geändert werden.</span><span class="sxs-lookup"><span data-stu-id="cb1ca-116">For example, if someone was casting a `DbConnection` to the [old SqlConnection type](xref:System.Data.SqlClient.SqlConnection), they would need to change the cast to the new `Microsoft.Data.SqlClient.SqlConnection` type.</span></span>

#### <a name="category"></a><span data-ttu-id="cb1ca-117">Kategorie</span><span class="sxs-lookup"><span data-stu-id="cb1ca-117">Category</span></span>

<span data-ttu-id="cb1ca-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="cb1ca-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="cb1ca-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="cb1ca-119">Affected APIs</span></span>

<span data-ttu-id="cb1ca-120">Keine</span><span class="sxs-lookup"><span data-stu-id="cb1ca-120">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
