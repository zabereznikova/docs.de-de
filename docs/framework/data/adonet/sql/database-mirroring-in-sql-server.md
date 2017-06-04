---
title: "Datenbankspiegelung in SQL&#160;Server | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 89befaff-bb46-4290-8382-e67cdb0e3de9
caps.latest.revision: 6
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 6
---
# Datenbankspiegelung in SQL&#160;Server
Mithilfe der Datenbankspiegelung in SQL Server können Sie eine Kopie, oder auch ein Spiegelbild, einer SQL Server\-Datenbank auf einem Standbyserver speichern.  Durch das Spiegeln wird sichergestellt, dass jederzeit zwei separate Kopien der Daten vorhanden sind. Dies gewährleistet eine hohe Verfügbarkeit und vollständige Datenredundanz.  Der .NET\-Datenanbieter für SQL Server stellt implizite Unterstützung für die Datenbankspiegelung bereit. Daher muss der Entwickler keine weiteren Schritte ausführen oder Code programmieren, nachdem die Spiegelung für eine SQL Server\-Datenbank konfiguriert wurde.  Außerdem unterstützt das <xref:System.Data.SqlClient.SqlConnection>\-Objekt einen expliziten Verbindungsmodus, über den der Name eines Failover\-Partnerservers im <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> angegeben werden kann.  
  
 Die folgende vereinfachte Ereignissequenz tritt bei einem <xref:System.Data.SqlClient.SqlConnection>\-Objekt ein, das eine Datenbank zum Ziel hat, welche für die Spiegelung konfiguriert wurde:  
  
1.  Die Clientanwendung stellt mit Erfolg eine Verbindung mit der Prinzipaldatenbank her, und der Server sendet den Namen des Partnerservers zurück, der dann auf dem Client zwischengespeichert wird.  
  
2.  Wenn der Server mit der Prinzipaldatenbank ausfällt oder die Konnektivität unterbrochen wird, gehen die Verbindung und der Transaktionsstatus verloren.  Die Clientanwendung versucht, erneut eine Verbindung mit der Prinzipaldatenbank herzustellen, und hat damit keinen Erfolg.  
  
3.  Die Clientanwendung versucht daraufhin transparent, eine Verbindung mit der Spiegeldatenbank auf dem Partnerserver herzustellen.  Wenn dieser Vorgang erfolgreich ausgeführt werden kann, wird die Verbindung zur Spiegeldatenbank umgeleitet, die daraufhin zur neuen Prinzipaldatenbank wird.  
  
## Angeben des Failoverpartners in der Verbindungszeichenfolge  
 Wenn Sie den Namen eines Failover\-Partnerservers in der Verbindungszeichenfolge angeben, versucht der Client transparent, eine Verbindung mit dem Failover\-Partnerserver herzustellen, wenn die Prinzipaldatenbank beim ersten Verbindungsversuch der Clientanwendung nicht verfügbar ist.  
  
```  
";Failover Partner=PartnerServerName"  
```  
  
 Wenn Sie den Namen des Failover\-Partnerservers nicht angeben und die Prinzipaldatenbank nicht verfügbar ist, wenn die Clientanwendung eine Verbindung herstellt, wird ein <xref:System.Data.SqlClient.SqlException>\-Objekt ausgelöst.  
  
 Wenn ein <xref:System.Data.SqlClient.SqlConnection> erfolgreich geöffnet wird, wird der Failover\-Partnername vom Server zurückgegeben. Er hat Vorrang vor allen in der Verbindungszeichenfolge angegebenen Werten.  
  
> [!NOTE]
>  Sie müssen den Namen des Anfangskatalogs oder der Angangsdatenbank explizit in der Verbindungszeichenfolge für Szenarien mit Datenbankspiegelung angeben.  Wenn der Client Failoverinformationen zu einer Verbindung empfängt, für die nicht explizit ein Anfangskatalog oder eine Anfangsdatenbank angegeben wurde, werden die Failoverinformationen nicht zwischengespeichert, und die Anwendung versucht auch nicht, bei einem Ausfall des Prinzipalservers einen Failover durchzuführen.  Wenn eine Verbindungszeichenfolge über einen Wert für den Failoverpartner, nicht jedoch über einen Wert für den Anfangskatalog oder die Anfangsdatenbank verfügt, wird eine `InvalidArgumentException` ausgelöst.  
  
