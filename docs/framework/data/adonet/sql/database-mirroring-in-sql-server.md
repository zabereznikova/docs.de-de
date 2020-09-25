---
title: Datenbankspiegelungen in SQL Server
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 89befaff-bb46-4290-8382-e67cdb0e3de9
ms.openlocfilehash: 7e2c1c8ea1cbc1bb22452b9ef9d1f250c96118ea
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173535"
---
# <a name="database-mirroring-in-sql-server"></a>Datenbankspiegelungen in SQL Server

Mithilfe der Datenbankspiegelung in SQL Server können Sie eine Kopie, oder auch Spiegelbild, einer SQL Server-Datenbank auf einem Standbyserver speichern. Die Spiegelung stellt sicher, dass jederzeit zwei getrennte Kopien der Daten vorhanden sind, was Hochverfügbarkeit und vollständige Datenredundanz gewährleistet. Der .NET-Datenanbieter für SQL Server stellt implizite Unterstützung für die Datenbankspiegelung bereit. Daher muss der Entwickler keine weiteren Schritte ausführen oder Code programmieren, nachdem die Spiegelung für eine SQL Server-Datenbank konfiguriert wurde. Zusätzlich unterstützt das <xref:System.Data.SqlClient.SqlConnection>-Objekt einen expliziten Verbindungsmodus, der es erlaubt, den Namen eines Failoverpartnerservers in <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> anzugeben.  
  
 Die folgende vereinfachte Ereignissequenz erfolgt für ein <xref:System.Data.SqlClient.SqlConnection>-Objekt, das eine für Spiegelung konfigurierte Datenbank als Ziel hat:  
  
1. Die Clientanwendung verbindet sich erfolgreich mit der Prinzipaldatenbank, und der Server sendet den Namen des Partnerservers zurück, der dann auf dem Client zwischengespeichert wird.  
  
2. Wenn der Server mit der Prinzipaldatenbank ausfällt oder die Verbindung unterbrochen wird, gehen Verbindung und Transaktionsstatus verloren. Die Clientanwendung versucht, wieder eine Verbindung mit der Prinzipaldatenbank herzustellen, und schlägt fehl.  
  
3. Die Clientanwendung versucht dann auf transparente Weise, eine Verbindung mit der Spiegeldatenbank auf dem Partnerserver herzustellen. Bei Erfolg wird die Verbindung zur Spiegeldatenbank umgeleitet, die dann zur neuen Prinzipaldatenbank wird.  
  
## <a name="specifying-the-failover-partner-in-the-connection-string"></a>Angeben des Failoverpartners in der Verbindungszeichenfolge  

 Wenn Sie den Namen eines Failoverpartnerservers in der Verbindungszeichenfolge angeben, versucht der Client transparent eine Verbindung mit dem Failoverpartner herzustellen, sofern die Prinzipaldatenbank beim ersten Verbindungsversuch der Clientanwendung nicht verfügbar ist.  
  
```csharp
";Failover Partner=PartnerServerName"  
```  
  
 Wenn Sie den Namen des Failoverpartnerservers weglassen und die Hauptdatenbank beim ersten Verbindungsversuch der Clientanwendung nicht verfügbar ist, wird eine <xref:System.Data.SqlClient.SqlException> ausgelöst.  
  
 Wenn <xref:System.Data.SqlClient.SqlConnection> erfolgreich geöffnet wird, wird der Failoverpartnername vom Server zurückgegeben und ersetzt alle in der Verbindungszeichenfolge angegebenen Werte.  
  
> [!NOTE]
> In Szenarien mit Datenbankspiegelung müssen Sie den Ausgangskatalog oder Datenbanknamen explizit in der Verbindungszeichenfolge angeben. Wenn der Client Failover-Informationen zu einer Verbindung empfängt, für die nicht explizit ein Anfangskatalog oder eine Anfangsdatenbank angegeben wurde, werden die Failover-Informationen nicht zwischengespeichert und die Anwendung versucht auch nicht, bei einem Ausfall des Prinzipalservers einen Failover durchzuführen. Wenn eine Verbindungszeichenfolge einen Wert für den Failoverpartner, aber keinen Wert für den Ausgangskatalog oder die Datenbank hat, wird eine `InvalidArgumentException` ausgelöst.  
  
