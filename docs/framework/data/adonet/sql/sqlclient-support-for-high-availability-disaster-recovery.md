---
title: SqlClient-Unterstützung für hohe Verfügbarkeit, Notfallwiederherstellung
ms.date: 03/30/2017
ms.assetid: 61e0b396-09d7-4e13-9711-7dcbcbd103a0
ms.openlocfilehash: 104fdd78ce3f4b9c18f09fc41fddebe46815d217
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938468"
---
# <a name="sqlclient-support-for-high-availability-disaster-recovery"></a>SqlClient-Unterstützung für hohe Verfügbarkeit, Notfallwiederherstellung
In diesem Thema wird die SqlClient-Unterstützung (in .NET Framework 4,5) für hohe Verfügbarkeit, Notfall Wiederherstellung (AlwaysOn-Verfügbarkeitsgruppen) erläutert.  AlwaysOn-Verfügbarkeitsgruppen Funktion wurde SQL Server 2012 hinzugefügt. Weitere Informationen zu AlwaysOn-Verfügbarkeitsgruppen finden Sie unter SQL Server-Onlinedokumentation.  
  
 Sie können jetzt den verfügbarkeitsgruppenlistener einer Verfügbarkeits Gruppe (hohe Verfügbarkeit, Notfall Wiederherstellung) oder SQL Server 2012-Failoverclusterinstanz in der Connection-Eigenschaft angeben. Wenn eine SqlClient-Anwendung mit einer AlwaysOn-Datenbank verbunden ist, die einen Failover ausführt, ist die ursprüngliche Verbindung unterbrochen, und die Anwendung muss eine neue Verbindung öffnen, um die Arbeit nach dem Failover fortzusetzen.  
  
 Wenn Sie keine Verbindung mit einem verfügbarkeitsgruppenlistener oder SQL Server 2012-Failoverclusterinstanz herstellen und mehrere IP-Adressen einem Hostnamen zugeordnet sind, durchläuft SqlClient sequenziell alle IP-Adressen, die dem DNS-Eintrag zugeordnet sind. Dies kann zeitaufwändig sein, wenn die erste IP-Adresse, die vom DNS-Server zurückgegeben wird, an keine Netzwerkschnittstellenkarte (NIC) gebunden ist. Beim Herstellen einer Verbindung mit einem verfügbarkeitsgruppenlistener oder einer SQL Server 2012-Failoverclusterinstanz wird von SqlClient versucht, Verbindungen mit allen IP-Adressen parallel herzustellen. Wenn ein Verbindungsversuch erfolgreich ist, verwirft der Treiber alle ausstehenden Verbindungen. unternommen.  
  
> [!NOTE]
> Ein höheres Verbindungstimeout und das Implementieren einer Logik für die Verbindungswiederholung erhöht die Wahrscheinlichkeit, dass eine Anwendung eine Verbindung mit einer Verfügbarkeitsgruppe herstellt. Da eine Verbindung aufgrund eines Failovers fehlschlagen kann, sollte auch eine Logik für Verbindungswiederholungen implementiert werden, die bis zur erfolgreichen Verbindung Verbindungswiederholungen durchführt.  
  
 Die folgenden Verbindungs Eigenschaften wurden SqlClient in .NET Framework 4,5 hinzugefügt:  
  
- `ApplicationIntent`  
  
- `MultiSubnetFailover`  
  
 Sie können diese Schlüsselwörter für Verbindungszeichenfolgen programmgesteuert ändern:  
  
1. <xref:System.Data.SqlClient.SqlConnectionStringBuilder.ApplicationIntent%2A>  
  
2. <xref:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover%2A>  

> [!NOTE]
> Das `MultiSubnetFailover` festlegen `true` von auf ist für .NET Framework 4.6.1 oder höhere Versionen nicht erforderlich.
  
