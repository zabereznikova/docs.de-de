---
ms.openlocfilehash: fcaee245e98dfe71beb4042a2664a14b64cf2398
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804041"
---
### <a name="sqlconnection-can-no-longer-connect-to-sql-server-1997-or-databases-using-the-via-adapter"></a>SqlConnection kann keine Verbindung mit SQL Server 1997 oder Datenbanken herstellen, die den VIA-Adapter verwenden

|   |   |
|---|---|
|Details|Verbindungen mit SQL Server-Datenbanken unter Verwendung des [Virtual Interface Adapter-Protokolls (VIA)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms191229%28v=sql.105%29) werden nicht mehr unterstützt. Das Protokoll, das verwendet wird, um eine Verbindung mit der SQL Server-Datenbank herzustellen, wird in der Verbindungszeichenfolge angezeigt. Eine VIA-Verbindung bleibt über &lt;servername&gt; erhalten. Wenn diese App über ein anderes Protokoll als das VIA-Protokoll eine Verbindung mit SQL herstellt (z.B. tcp: oder np:) kommt es nicht zu einem Breaking Change. Außerdem werden Verbindungen mit SQL Server 7 (1997) nicht mehr unterstützt.|
|Vorschlag|Das VIA-Protokoll ist veraltet. Daher sollte ein anderes Protokoll verwendet werden, um eine Verbindung mit SQL-Datenbanken herzustellen. TCP/IP ist das am häufigsten verwendete Protokoll. Weitere Informationen zum Herstellen einer Verbindung über TCP/IP finden Sie unter [Aktivieren des TCP/IP-Protokolls für eine Datenbankinstanz](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bb909712(v=vs.90)). Wenn Sie nur über ein Intranet auf eine Datenbank zugreifen, ist die Leistung des Protokolls für freigegebene Pipes möglicherweise besser, wenn das Netzwerk langsam ist.|
|Bereich|Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String)?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String,System.Data.SqlClient.SqlCredential)?displayProperty=nameWithType></li></ul>|
