---
ms.openlocfilehash: d606fbc4048421bc572cfe3db2e06bbcd4529e25
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620292"
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
