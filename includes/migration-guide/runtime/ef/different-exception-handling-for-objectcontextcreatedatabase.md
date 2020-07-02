---
ms.openlocfilehash: 687118157020ede200f97a0125c4740a06bf4b5e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620303"
---
### <a name="different-exception-handling-for-objectcontextcreatedatabase-and-dbproviderservicescreatedatabase-methods"></a><span data-ttu-id="340cc-101">Unterschiedliche Ausnahmebehandlung für die Methoden „ObjectContext.CreateDatabase“ und „DbProviderServices.CreateDatabase“</span><span class="sxs-lookup"><span data-stu-id="340cc-101">Different exception handling for ObjectContext.CreateDatabase and DbProviderServices.CreateDatabase methods</span></span>

#### <a name="details"></a><span data-ttu-id="340cc-102">Details</span><span class="sxs-lookup"><span data-stu-id="340cc-102">Details</span></span>

<span data-ttu-id="340cc-103">Ab .NET Framework 4.5 versuchen <code>CreateDatabase</code>-Methoden, eine leere Datenbank zu löschen, wenn die Datenbankerstellung fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="340cc-103">Beginning in .NET Framework 4.5, if database creation fails, <code>CreateDatabase</code> methods will attempt to drop the empty database.</span></span> <span data-ttu-id="340cc-104">Wenn dieser Vorgang erfolgreich ist, wird die ursprüngliche <xref:System.Data.SqlClient.SqlException?displayProperty=fullName> weitergegeben (anstelle der <xref:System.InvalidOperationException?displayProperty=fullName>, die in .NET Framework 4.0 immer ausgelöst wurde).</span><span class="sxs-lookup"><span data-stu-id="340cc-104">If that operation succeeds, the original <xref:System.Data.SqlClient.SqlException?displayProperty=fullName> will be propagated (instead of the <xref:System.InvalidOperationException?displayProperty=fullName> that was always thrown in .NET Framework 4.0)</span></span>

#### <a name="suggestion"></a><span data-ttu-id="340cc-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="340cc-105">Suggestion</span></span>

<span data-ttu-id="340cc-106">Beim Abfangen einer <xref:System.InvalidOperationException?displayProperty=fullName>-Ausnahme während der Ausführung von <xref:System.Data.Objects.ObjectContext.CreateDatabase> oder <xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)> sollten SQLExceptions-Ausnahmen nun ebenfalls abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="340cc-106">When catching an <xref:System.InvalidOperationException?displayProperty=fullName> while executing <xref:System.Data.Objects.ObjectContext.CreateDatabase> or <xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)>, SQLExceptions should now also be caught.</span></span>

| <span data-ttu-id="340cc-107">name</span><span class="sxs-lookup"><span data-stu-id="340cc-107">Name</span></span>    | <span data-ttu-id="340cc-108">Wert</span><span class="sxs-lookup"><span data-stu-id="340cc-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="340cc-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="340cc-109">Scope</span></span>   |<span data-ttu-id="340cc-110">Gering</span><span class="sxs-lookup"><span data-stu-id="340cc-110">Minor</span></span>|
|<span data-ttu-id="340cc-111">Version</span><span class="sxs-lookup"><span data-stu-id="340cc-111">Version</span></span>|<span data-ttu-id="340cc-112">4.5</span><span class="sxs-lookup"><span data-stu-id="340cc-112">4.5</span></span>|
|<span data-ttu-id="340cc-113">Typ</span><span class="sxs-lookup"><span data-stu-id="340cc-113">Type</span></span>|<span data-ttu-id="340cc-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="340cc-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="340cc-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="340cc-115">Affected APIs</span></span>

-<xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)?displayProperty=nameWithType></li></ul>|
