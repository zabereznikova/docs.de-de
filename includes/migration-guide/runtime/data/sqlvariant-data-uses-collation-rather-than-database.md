---
ms.openlocfilehash: e7a5a95a5d13f3396d396ad0d74a19a0efa3a967
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59235532"
---
### <a name="sqlvariant-data-uses-sqlvariant-collation-rather-than-database-collation"></a>Sql_variant-Daten verwenden sql_variant-Sortierreihenfolgen anstatt Datenbanksortierreihenfolgen

|   |   |
|---|---|
|Details|<code>sql_variant</code>-Daten verwenden <code>sql_variant</code>-Sortierreihenfolgen anstatt Datenbanksortierreihenfolgen.|
|Vorschlag|Diese Änderung behandelt potenzielle Datenbeschädigungen, die verursacht werden, wenn sich die Datenbanksortierreihenfolge von der <code>sql_variant</code>-Sortierreihenfolge unterscheidet. Bei Anwendungen, die auf den beschädigten Daten basieren, treten möglicherweise Fehler auf.|
|Bereich|Transparent|
|Version|4.5|
|Typ|Laufzeit|
