---
ms.openlocfilehash: 768a948849064cedb38110f5ed271717442325c0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620313"
---
### <a name="log-file-name-created-by-the-objectcontextcreatedatabase-method-has-changed-to-match-sql-server-specifications"></a>Der von der ObjectContext.CreateDatabase-Methode erstellte Protokolldateiname wurde geändert, um den SQL Server-Spezifikationen zu entsprechen

#### <a name="details"></a>Details

Wenn die <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=fullName>-Methode entweder direkt oder durch Code First mit dem SqlClient-Anbieter und einem AttachDBFilename-Wert in der Verbindungszeichenfolge aufgerufen wird, erstellt sie eine Protokolldatei namens „Dateiname_log.ldf“ anstelle von „Dateiname.ldf“ (wobei „Dateiname“ der vom AttachDBFilename-Wert angegebene Name der Datei ist). Diese Änderung verbessert das Debuggen, indem eine Protokolldatei bereitgestellt wird, die nach den SQL Server-Spezifikationen benannt wird.

#### <a name="suggestion"></a>Vorschlag

Wenn der Name der Protokolldatei für eine App wichtig ist, sollte die App aktualisiert werden, um das standardmäßige Dateinamenformat „_log.ldf“ zu erwarten.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=nameWithType></li></ul>|
