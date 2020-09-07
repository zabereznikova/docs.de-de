---
ms.openlocfilehash: fb339fb35cdcbba4f1c860fae9c17162c4cff596
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496735"
---
### <a name="sql_variant-data-uses-sql_variant-collation-rather-than-database-collation"></a><span data-ttu-id="e7981-101">Sql_variant-Daten verwenden sql_variant-Sortierreihenfolgen anstatt Datenbanksortierreihenfolgen</span><span class="sxs-lookup"><span data-stu-id="e7981-101">Sql_variant data uses sql_variant collation rather than database collation</span></span>

#### <a name="details"></a><span data-ttu-id="e7981-102">Details</span><span class="sxs-lookup"><span data-stu-id="e7981-102">Details</span></span>

<span data-ttu-id="e7981-103"><code>sql_variant</code>-Daten verwenden <code>sql_variant</code>-Sortierreihenfolgen anstatt Datenbanksortierreihenfolgen.</span><span class="sxs-lookup"><span data-stu-id="e7981-103"><code>sql_variant</code> data uses <code>sql_variant</code> collation rather than database collation.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e7981-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="e7981-104">Suggestion</span></span>

<span data-ttu-id="e7981-105">Diese Änderung behandelt potenzielle Datenbeschädigungen, die verursacht werden, wenn sich die Datenbanksortierreihenfolge von der <code>sql_variant</code>-Sortierreihenfolge unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="e7981-105">This change addresses possible data corruption if the database collation differs from the <code>sql_variant</code> collation.</span></span> <span data-ttu-id="e7981-106">Bei Anwendungen, die auf den beschädigten Daten basieren, treten möglicherweise Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="e7981-106">Applications that rely on the corrupted data may experience failure.</span></span>

| <span data-ttu-id="e7981-107">name</span><span class="sxs-lookup"><span data-stu-id="e7981-107">Name</span></span>    | <span data-ttu-id="e7981-108">Wert</span><span class="sxs-lookup"><span data-stu-id="e7981-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e7981-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="e7981-109">Scope</span></span>   |<span data-ttu-id="e7981-110">Transparent</span><span class="sxs-lookup"><span data-stu-id="e7981-110">Transparent</span></span>|
|<span data-ttu-id="e7981-111">Version</span><span class="sxs-lookup"><span data-stu-id="e7981-111">Version</span></span>|<span data-ttu-id="e7981-112">4.5</span><span class="sxs-lookup"><span data-stu-id="e7981-112">4.5</span></span>|
|<span data-ttu-id="e7981-113">Typ</span><span class="sxs-lookup"><span data-stu-id="e7981-113">Type</span></span>|<span data-ttu-id="e7981-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="e7981-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="e7981-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="e7981-115">Affected APIs</span></span>

<span data-ttu-id="e7981-116">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="e7981-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
