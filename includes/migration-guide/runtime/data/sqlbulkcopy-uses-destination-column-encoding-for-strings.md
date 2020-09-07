---
ms.openlocfilehash: fd9f4f3de8f7be39242d4ff6924d480f20a1a06b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496445"
---
### <a name="sqlbulkcopy-uses-destination-column-encoding-for-strings"></a>„SqlBulkCopy“ verwendet die Codierung der Zielspalte für Zeichenfolgen

#### <a name="details"></a>Details

Beim Einfügen von Daten in eine Spalte verwendet <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=fullName> die Codierung der Zielspalte, und nicht die Standardcodierung für <code>VARCHAR</code>- und <code>CHAR</code>-Typen. Diese Änderung schließt die Gefahr einer möglichen Datenbeschädigung aus, die bei Verwenden der Standardcodierung verursacht wird, wenn diese nicht von der Zielspalte verwendet wird. In seltenen Fällen kann eine vorhandene Anwendung eine SqlException-Ausnahme auslösen, wenn die Änderung der Codierung Daten erzeugt, die zu groß für die Zielspalte sind.

#### <a name="suggestion"></a>Vorschlag

Gehen Sie davon aus, dass <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=fullName> keine Daten mehr aufgrund von Codierungsunterschieden beschädigt. Wenn Zeichenfolgen kopiert werden, die fast das Größenlimit der Zielspalte erreicht haben, kann es erforderlich sein, die Daten (die kopiert werden sollen, um zu überprüfen, dass die Daten in die Zielspalte passen) vorab zu codieren oder <xref:System.Data.SqlClient.SqlException?displayProperty=fullName>-Ausnahmen abzufangen.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=nameWithType>
- <xref:System.Data.SqlClient.SqlBulkCopy.%23ctor(System.Data.SqlClient.SqlConnection)>

<!--

#### Affected APIs

- `T:System.Data.SqlClient.SqlBulkCopy`
- `M:System.Data.SqlClient.SqlBulkCopy.#ctor(System.Data.SqlClient.SqlConnection)`

-->
