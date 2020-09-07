---
ms.openlocfilehash: fb339fb35cdcbba4f1c860fae9c17162c4cff596
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496735"
---
### <a name="sql_variant-data-uses-sql_variant-collation-rather-than-database-collation"></a>Sql_variant-Daten verwenden sql_variant-Sortierreihenfolgen anstatt Datenbanksortierreihenfolgen

#### <a name="details"></a>Details

<code>sql_variant</code>-Daten verwenden <code>sql_variant</code>-Sortierreihenfolgen anstatt Datenbanksortierreihenfolgen.

#### <a name="suggestion"></a>Vorschlag

Diese Änderung behandelt potenzielle Datenbeschädigungen, die verursacht werden, wenn sich die Datenbanksortierreihenfolge von der <code>sql_variant</code>-Sortierreihenfolge unterscheidet. Bei Anwendungen, die auf den beschädigten Daten basieren, treten möglicherweise Fehler auf.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Transparent|
|Version|4.5|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
