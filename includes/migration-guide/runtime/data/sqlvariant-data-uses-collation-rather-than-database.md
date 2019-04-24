---
ms.openlocfilehash: e7a5a95a5d13f3396d396ad0d74a19a0efa3a967
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59235532"
---
### <a name="sqlvariant-data-uses-sqlvariant-collation-rather-than-database-collation"></a><span data-ttu-id="e576c-101">Sql_variant-Daten verwenden sql_variant-Sortierreihenfolgen anstatt Datenbanksortierreihenfolgen</span><span class="sxs-lookup"><span data-stu-id="e576c-101">Sql_variant data uses sql_variant collation rather than database collation</span></span>

|   |   |
|---|---|
|<span data-ttu-id="e576c-102">Details</span><span class="sxs-lookup"><span data-stu-id="e576c-102">Details</span></span>|<span data-ttu-id="e576c-103"><code>sql_variant</code>-Daten verwenden <code>sql_variant</code>-Sortierreihenfolgen anstatt Datenbanksortierreihenfolgen.</span><span class="sxs-lookup"><span data-stu-id="e576c-103"><code>sql_variant</code> data uses <code>sql_variant</code> collation rather than database collation.</span></span>|
|<span data-ttu-id="e576c-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="e576c-104">Suggestion</span></span>|<span data-ttu-id="e576c-105">Diese Änderung behandelt potenzielle Datenbeschädigungen, die verursacht werden, wenn sich die Datenbanksortierreihenfolge von der <code>sql_variant</code>-Sortierreihenfolge unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="e576c-105">This change addresses possible data corruption if the database collation differs from the <code>sql_variant</code> collation.</span></span> <span data-ttu-id="e576c-106">Bei Anwendungen, die auf den beschädigten Daten basieren, treten möglicherweise Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="e576c-106">Applications that rely on the corrupted data may experience failure.</span></span>|
|<span data-ttu-id="e576c-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="e576c-107">Scope</span></span>|<span data-ttu-id="e576c-108">Transparent</span><span class="sxs-lookup"><span data-stu-id="e576c-108">Transparent</span></span>|
|<span data-ttu-id="e576c-109">Version</span><span class="sxs-lookup"><span data-stu-id="e576c-109">Version</span></span>|<span data-ttu-id="e576c-110">4.5</span><span class="sxs-lookup"><span data-stu-id="e576c-110">4.5</span></span>|
|<span data-ttu-id="e576c-111">Typ</span><span class="sxs-lookup"><span data-stu-id="e576c-111">Type</span></span>|<span data-ttu-id="e576c-112">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="e576c-112">Runtime</span></span>|
