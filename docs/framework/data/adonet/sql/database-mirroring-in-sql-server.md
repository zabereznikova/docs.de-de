---
title: Datenbankspiegelungen in SQL Server
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 89befaff-bb46-4290-8382-e67cdb0e3de9
ms.openlocfilehash: 1445a95fc6360a7956048d2bae2d840f9c3f7a99
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59325695"
---
# <a name="database-mirroring-in-sql-server"></a>Datenbankspiegelungen in SQL Server
Mithilfe der Datenbankspiegelung in SQL Server können Sie eine Kopie, oder auch ein Spiegelbild, einer SQL Server-Datenbank auf einem Standbyserver speichern. Durch das Spiegeln wird sichergestellt, dass jederzeit zwei separate Kopien der Daten vorhanden sind. Dies gewährleistet Hochverfügbarkeit und vollständige Datenredundanz. Der .NET-Datenanbieter für SQL Server stellt implizite Unterstützung für die Datenbankspiegelung bereit. Daher muss der Entwickler keine weiteren Schritte ausführen oder Code programmieren, nachdem die Spiegelung für eine SQL Server-Datenbank konfiguriert wurde. Außerdem unterstützt das <xref:System.Data.SqlClient.SqlConnection>-Objekt einen expliziten Verbindungsmodus, über den der Name eines Failover-Partnerservers im <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> angegeben werden kann.  
  
 Die folgende vereinfachte Ereignissequenz tritt bei einem <xref:System.Data.SqlClient.SqlConnection>-Objekt ein, das eine Datenbank zum Ziel hat, welche für die Spiegelung konfiguriert wurde:  
  
1. Die Clientanwendung stellt mit Erfolg eine Verbindung mit der Prinzipaldatenbank her, und der Server sendet den Namen des Partnerservers zurück, der dann auf dem Client zwischengespeichert wird.  
  
2. Wenn der Server mit der Prinzipaldatenbank ausfällt oder die Konnektivität unterbrochen wird, gehen die Verbindung und der Transaktionsstatus verloren. Die Clientanwendung versucht, erneut eine Verbindung mit der Prinzipaldatenbank herzustellen, und hat damit keinen Erfolg.  
  
3. Die Clientanwendung versucht daraufhin transparent, eine Verbindung mit der Spiegeldatenbank auf dem Partnerserver herzustellen. Wenn dieser Vorgang erfolgreich ausgeführt werden kann, wird die Verbindung zur Spiegeldatenbank umgeleitet, die daraufhin zur neuen Prinzipaldatenbank wird.  
  
## <a name="specifying-the-failover-partner-in-the-connection-string"></a>Angeben des Failoverpartners in der Verbindungszeichenfolge  
 Wenn Sie den Namen eines Failover-Partnerservers in der Verbindungszeichenfolge angeben, versucht der Client transparent, eine Verbindung mit dem Failover-Partnerserver herzustellen, wenn die Prinzipaldatenbank beim ersten Verbindungsversuch der Clientanwendung nicht verfügbar ist.  
  
```  
";Failover Partner=PartnerServerName"  
```  
  
 Wenn Sie den Namen des Failover-Partnerservers nicht angeben und die Prinzipaldatenbank nicht verfügbar ist, wenn die Clientanwendung eine Verbindung herstellt, wird ein <xref:System.Data.SqlClient.SqlException>-Objekt ausgelöst.  
  
 Wenn ein <xref:System.Data.SqlClient.SqlConnection> erfolgreich geöffnet wird, wird der Failover-Partnername vom Server zurückgegeben. Er hat Vorrang vor allen in der Verbindungszeichenfolge angegebenen Werten.  
  
> [!NOTE]
>  Sie müssen den Namen des Anfangskatalogs oder der Angangsdatenbank explizit in der Verbindungszeichenfolge für Szenarien mit Datenbankspiegelung angeben. Wenn der Client Failoverinformationen zu einer Verbindung empfängt, für die nicht explizit ein Anfangskatalog oder eine Anfangsdatenbank angegeben wurde, werden die Failoverinformationen nicht zwischengespeichert, und die Anwendung versucht auch nicht, bei einem Ausfall des Prinzipalservers einen Failover durchzuführen. Wenn eine Verbindungszeichenfolge über einen Wert für den Failoverpartner, nicht jedoch über einen Wert für den Anfangskatalog oder die Anfangsdatenbank verfügt, wird eine `InvalidArgumentException` ausgelöst.  
  