## <a name="connecting-with-multisubnetfailover"></a>Verbinden mit MultiSubnetFailover  
 Geben `MultiSubnetFailover=True` Sie immer an, wenn Sie eine Verbindung mit einem 2012 SQL Server verfügbarkeitsgruppenlistener oder einer SQL Server 2012-Failovercluster `MultiSubnetFailover`ermöglicht ein schnelleres Failover für alle Verfügbarkeits Gruppen und oder Failoverclusterinstanzen in SQL Server 2012 und reduziert die Failoverzeit für einzelne und multisubnetz-AlwaysOn-Topologien erheblich. Während eines Multisubnetzfailovers versucht der Client parallel, Verbindungen herzustellen. Während eines Subnetzfailovers wird die Herstellung der TCP-Verbindung aggressiv neu versucht.  
  
 Die `MultiSubnetFailover` -Verbindungs Eigenschaft gibt an, dass die Anwendung in einer Verfügbarkeits Gruppe oder SQL Server 2012-Failoverclusterinstanz bereitgestellt wird und dass SqlClient versucht, eine Verbindung mit der Datenbank auf der primären SQL Server Instanz herzustellen. Stellen Sie eine Verbindung mit allen IP-Adressen her. Wenn `MultiSubnetFailover=True` für eine Verbindung angegeben wird, versucht der Client, TCP-Verbindungen schneller wiederherzustellen, als in den standardmäßigen TCP-Neuverbindungsintervallen des Betriebssystems angegeben. Dies ermöglicht die schnellere Wiederverbindung nach einem Failover einer AlwaysOn-Verfügbarkeitsgruppe oder einer AlwaysOn-Failoverclusterinstanz und ist auf Verfügbarkeitsgruppen und Failoverclusterinstanzen mit einem oder mehreren Subnetzen anwendbar.  
  
 Weitere Informationen über Schlüsselwörter für Verbindungszeichenfolgen in SqlClient finden Sie unter <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.  
  
 Wenn `MultiSubnetFailover=True` Sie angeben, dass eine Verbindung mit einem anderen als einem verfügbarkeitsgruppenlistener oder SQL Server 2012-Failoverclusterinstanz hergestellt werden kann, kann dies zu negativen Auswirkungen auf die Leistung führen.  
  
 Verwenden Sie die folgenden Richtlinien zum Herstellen einer Verbindung mit einem Server in einer Verfügbarkeits Gruppe oder SQL Server 2012-Failoverclusterinstanz:  
  
- Verwenden Sie die `MultiSubnetFailover`-Verbindungseigenschaft beim Herstellen der Verbindung mit einem einzelnen oder mehreren Subnetzen. Die Leistung wird in beiden Fällen gesteigert.  
  
- Um eine Verbindung mit einer Verfügbarkeitsgruppe herzustellen, geben Sie den Verfügbarkeitsgruppenlistener der Verfügbarkeitsgruppe als Server in der Verbindungszeichenfolge an.  
  
- Das Herstellen einer Verbindung mit einer SQL Server-Instanz, die mit mehr als 64 IP-Adressen konfiguriert ist, verursacht einen Verbindungsfehler  
  
- Das Verhalten einer Anwendung, die die `MultiSubnetFailover` -Verbindungs Eigenschaft verwendet, wird nicht vom Authentifizierungstyp beeinflusst: SQL Server-Authentifizierung, Kerberos-Authentifizierung oder Windows-Authentifizierung.  
  
- Erhöhen Sie den Wert von `Connect Timeout`, um die Failoverzeit anzupassen und die Wiederholungsversuche für die Verbindung mit der Anwendung zu verringern.  
  
- Verteilte Transaktionen werden nicht unterstützt.  
  
 Wenn das schreibgeschützte Routing nicht aktiviert ist, schlägt die Verbindung mit dem Speicherort eines sekundären Replikats in folgenden Situationen fehl:  
  
1. Wenn der Speicherort des sekundären Replikats keine Verbindungen akzeptiert.  
  
2. Wenn eine Anwendung `ApplicationIntent=ReadWrite` (unten erläutert) verwendet und der Speicherort des sekundären Replikats für den schreibgeschützten Zugriff konfiguriert ist.  
  
 <xref:System.Data.SqlClient.SqlDependency> wird für schreibgeschützte sekundäre Replikate nicht unterstützt.  
  
 Ein Verbindungsfehler tritt auf, wenn ein primäres Replikat so konfiguriert ist, dass schreibgeschützte Arbeitslasten abgelehnt werden und die Verbindungszeichenfolge `ApplicationIntent=ReadOnly` enthält.  
  