## Abrufen des Namens für den aktuellen Server  
 Im Fall eines Failovers können Sie den Namen des Servers, mit dem tatsächlich die aktuelle Verbindung besteht, mit der <xref:System.Data.SqlClient.SqlConnection.DataSource%2A>\-Eigenschaft eines <xref:System.Data.SqlClient.SqlConnection>\-Objekts abrufen.  Das folgende Codefragment ruft den Namen des aktiven Servers ab. Dabei wird davon ausgegangen, dass die Verbindungsvariable auf eine geöffnete <xref:System.Data.SqlClient.SqlConnection> verweist.  
  
 Wenn ein Failover\-Ereignis eintritt und die Verbindung zum Spiegelserver wechselt, wird die **DataSource**\-Eigenschaft aktualisiert, um den Namen des Spiegelservers wiederzugeben.  
  
```vb  
Dim activeServer As String = connection.DataSource  
```  
  
```csharp  
string activeServer = connection.DataSource;  
```  
  
## Spiegelungsverhalten bei "SqlClient"  
 Der Client versucht stets, eine Verbindung mit dem aktuellen Prinzipalserver herzustellen.  Wenn keine Verbindung hergestellt werden kann, wechselt er zum Failover\-Partner.  Wenn die Spiegeldatenbank auf dem Partnerserver bereits auf die Prinzipalrolle heraufgestuft wurde, kann die Verbindung hergestellt werden. Die neue Prinzipal\-Spiegel\-Zuordnung wird an den Client gesendet und für die Lebensdauer der aufrufenden <xref:System.AppDomain> zwischengespeichert.  Sie wird nicht im dauerhaften Speicher gespeichert und ist für nachfolgende Verbindungen in einer anderen **AppDomain** oder einem anderen Prozess nicht verfügbar.  Sie ist allerdings für nachfolgende Verbindungen innerhalb derselben **AppDomain** verfügbar.  Beachten Sie, dass eine andere **AppDomain** oder ein anderer Prozess, die oder der auf demselben oder einem anderen Computer ausgeführt wird, immer über einen eigenen Pool von Verbindungen verfügt, die nicht zurückgesetzt werden.  Wenn in diesem Fall die primäre Datenbank ausfällt, wird jeder Prozess bzw. jede **AppDomain** einmal mit einem Fehler ausgeführt, und der Pool wird automatisch gelöscht.  
  
> [!NOTE]
>  Die Unterstützung für Spiegelung auf dem Server wird pro Datenbank konfiguriert.  Wenn für andere Datenbanken, die nicht zur Prinzipal\-Spiegel\-Konfiguration gehören, Datenbearbeitungsvorgänge ausgeführt werden \(entweder durch Verwendung mehrteiliger Namen oder durch Ändern der aktuellen Datenbank\), werden die Änderungen an diesen anderen Datenbanken bei einem Ausfall nicht übernommen.  Beim Ändern von Daten in einer Datenbank, die nicht gespiegelt ist, wird kein Fehler erzeugt.  Entwickler müssen die möglichen Auswirkungen solcher Vorgänge überprüfen.  
  
## Ressourcen zur Datenbankspiegelung  
 Die Begriffsdokumentation und Informationen zum Konfigurieren, Bereitstellen und Verwalten der Spiegelung finden Sie in den folgenden Ressourcen in der SQL Server\-Onlinedokumentation.  
  
|Ressource|Beschreibung|  
|---------------|------------------|  
|[Datenbankspiegelung](http://msdn.microsoft.com/library/bb934127.aspx) in der SQL Server\-Onlinedokumentation|Beschreibt, wie die Spiegelung in SQL Server eingerichtet und konfiguriert wird.|  
  
## Siehe auch  
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)