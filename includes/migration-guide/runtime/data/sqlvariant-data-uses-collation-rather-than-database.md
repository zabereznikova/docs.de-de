---
ms.openlocfilehash: d606fbc4048421bc572cfe3db2e06bbcd4529e25
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620292"
---
### <a name="sql_variant-data-uses-sql_variant-collation-rather-than-database-collation"></a><span data-ttu-id="c8ea4-101">Sql_variant-Daten verwenden sql_variant-Sortierreihenfolgen anstatt Datenbanksortierreihenfolgen</span><span class="sxs-lookup"><span data-stu-id="c8ea4-101">Sql_variant data uses sql_variant collation rather than database collation</span></span>

#### <a name="details"></a><span data-ttu-id="c8ea4-102">Details</span><span class="sxs-lookup"><span data-stu-id="c8ea4-102">Details</span></span>

<span data-ttu-id="c8ea4-103"><code>sql_variant</code>-Daten verwenden <code>sql_variant</code>-Sortierreihenfolgen anstatt Datenbanksortierreihenfolgen.</span><span class="sxs-lookup"><span data-stu-id="c8ea4-103"><code>sql_variant</code> data uses <code>sql_variant</code> collation rather than database collation.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c8ea4-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="c8ea4-104">Suggestion</span></span>

<span data-ttu-id="c8ea4-105">Diese Änderung behandelt potenzielle Datenbeschädigungen, die verursacht werden, wenn sich die Datenbanksortierreihenfolge von der <code>sql_variant</code>-Sortierreihenfolge unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="c8ea4-105">This change addresses possible data corruption if the database collation differs from the <code>sql_variant</code> collation.</span></span> <span data-ttu-id="c8ea4-106">Bei Anwendungen, die auf den beschädigten Daten basieren, treten möglicherweise Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="c8ea4-106">Applications that rely on the corrupted data may experience failure.</span></span>

| <span data-ttu-id="c8ea4-107">name</span><span class="sxs-lookup"><span data-stu-id="c8ea4-107">Name</span></span>    | <span data-ttu-id="c8ea4-108">Wert</span><span class="sxs-lookup"><span data-stu-id="c8ea4-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c8ea4-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="c8ea4-109">Scope</span></span>   |<span data-ttu-id="c8ea4-110">Transparent</span><span class="sxs-lookup"><span data-stu-id="c8ea4-110">Transparent</span></span>|
|<span data-ttu-id="c8ea4-111">Version</span><span class="sxs-lookup"><span data-stu-id="c8ea4-111">Version</span></span>|<span data-ttu-id="c8ea4-112">4.5</span><span class="sxs-lookup"><span data-stu-id="c8ea4-112">4.5</span></span>|
|<span data-ttu-id="c8ea4-113">Typ</span><span class="sxs-lookup"><span data-stu-id="c8ea4-113">Type</span></span>|<span data-ttu-id="c8ea4-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="c8ea4-114">Runtime</span></span>|
