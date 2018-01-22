---
title: "SqlClient-Unterstützung für hohe Verfügbarkeit, Notfallwiederherstellung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 61e0b396-09d7-4e13-9711-7dcbcbd103a0
caps.latest.revision: "13"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 4f6ede253f52682cfe5a698cf4fb02841dc4c1e0
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="sqlclient-support-for-high-availability-disaster-recovery"></a>SqlClient-Unterstützung für hohe Verfügbarkeit, Notfallwiederherstellung
In diesem Thema wird die (in [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)] eingeführte) SqlClient-Unterstützung für hohe Verfügbarkeit und Notfallwiederherstellung erörtert, die in Form von AlwaysOn-Verfügbarkeitsgruppen bereitgestellt wird.  Die Funktion für AlwaysOn-Verfügbarkeitsgruppen wurde [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012 hinzugefügt. Weitere Informationen über AlwaysOn Availability Gruppen finden Sie unter [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Online-Bücher.  
  
 Sie können jetzt den Verfügbarkeitsgruppenlistener einer Verfügbarkeitsgruppe (für hohe Verfügbarkeit und Notfallwiederherstellung) oder eine [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012-Failoverclusterinstanz in der Verbindungseigenschaft angeben. Wenn eine SqlClient-Anwendung mit einer AlwaysOn-Datenbank verbunden ist, die einen Failover ausführt, ist die ursprüngliche Verbindung unterbrochen, und die Anwendung muss eine neue Verbindung öffnen, um die Arbeit nach dem Failover fortzusetzen.  
  
 Wenn Sie keine Verbindung mit einem Verfügbarkeitsgruppenlistener oder einer [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012-Failoverclusterinstanz herstellen und mehrere IP-Adressen einem Hostnamen zugeordnet sind, durchläuft SqlClient nacheinander alle IP-Adressen, die dem DNS-Eintrag zugeordnet sind. Dies kann zeitaufwändig sein, wenn die erste IP-Adresse, die vom DNS-Server zurückgegeben wird, an keine Netzwerkschnittstellenkarte (NIC) gebunden ist. Beim Herstellen einer Verbindung mit einem Verfügbarkeitsgruppenlistener oder einer [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012-Failoverclusterinstanz versucht SqlClient, Verbindungen mit allen IP-Adressen gleichzeitig herzustellen, und wenn ein Verbindungsversuch erfolgreich war, verwirft der Treiber alle ausstehenden Verbindungsversuche.  
  
> [!NOTE]
>  Ein höheres Verbindungstimeout und das Implementieren einer Logik für die Verbindungswiederholung erhöht die Wahrscheinlichkeit, dass eine Anwendung eine Verbindung mit einer Verfügbarkeitsgruppe herstellt. Da eine Verbindung aufgrund eines Failovers fehlschlagen kann, sollte auch eine Logik für Verbindungswiederholungen implementiert werden, die bis zur erfolgreichen Verbindung Verbindungswiederholungen durchführt.  
  
 Die folgenden Verbindungseigenschaften wurden SqlClient in [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)] hinzugefügt:  
  
-   `ApplicationIntent`  
  
-   `MultiSubnetFailover`  
  
 Sie können diese Schlüsselwörter für Verbindungszeichenfolgen programmgesteuert ändern:  
  
1.  <xref:System.Data.SqlClient.SqlConnectionStringBuilder.ApplicationIntent%2A>  
  
2.  <xref:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover%2A>  

> [!NOTE]
>  Festlegen von `MultiSubnetFailover` auf `true` ist nicht erforderlich, mit [!INCLUDE[net_v461](../../../../../includes/net-v461-md.md)]) oder höhere Versionen.
  
## <a name="connecting-with-multisubnetfailover"></a>Verbinden mit MultiSubnetFailover  
 Geben Sie immer `MultiSubnetFailover=True` an, wenn Sie eine Verbindung mit einem [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012-Verfügbarkeitsgruppenlistener oder einer [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012-Failoverclusterinstanz herstellen. `MultiSubnetFailover` ermöglicht ein schnelleres Failover für alle Verfügbarkeitsgruppen und/oder Failoverclusterinstanzen in [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012 und verringert erheblich die Failoverzeit für AlwaysOn-Topologien mit einem oder mehreren Subnetzen. Während eines Multisubnetzfailovers versucht der Client parallel, Verbindungen herzustellen. Während eines Subnetzfailovers wird die Herstellung der TCP-Verbindung aggressiv neu versucht.  
  
 Die `MultiSubnetFailover`-Verbindungseigenschaft gibt an, dass die Anwendung in einer Verfügbarkeitsgruppe oder [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012-Failoverclusterinstanz bereitgestellt wird und dass SqlClient versucht, eine Verbindung mit der Datenbank auf der primären [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]-Instanz herzustellen, indem eine Verbindung mit allen IP-Adressen versucht wird. Wenn `MultiSubnetFailover=True` für eine Verbindung angegeben wird, versucht der Client, TCP-Verbindungen schneller wiederherzustellen, als in den standardmäßigen TCP-Neuverbindungsintervallen des Betriebssystems angegeben. Dies ermöglicht die schnellere Wiederverbindung nach einem Failover einer AlwaysOn-Verfügbarkeitsgruppe oder einer AlwaysOn-Failoverclusterinstanz und ist auf Verfügbarkeitsgruppen und Failoverclusterinstanzen mit einem oder mehreren Subnetzen anwendbar.  
  
 Weitere Informationen über Schlüsselwörter für Verbindungszeichenfolgen in SqlClient finden Sie unter <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.  
  
 Das Angeben von `MultiSubnetFailover=True` wenn eine Verbindung mit anderen Komponenten als einem Verfügbarkeitsgruppenlistener oder einer [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012-Failoverclusterinstanz hergestellt wird, führt zu verminderter Leistung und wird nicht unterstützt.  
  
 Verwenden Sie die folgenden Richtlinien, um eine Verbindung mit einem Server in einer Verfügbarkeitsgruppe oder einer [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012-Failoverclusterinstanz herzustellen:  
  
-   Verwenden Sie die `MultiSubnetFailover`-Verbindungseigenschaft beim Herstellen der Verbindung mit einem einzelnen oder mehreren Subnetzen. Die Leistung wird in beiden Fällen gesteigert.  
  
-   Um eine Verbindung mit einer Verfügbarkeitsgruppe herzustellen, geben Sie den Verfügbarkeitsgruppenlistener der Verfügbarkeitsgruppe als Server in der Verbindungszeichenfolge an.  
  
-   Die Verbindung mit einer [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]-Instanz, die mit mehr als 64 IP-Adressen konfiguriert wurde, führt zu einem Verbindungsfehler.  
  
-   Das Verhalten einer Anwendung, die die `MultiSubnetFailover`-Verbindungseigenschaft verwendet, wird je nach Art der Authentifizierung nicht beeinflusst: [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]-Authentifizierung, Kerberos-Authentifizierung oder Windows-Authentifizierung.  
  
-   Erhöhen Sie den Wert von `Connect Timeout`, um die Failoverzeit anzupassen und die Wiederholungsversuche für die Verbindung mit der Anwendung zu verringern.  
  
-   Verteilte Transaktionen werden nicht unterstützt.  
  
 Wenn das schreibgeschützte Routing nicht aktiviert ist, schlägt die Verbindung mit dem Speicherort eines sekundären Replikats in folgenden Situationen fehl:  
  
1.  Wenn der Speicherort des sekundären Replikats keine Verbindungen akzeptiert.  
  
2.  Wenn eine Anwendung `ApplicationIntent=ReadWrite` (unten erläutert) verwendet und der Speicherort des sekundären Replikats für den schreibgeschützten Zugriff konfiguriert ist.  
  
 <xref:System.Data.SqlClient.SqlDependency> wird für schreibgeschützte sekundäre Replikate nicht unterstützt.  
  
 Ein Verbindungsfehler tritt auf, wenn ein primäres Replikat so konfiguriert ist, dass schreibgeschützte Arbeitslasten abgelehnt werden und die Verbindungszeichenfolge `ApplicationIntent=ReadOnly` enthält.  
  
## <a name="upgrading-to-use-multi-subnet-clusters-from-database-mirroring"></a>Upgrade von der Datenbankspiegelung auf die Verwendung von Multisubnetz-Clustern  
 Ein Verbindungsfehler (<xref:System.ArgumentException>) tritt auf, wenn die Verbindungsschlüsselwörter `MultiSubnetFailover` und `Failover Partner` in der Verbindungszeichenfolge vorhanden sind oder wenn `MultiSubnetFailover=True` und ein anderes Protokoll als TCP verwendet werden. Ein Fehler (<xref:System.Data.SqlClient.SqlException>) tritt ebenfalls auf, wenn `MultiSubnetFailover` verwendet wird und [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] eine Failoverpartnerantwort zurückgibt, die angibt, das die Anwendung Teil eines Datenbankspiegelungspaares ist.  
  
 Wenn Sie eine SqlClient-Anwendung, die aktuell die Datenbankspiegelung verwendet, auf ein Multisubnetz-Szenario aktualisieren, sollten Sie die `Failover Partner`-Verbindungseigenschaft entfernen und durch `MultiSubnetFailover` = `True` ersetzen und anstelle des Servernamens in der Verbindungszeichenfolge einen Verfügbarkeitsgruppenlistener verwenden. Wenn eine Verbindungszeichenfolge `Failover Partner` und `MultiSubnetFailover=True` verwendet, generiert der Treiber einen Fehler. Wenn jedoch eine Verbindungszeichenfolge `Failover Partner` und `MultiSubnetFailover=False` (oder `ApplicationIntent=ReadWrite`) verwendet, unterliegt die Anwendung der Datenbankspiegelung.  
  
 Der Treiber gibt einen Fehler zurück, wenn die Datenbankspiegelung auf der primären Datenbank in der Verfügbarkeitsgruppe verwendet wird und wenn `MultiSubnetFailover=True` in der Verbindungszeichenfolge verwendet wird, wodurch eine Verbindung mit einer primären Datenbank und nicht mit einem Verfügbarkeitsgruppenlistener hergestellt wird.  
  
## <a name="specifying-application-intent"></a>Angeben des Anwendungszwecks  
 Bei `ApplicationIntent=ReadOnly` fordert der Client eine Lesearbeitslast an, wenn er eine Verbindung mit einer AlwaysOn-fähigen Datenbank herstellt. Der Server erzwingt den Zweck zur Verbindungszeit und während einer USE-Datenbankanweisung, aber nur für eine AlwaysOn-fähige Datenbank.  
  
 Das `ApplicationIntent`-Schlüsselwort funktioniert nicht mit schreibgeschützten Legacy-Datenbanken.  
  
 Eine Datenbank kann Lesearbeitslasten für die AlwaysOn-Zieldatenbank zulassen oder ablehnen. (Dies erfolgt über die `ALLOW_CONNECTIONS`-Klausel der `PRIMARY_ROLE`-Anweisung und der `SECONDARY_ROLE`[!INCLUDE[tsql](../../../../../includes/tsql-md.md)]-Anweisung).  
  
 Das `ApplicationIntent`-Schlüsselwort wird verwendet, um das schreibgeschützte Routing zu aktivieren.  
  
## <a name="read-only-routing"></a>Schreibgeschütztes Routing  
 Das schreibgeschützte Routing ist eine Funktion, die die Verfügbarkeit eines schreibgeschützten Replikats einer Datenbank sicherstellt. So aktivieren Sie das schreibgeschützte Routing  
  
1.  Sie müssen eine Verbindung mit dem Verfügbarkeitsgruppenlistener einer AlwaysOn-Verfügbarkeitsgruppe herstellen.  
  
2.  Das `ApplicationIntent`-Schlüsselwort der Verbindungszeichenfolge muss auf `ReadOnly` festgelegt werden.  
  
3.  Die Verfügbarkeitsgruppe muss vom Datenbankadministrator so konfiguriert werden, dass schreibgeschütztes Routing aktiviert ist.  
  
 Es ist möglich, dass mehrere Verbindungen, die das schreibgeschützte Routing verwenden, nicht alle eine Verbindung mit demselben schreibgeschützten Replikat herstellen. Änderungen in der Datenbanksynchronisierung oder Änderungen an der Routingkonfiguration des Servers können dazu führen, dass Clientverbindungen mit anderen schreibgeschützten Replikaten hergestellt werden. Um sicherzustellen, dass alle schreibgeschützten Anforderungen an dasselbe schreibgeschützte Replikat gerichtet werden, übergeben Sie keinen Verfügbarkeitsgruppenlistener an das `Data Source`-Schlüsselwort der Verbindungszeichenfolge. Stattdessen geben Sie den Namen der schreibgeschützten Instanz an.  
  
 Das schreibgeschützte Routing dauert möglicherweise länger als die Verbindung mit der primären Datenbank, da zuerst eine Verbindung mit der primären Datenbank hergestellt und dann nach dem besten verfügbaren lesbaren sekundären Replikat gesucht wird. Aus diesem Grund sollten Sie das Anmeldetimeout erhöhen.  
  
## <a name="see-also"></a>Siehe auch  
 [SQL Server Features and ADO.NET (SQL Server-Features und ADO.NET)](../../../../../docs/framework/data/adonet/sql/sql-server-features-and-adonet.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