## <a name="upgrading-to-use-multi-subnet-clusters-from-database-mirroring"></a>Upgrade von der Datenbankspiegelung auf die Verwendung von Multisubnetz-Clustern  
 Ein Verbindungsfehler (<xref:System.ArgumentException>) tritt auf, wenn die Verbindungsschlüsselwörter `MultiSubnetFailover` und `Failover Partner` in der Verbindungszeichenfolge vorhanden sind oder wenn `MultiSubnetFailover=True` und ein anderes Protokoll als TCP verwendet werden. Ein Fehler (<xref:System.Data.SqlClient.SqlException>) tritt auch auf, `MultiSubnetFailover` wenn verwendet wird und das SQL Server eine failoverpartnerantwort zurückgibt, die angibt, dass es Teil eines Daten Bank Spiegelungs Paars ist.  
  
 Wenn Sie eine SqlClient-Anwendung, die aktuell die Datenbankspiegelung verwendet, auf ein Multisubnetz-Szenario aktualisieren, sollten Sie die `Failover Partner`-Verbindungseigenschaft entfernen und durch `MultiSubnetFailover` = `True` ersetzen und anstelle des Servernamens in der Verbindungszeichenfolge einen Verfügbarkeitsgruppenlistener verwenden. Wenn eine Verbindungszeichenfolge `Failover Partner` und `MultiSubnetFailover=True` verwendet, generiert der Treiber einen Fehler. Wenn jedoch eine Verbindungszeichenfolge `Failover Partner` und `MultiSubnetFailover=False` (oder `ApplicationIntent=ReadWrite`) verwendet, unterliegt die Anwendung der Datenbankspiegelung.  
  
 Der Treiber gibt einen Fehler zurück, wenn die Datenbankspiegelung auf der primären Datenbank in der Verfügbarkeitsgruppe verwendet wird und wenn `MultiSubnetFailover=True` in der Verbindungszeichenfolge verwendet wird, wodurch eine Verbindung mit einer primären Datenbank und nicht mit einem Verfügbarkeitsgruppenlistener hergestellt wird.  
  
## <a name="specifying-application-intent"></a>Angeben des Anwendungszwecks  
 Bei `ApplicationIntent=ReadOnly` fordert der Client eine Lesearbeitslast an, wenn er eine Verbindung mit einer AlwaysOn-fähigen Datenbank herstellt. Der Server erzwingt den Zweck zur Verbindungszeit und während einer USE-Datenbankanweisung, aber nur für eine AlwaysOn-fähige Datenbank.  
  
 Das `ApplicationIntent`-Schlüsselwort funktioniert nicht mit schreibgeschützten Legacy-Datenbanken.  
  
 Eine Datenbank kann Lesearbeitslasten für die AlwaysOn-Zieldatenbank zulassen oder ablehnen. (Dies erfolgt mit der `ALLOW_CONNECTIONS` `PRIMARY_ROLE` -Klausel der-Anweisung `SECONDARY_ROLE`und der Transact-SQL-Anweisung.)  
  
 Das `ApplicationIntent`-Schlüsselwort wird verwendet, um das schreibgeschützte Routing zu aktivieren.  
  
## <a name="read-only-routing"></a>Schreibgeschütztes Routing  
 Das schreibgeschützte Routing ist eine Funktion, die die Verfügbarkeit eines schreibgeschützten Replikats einer Datenbank sicherstellt. So aktivieren Sie das schreibgeschützte Routing  
  
1. Sie müssen eine Verbindung mit dem Verfügbarkeitsgruppenlistener einer AlwaysOn-Verfügbarkeitsgruppe herstellen.  
  
2. Das `ApplicationIntent`-Schlüsselwort der Verbindungszeichenfolge muss auf `ReadOnly` festgelegt werden.  
  
3. Die Verfügbarkeitsgruppe muss vom Datenbankadministrator so konfiguriert werden, dass schreibgeschütztes Routing aktiviert ist.  
  
 Es ist möglich, dass mehrere Verbindungen, die das schreibgeschützte Routing verwenden, nicht alle eine Verbindung mit demselben schreibgeschützten Replikat herstellen. Änderungen in der Datenbanksynchronisierung oder Änderungen an der Routingkonfiguration des Servers können dazu führen, dass Clientverbindungen mit anderen schreibgeschützten Replikaten hergestellt werden. Um sicherzustellen, dass alle schreibgeschützten Anforderungen an dasselbe schreibgeschützte Replikat gerichtet werden, übergeben Sie keinen Verfügbarkeitsgruppenlistener an das `Data Source`-Schlüsselwort der Verbindungszeichenfolge. Stattdessen geben Sie den Namen der schreibgeschützten Instanz an.  
  
 Das schreibgeschützte Routing dauert möglicherweise länger als die Verbindung mit der primären Datenbank, da zuerst eine Verbindung mit der primären Datenbank hergestellt und dann nach dem besten verfügbaren lesbaren sekundären Replikat gesucht wird. Aus diesem Grund sollten Sie das Anmeldetimeout erhöhen.  
  
## <a name="see-also"></a>Siehe auch

- [SQL Server Features and ADO.NET (SQL Server-Features und ADO.NET)](../../../../../docs/framework/data/adonet/sql/sql-server-features-and-adonet.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
