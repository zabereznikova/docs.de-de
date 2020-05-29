---
ms.openlocfilehash: 4a60f4b135d5710ad0cc4900337e2970ffb8dd58
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83435411"
---
### <a name="connection-pool-blocking-period-for-azure-sql-databases-is-removed"></a>Die Sperrfrist des Verbindungspools für Azure SQL-Datenbanken wurde entfernt

|   |   |
|---|---|
|Details|Ab .NET Framework 4.6.2 werden Fehler bei Anforderungen zum Öffnen von Verbindungen mit bekannten Azure SQL-Datenbanken (\*.database.Windows.NET, \*.database.chinacloudapi.cn, \*.database.usgovcloudapi.net, \*.database.cloudapi.de) nicht zwischengespeichert, und die Sperrfrist des Verbindungspools wird entfernt. Wiederholungsversuche von Anforderungen zum Öffnen von Verbindungen erfolgen nahezu unmittelbar nach vorübergehenden Verbindungsfehlern. Diese Änderung ermöglicht die sofortige Wiederholung eines Versuchs zum Öffnen einer Verbindung mit Azure SQL-Datenbanken. Dadurch wird die Leistung von cloudfähigen Apps verbessert. Für alle anderen Verbindungsversuche wird die Sperrfrist für den Verbindungspool weiterhin erzwungen.<p/>Wenn in .NET Framework 4.6.1 und früherer Versionen eine App einen vorübergehender Verbindungsfehler beim Herstellen der Verbindung mit der Datenbank erkennt, kann der Verbindungsversuch nicht schnell wiederholt werden, da der Fehler vom Verbindungspool im Cache gespeichert und 5 Sekunden bis 1 Minute erneut ausgelöst wird. Weitere Informationen finden Sie unter [SQL Server-Verbindungspooling (ADO.NET)](~/docs/framework/data/adonet/sql-server-connection-pooling.md). Dieses Verhalten ist für Verbindungen mit Azure SQL-Datenbanken problematisch, die häufig aufgrund vorübergehender Fehler fehlschlagen, die in der Regel innerhalb weniger Sekunden behoben sind. Das Sperrfeature des Verbindungspools bedeutet, dass die App für einen längeren Zeitraum keine Verbindung mit der Datenbank herstellen kann, obwohl die Datenbank verfügbar ist und die App innerhalb weniger Sekunden rendern muss.|
|Vorschlag|Wenn dieses Verhalten nicht erwünscht ist, kann die Sperrfrist des Verbindungspools konfiguriert werden, indem die <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod?displayProperty=name>-Eigenschaft festgelegt wird, die in .NET Framework 4.6.2 eingeführt wurde. Der Wert der Eigenschaft ist ein Mitglied der <xref:System.Data.SqlClient.PoolBlockingPeriod?displayProperty=name>-Enumeration, die einen von drei Werten annehmen kann:<ul><li><xref:System.Data.SqlClient.PoolBlockingPeriod.AlwaysBlock></li><li><xref:System.Data.SqlClient.PoolBlockingPeriod.Auto></li><li><xref:System.Data.SqlClient.PoolBlockingPeriod.NeverBlock></li></ul>Das vorherige Verhalten kann wiederhergestellt werden, indem Sie die <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod?displayProperty=name>-Eigenschaft auf <xref:System.Data.SqlClient.PoolBlockingPeriod.AlwaysBlock> festlegen.|
|Bereich|Gering|
|Version|4.6.2|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Data.Common.DbConnection.OpenAsync?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnection.Open?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnection.OpenAsync(System.Threading.CancellationToken)?displayProperty=nameWithType></li></ul>|
