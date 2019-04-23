---
ms.openlocfilehash: e7a5a95a5d13f3396d396ad0d74a19a0efa3a967
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235532"
---
### <a name="sqlvariant-data-uses-sqlvariant-collation-rather-than-database-collation"></a>Sql_variant-Daten verwenden sql_variant-Sortierreihenfolgen anstatt Datenbanksortierreihenfolgen

|   |   |
|---|---|
|Details|<code>sql_variant</code> -Daten verwenden <code>sql_variant</code>-Sortierreihenfolgen anstatt Datenbanksortier-Reihenfolgen.|
|Vorschlag|Diese Änderung behandelt potenzielle Datenbeschädigungen, die verursacht werden, wenn sich die Datenbanksortierreihenfolge von der <code>sql_variant</code>-Sortierreihenfolge unterscheidet. Bei Anwendungen, die auf den beschädigten Daten basieren, treten möglicherweise Fehler auf.|
|Bereich|Transparent|
|Version|4.5|
|Typ|Laufzeit|