## <a name="retrieving-the-current-server-name"></a>Abrufen des Namens für den aktuellen Server  
 Im Fall eines Failovers können Sie den Namen des Servers, mit dem tatsächlich die aktuelle Verbindung besteht, mit der <xref:System.Data.SqlClient.SqlConnection.DataSource%2A>-Eigenschaft eines <xref:System.Data.SqlClient.SqlConnection>-Objekts abrufen. Das folgende Codefragment ruft den Namen des aktiven Servers ab. Dabei wird davon ausgegangen, dass die Verbindungsvariable auf eine geöffnete <xref:System.Data.SqlClient.SqlConnection> verweist.  
  
 Wenn eine failoverereignis tritt auf, und die Verbindung an den Spiegelserver wechselt die **DataSource** -Eigenschaft aktualisiert, um den Namen des Spiegelservers wiederzugeben.  
  
```vb  
Dim activeServer As String = connection.DataSource  
```  
  
```csharp  
string activeServer = connection.DataSource;  
```  
  
## <a name="sqlclient-mirroring-behavior"></a>Spiegelungsverhalten bei "SqlClient"  
 Der Client versucht stets, eine Verbindung mit dem aktuellen Prinzipalserver herzustellen. Wenn keine Verbindung hergestellt werden kann, wechselt er zum Failover-Partner. Wenn die Spiegeldatenbank auf dem Partnerserver bereits auf die Prinzipalrolle heraufgestuft wurde, kann die Verbindung hergestellt werden. Die neue Prinzipal-Spiegel-Zuordnung wird an den Client gesendet und für die Lebensdauer der aufrufenden <xref:System.AppDomain> zwischengespeichert. Es ist nicht im dauerhaften Speicher gespeichert und ist nicht verfügbar für nachfolgende Verbindungen in einem anderen **AppDomain** oder Prozess. Allerdings ist es verfügbaren für nachfolgende Verbindungen innerhalb des gleichen **AppDomain**. Beachten Sie, dass eine andere **AppDomain** immer auf demselben oder einem anderen Computer ausgeführten Prozess hat eigenen Pool von Verbindungen und diese Verbindungen werden nicht zurückgesetzt. In diesem Fall, wenn die primäre Datenbank ausfällt, jede verarbeiten oder **AppDomain** einmal ein Fehler auftritt, und der Pool wird automatisch gelöscht.  
  
> [!NOTE]
>  Die Unterstützung für Spiegelung auf dem Server wird pro Datenbank konfiguriert. Wenn für andere Datenbanken, die nicht zur Prinzipal-Spiegel-Konfiguration gehören, Datenbearbeitungsvorgänge ausgeführt werden (entweder durch Verwendung mehrteiliger Namen oder durch Ändern der aktuellen Datenbank), werden die Änderungen an diesen anderen Datenbanken bei einem Ausfall nicht übernommen. Beim Ändern von Daten in einer Datenbank, die nicht gespiegelt ist, wird kein Fehler erzeugt. Entwickler müssen die möglichen Auswirkungen solcher Vorgänge überprüfen.  
  
## <a name="database-mirroring-resources"></a>Ressourcen zur Datenbankspiegelung  
 Die Begriffsdokumentation und Informationen zum Konfigurieren bereitstellen und Verwalten der datenbankspiegelung, finden Sie unter den folgenden Ressourcen in SQL Server-Dokumentation.  
  
|Ressource|Beschreibung|  
|--------------|-----------------|  
|[Datenbankspiegelung](/sql/database-engine/database-mirroring/database-mirroring-sql-server)|Beschreibt, wie die Spiegelung in SQL Server eingerichtet und konfiguriert wird.|  
  
## <a name="see-also"></a>Siehe auch

- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
