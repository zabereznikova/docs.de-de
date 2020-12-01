---
title: 'Entschärfung: Poolsperrfrist'
description: Hier erfahren Sie, wie Sie Probleme beheben, die durch das Entfernen der Sperrfrist für den Verbindungspool für Verbindungen mit Azure SQL-Datenbanken verursacht werden.
ms.date: 03/30/2017
ms.assetid: 92d2de20-79be-4df1-b182-144143a8866a
ms.openlocfilehash: 270a71790f7a602df003415e9dc6dbf784cffdd7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276567"
---
# <a name="mitigation-pool-blocking-period"></a>Entschärfung: Poolsperrfrist

Die Sperrfrist für den Verbindungspool wurde für Verbindungen mit Azure SQL-Datenbanken entfernt.  
  
## <a name="additional-description"></a>Zusätzliche Beschreibung  

 Wenn in .NET Framework 4.6.1 und früheren Versionen eine App einen vorübergehender Verbindungsfehler beim Herstellen der Verbindung mit der Datenbank erkennt, kann der Verbindungsversuch nicht schnell wiederholt werden, da der Fehler vom Verbindungspool zwischengespeichert und für einen Zeitraum von fünf bis 60 Sekunden erneut ausgelöst wird. Weitere Informationen finden Sie unter [SQL Server-Verbindungspooling (ADO.NET)](../data/adonet/sql-server-connection-pooling.md). Dieses Verhalten ist für Verbindungen mit Azure SQL-Datenbanken problematisch, die häufig aufgrund vorübergehender Fehler fehlschlagen, die in der Regel innerhalb weniger Sekunden behoben sind. Das Sperrfeature des Verbindungspools bedeutet, dass die App für einen längeren Zeitraum keine Verbindung mit der Datenbank herstellen kann, auch wenn die Datenbank verfügbar ist. Dieses Verhalten ist besonders problematisch für Web-Apps, die eine Verbindung mit Azure SQL-Datenbanken herstellen und die innerhalb von wenigen Sekunden gerendert werden müssen.  
  
 Ab .NET Framework 4.6.2 werden Fehler bei Anforderungen zum Öffnen von Verbindungen mit bekannten Azure SQL-Datenbanken (*.database.Windows.net, \*.database.chinacloudapi.cn, \*.database.usgovcloudapi.net, \*.database.cloudapi.de) nicht mehr zwischengespeichert. Für alle anderen Verbindungsversuche wird die Sperrfrist für den Verbindungspool weiterhin erzwungen.  
  
## <a name="impact"></a>Auswirkungen  

 Diese Änderung ermöglicht die sofortige Wiederholung eines Versuchs zum Öffnen einer Verbindung mit Azure SQL-Datenbanken. Dadurch wird die Leistung von cloudfähigen Apps verbessert.  
  
## <a name="mitigation"></a>Minderung  

 Für Apps, die von dieser Änderung negativ betroffen sind, kann die Sperrfrist für den Verbindungspool konfiguriert werden, indem die neue <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A?displayProperty=nameWithType>-Eigenschaft festgelegt wird.  Der Wert der Eigenschaft ist ein Mitglied der <xref:System.Data.SqlClient.PoolBlockingPeriod?displayProperty=nameWithType>-Enumeration, die einen von drei Werten annehmen kann:  
  
- <xref:System.Data.SqlClient.PoolBlockingPeriod.AlwaysBlock?displayProperty=nameWithType>
  
- <xref:System.Data.SqlClient.PoolBlockingPeriod.Auto?displayProperty=nameWithType>
  
- <xref:System.Data.SqlClient.PoolBlockingPeriod.NeverBlock?displayProperty=nameWithType>
  
 Das vorherige Verhalten kann wiederhergestellt werden, indem Sie die <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A>-Eigenschaft auf <xref:System.Data.SqlClient.PoolBlockingPeriod.AlwaysBlock?displayProperty=nameWithType> festlegen.  
  
## <a name="see-also"></a>Siehe auch

- [Anwendungskompatibilität](application-compatibility.md)