## <a name="retrieving-the-current-server-name"></a>Abrufen des Namens für den aktuellen Server  

 Bei einem Failover können Sie den Namen des Servers abrufen, mit dem die aktuelle Verbindung tatsächlich besteht, indem Sie die <xref:System.Data.SqlClient.SqlConnection.DataSource%2A>-Eigenschaft eines <xref:System.Data.SqlClient.SqlConnection>-Objekts verwenden. Das folgende Codefragment ruft den Namen des aktiven Servers ab, wobei angenommen wird, dass die Verbindungsvariable auf eine geöffnete <xref:System.Data.SqlClient.SqlConnection> verweist.  
  
 Wenn ein Failover-Ereignis eintritt und die Verbindung zum Spiegelserver wechselt, wird die **DataSource**-Eigenschaft aktualisiert, um den Namen des Spiegelservers wiederzugeben.  
  
```vb  
Dim activeServer As String = connection.DataSource  
```  
  
```csharp  
string activeServer = connection.DataSource;  
```  
  
## <a name="sqlclient-mirroring-behavior"></a>Spiegelungsverhalten bei "SqlClient"  

 Der Client versucht stets, eine Verbindung mit dem aktuellen Prinzipalserver herzustellen. Bei Misserfolg wird der Failoverpartner versucht. Wenn die Spiegeldatenbank bereits auf die Prinzipalrolle auf dem Partnerserver umgestellt wurde, ist die Verbindung erfolgreich. Die neue Zuordnung zwischen Prinzipal und Spiegel wird an den Client gesendet und für die Lebensdauer des Aufrufs von <xref:System.AppDomain> zwischengespeichert. Sie wird nicht im dauerhaften Speicher gespeichert und ist für nachfolgende Verbindungen in einer anderen **AppDomain** oder einem anderen Prozess nicht verfügbar. Sie ist allerdings für nachfolgende Verbindungen innerhalb derselben **AppDomain** verfügbar. Beachten Sie, dass eine andere **AppDomain** oder ein anderer Prozess, die oder der auf demselben oder einem anderen Computer ausgeführt wird, immer über einen eigenen Pool von Verbindungen verfügt, die nicht zurückgesetzt werden. Wenn in diesem Fall die primäre Datenbank ausfällt, wird jeder Prozess bzw. jede **AppDomain** einmal mit einem Fehler ausgeführt, und der Pool wird automatisch gelöscht.  
  
> [!NOTE]
> Die Unterstützung der Spiegelung auf dem Server wird datenbankbezogen konfiguriert. Wenn Datenbearbeitungsvorgänge auf andere, nicht im Prinzipal-/Spiegelsatz enthaltene Datenbanken angewendet werden, entweder durch Verwendung mehrteiliger Namen oder durch Änderung der aktuellen Datenbank, werden die Änderungen an diesen anderen Datenbanken bei einem Fehler nicht weitergegeben. Wenn Daten in einer nicht gespiegelten Datenbank geändert werden, wird kein Fehler ausgegeben. Der Entwickler muss die möglichen Auswirkungen solcher Vorgänge einschätzen.  
  
## <a name="database-mirroring-resources"></a>Ressourcen zur Datenbankspiegelung  

 Die Begriffsdokumentation und Informationen zum Konfigurieren, Bereitstellen und Verwalten der Spiegelung finden Sie in den folgenden Ressourcen in der SQL Server-Dokumentation.  
  
|Resource|BESCHREIBUNG|  
|--------------|-----------------|  
|[Datenbankspiegelung](/sql/database-engine/database-mirroring/database-mirroring-sql-server)|Beschreibt, wie Spiegelung in SQL Server eingerichtet und konfiguriert wird.|  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über ADO.NET](../ado-net-overview.md)
