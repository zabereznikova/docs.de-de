---
ms.openlocfilehash: 8c593fa6490451c6236f0d4390f09d4e9e4f0cbb
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496523"
---
### <a name="different-exception-handling-for-objectcontextcreatedatabase-and-dbproviderservicescreatedatabase-methods"></a><span data-ttu-id="fee08-101">Unterschiedliche Ausnahmebehandlung für die Methoden „ObjectContext.CreateDatabase“ und „DbProviderServices.CreateDatabase“</span><span class="sxs-lookup"><span data-stu-id="fee08-101">Different exception handling for ObjectContext.CreateDatabase and DbProviderServices.CreateDatabase methods</span></span>

#### <a name="details"></a><span data-ttu-id="fee08-102">Details</span><span class="sxs-lookup"><span data-stu-id="fee08-102">Details</span></span>

<span data-ttu-id="fee08-103">Ab .NET Framework 4.5 versuchen <code>CreateDatabase</code>-Methoden, eine leere Datenbank zu löschen, wenn die Datenbankerstellung fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="fee08-103">Beginning in .NET Framework 4.5, if database creation fails, <code>CreateDatabase</code> methods will attempt to drop the empty database.</span></span> <span data-ttu-id="fee08-104">Wenn dieser Vorgang erfolgreich ist, wird die ursprüngliche <xref:System.Data.SqlClient.SqlException?displayProperty=fullName> weitergegeben (anstelle der <xref:System.InvalidOperationException?displayProperty=fullName>, die in .NET Framework 4.0 immer ausgelöst wurde).</span><span class="sxs-lookup"><span data-stu-id="fee08-104">If that operation succeeds, the original <xref:System.Data.SqlClient.SqlException?displayProperty=fullName> will be propagated (instead of the <xref:System.InvalidOperationException?displayProperty=fullName> that was always thrown in .NET Framework 4.0)</span></span>

#### <a name="suggestion"></a><span data-ttu-id="fee08-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="fee08-105">Suggestion</span></span>

<span data-ttu-id="fee08-106">Beim Abfangen einer <xref:System.InvalidOperationException?displayProperty=fullName>-Ausnahme während der Ausführung von <xref:System.Data.Objects.ObjectContext.CreateDatabase> oder <xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)> sollten SQLExceptions-Ausnahmen nun ebenfalls abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="fee08-106">When catching an <xref:System.InvalidOperationException?displayProperty=fullName> while executing <xref:System.Data.Objects.ObjectContext.CreateDatabase> or <xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)>, SQLExceptions should now also be caught.</span></span>

| <span data-ttu-id="fee08-107">name</span><span class="sxs-lookup"><span data-stu-id="fee08-107">Name</span></span>    | <span data-ttu-id="fee08-108">Wert</span><span class="sxs-lookup"><span data-stu-id="fee08-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="fee08-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="fee08-109">Scope</span></span>   |<span data-ttu-id="fee08-110">Gering</span><span class="sxs-lookup"><span data-stu-id="fee08-110">Minor</span></span>|
|<span data-ttu-id="fee08-111">Version</span><span class="sxs-lookup"><span data-stu-id="fee08-111">Version</span></span>|<span data-ttu-id="fee08-112">4.5</span><span class="sxs-lookup"><span data-stu-id="fee08-112">4.5</span></span>|
|<span data-ttu-id="fee08-113">Typ</span><span class="sxs-lookup"><span data-stu-id="fee08-113">Type</span></span>|<span data-ttu-id="fee08-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="fee08-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="fee08-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="fee08-115">Affected APIs</span></span>

- <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=nameWithType>
- <xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Data.Objects.ObjectContext.CreateDatabase`
- `M:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)`

-->
