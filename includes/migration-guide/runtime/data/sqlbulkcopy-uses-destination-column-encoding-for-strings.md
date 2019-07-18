---
ms.openlocfilehash: fa09831ac47a59535ff73c8c8680c2642c3248c9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235520"
---
### <a name="sqlbulkcopy-uses-destination-column-encoding-for-strings"></a>„SqlBulkCopy“ verwendet die Codierung der Zielspalte für Zeichenfolgen

|   |   |
|---|---|
|Details|Beim Einfügen von Daten in eine Spalte verwendet <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=name> die Codierung der Zielspalte, und nicht die Standardcodierung für <code>VARCHAR</code>- und <code>CHAR</code>-Typen. Diese Änderung schließt die Gefahr einer möglichen Datenbeschädigung aus, die bei Verwenden der Standardcodierung verursacht wird, wenn diese nicht von der Zielspalte verwendet wird. In seltenen Fällen kann eine vorhandene Anwendung eine SqlException-Ausnahme auslösen, wenn die Änderung der Codierung Daten erzeugt, die zu groß für die Zielspalte sind.|
|Vorschlag|Gehen Sie davon aus, dass <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=name> keine Daten mehr aufgrund von Codierungsunterschieden beschädigt. Wenn Zeichenfolgen kopiert werden, die fast das Größenlimit der Zielspalte erreicht haben, kann es erforderlich sein, die Daten (die kopiert werden sollen, um zu überprüfen, dass die Daten in die Zielspalte passen) vorab zu codieren oder <xref:System.Data.SqlClient.SqlException?displayProperty=name>-Ausnahmen abzufangen.|
|Bereich|Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlBulkCopy.%23ctor(System.Data.SqlClient.SqlConnection)?displayProperty=nameWithType></li></ul>|
