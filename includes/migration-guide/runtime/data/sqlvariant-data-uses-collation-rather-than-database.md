---
ms.openlocfilehash: e7a5a95a5d13f3396d396ad0d74a19a0efa3a967
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235532"
---
### <a name="sqlvariant-data-uses-sqlvariant-collation-rather-than-database-collation"></a><span data-ttu-id="5f063-101">Sql_variant-Daten verwenden sql_variant-Sortierreihenfolgen anstatt Datenbanksortierreihenfolgen</span><span class="sxs-lookup"><span data-stu-id="5f063-101">Sql_variant data uses sql_variant collation rather than database collation</span></span>

|   |   |
|---|---|
|<span data-ttu-id="5f063-102">Details</span><span class="sxs-lookup"><span data-stu-id="5f063-102">Details</span></span>|<code>sql_variant</code> <span data-ttu-id="5f063-103">-Daten verwenden <code>sql_variant</code>-Sortierreihenfolgen anstatt Datenbanksortier-Reihenfolgen.</span><span class="sxs-lookup"><span data-stu-id="5f063-103">data uses <code>sql_variant</code> collation rather than database collation.</span></span>|
|<span data-ttu-id="5f063-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="5f063-104">Suggestion</span></span>|<span data-ttu-id="5f063-105">Diese Änderung behandelt potenzielle Datenbeschädigungen, die verursacht werden, wenn sich die Datenbanksortierreihenfolge von der <code>sql_variant</code>-Sortierreihenfolge unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="5f063-105">This change addresses possible data corruption if the database collation differs from the <code>sql_variant</code> collation.</span></span> <span data-ttu-id="5f063-106">Bei Anwendungen, die auf den beschädigten Daten basieren, treten möglicherweise Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="5f063-106">Applications that rely on the corrupted data may experience failure.</span></span>|
|<span data-ttu-id="5f063-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="5f063-107">Scope</span></span>|<span data-ttu-id="5f063-108">Transparent</span><span class="sxs-lookup"><span data-stu-id="5f063-108">Transparent</span></span>|
|<span data-ttu-id="5f063-109">Version</span><span class="sxs-lookup"><span data-stu-id="5f063-109">Version</span></span>|<span data-ttu-id="5f063-110">4.5</span><span class="sxs-lookup"><span data-stu-id="5f063-110">4.5</span></span>|
|<span data-ttu-id="5f063-111">Typ</span><span class="sxs-lookup"><span data-stu-id="5f063-111">Type</span></span>|<span data-ttu-id="5f063-112">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="5f063-112">Runtime</span></span>|
