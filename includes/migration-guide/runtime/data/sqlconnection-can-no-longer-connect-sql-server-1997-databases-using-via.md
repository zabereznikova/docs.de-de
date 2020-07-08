---
ms.openlocfilehash: 241184d61d718fedfea396260e739d2dbc05c305
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620283"
---
### <a name="sqlconnection-can-no-longer-connect-to-sql-server-1997-or-databases-using-the-via-adapter"></a>SqlConnection kann keine Verbindung mit SQL Server 1997 oder Datenbanken herstellen, die den VIA-Adapter verwenden

#### <a name="details"></a>Details

Verbindungen mit SQL Server-Datenbanken unter Verwendung des [Virtual Interface Adapter-Protokolls (VIA)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms191229(v=sql.105)) werden nicht mehr unterstützt. Das Protokoll, das verwendet wird, um eine Verbindung mit der SQL Server-Datenbank herzustellen, wird in der Verbindungszeichenfolge angezeigt. Eine VIA-Verbindung bleibt über &lt;servername&gt; erhalten. Wenn diese App über ein anderes Protokoll als das VIA-Protokoll eine Verbindung mit SQL herstellt (z. B. tcp: oder np:) kommt es nicht zu einem Breaking Change. Außerdem werden Verbindungen mit SQL Server 7 (1997) nicht mehr unterstützt.

#### <a name="suggestion"></a>Vorschlag

Das VIA-Protokoll ist veraltet. Daher sollte ein anderes Protokoll verwendet werden, um eine Verbindung mit SQL-Datenbanken herzustellen. TCP/IP ist das am häufigsten verwendete Protokoll. Weitere Informationen zum Herstellen einer Verbindung über TCP/IP finden Sie unter [Aktivieren des TCP/IP-Protokolls für eine Datenbankinstanz](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bb909712(v=vs.90)). Wenn Sie nur über ein Intranet auf eine Datenbank zugreifen, ist die Leistung des Protokolls für freigegebene Pipes möglicherweise besser, wenn das Netzwerk langsam ist.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String)></li><li><xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String,System.Data.SqlClient.SqlCredential)></li></ul>|
