---
title: Aktivieren von Multiple Active Result Sets
description: Erfahren Sie, wie Sie Mars in einer Verbindungs Zeichenfolge aktivieren bzw. deaktivieren, die mit SQL Server funktioniert, sodass Sie mehrere Batches in einer einzelnen Verbindung in ADO.net ausführen können.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 576079e4-debe-4ab5-9204-fcbe2ca7a5e2
ms.openlocfilehash: 0c5b4043b389c7dde39a477f90e82bbf654331f7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156250"
---
# <a name="enabling-multiple-active-result-sets"></a>Aktivieren von Multiple Active Result Sets

MARS ist eine Funktion, die mit SQL Server verwendet wird und das Ausführen mehrerer Batches über eine einzelne Verbindung ermöglicht. Wenn MARS für die Verwendung mit SQL Server aktiviert wird, fügen die einzelnen verwendeten Befehlsobjekte der Verbindung eine Sitzung hinzu.  
  
> [!NOTE]
> Eine einzelne MARS-Sitzung öffnet eine logische Verbindung, die MARS verwenden kann, und dann eine logische Verbindung für jeden aktiven Befehl.  
  
## <a name="enabling-and-disabling-mars-in-the-connection-string"></a>Aktivieren und Deaktivieren von MARS in der Verbindungszeichenfolge  
  
> [!NOTE]
> Die folgenden Verbindungszeichenfolgen verwenden die **AdventureWorks**-Beispieldatenbank aus SQL Server. Die angegebenen Verbindungszeichenfolgen setzen voraus, dass die Datenbank auf einem Server namens MSSQL1 installiert ist. Ändern Sie die Verbindungszeichenfolge nach Bedarf für Ihre Umgebung.  
  
 Die MARS-Feature ist standardmäßig deaktiviert. Sie kann durch Hinzufügen des Schlüsselwortpaares „MultipleActiveResultSets=True“ zu Ihrer Verbindungszeichenfolge aktiviert werden. „True“ ist der einzige gültige Wert zum Aktivieren von MARS. Das folgende Beispiel zeigt, wie eine Verbindung mit einer Instanz von SQL Server hergestellt wird und wie angegeben wird, dass MARS aktiviert werden soll.  
  
```vb  
Dim connectionString As String = "Data Source=MSSQL1;" & _  
    "Initial Catalog=AdventureWorks;Integrated Security=SSPI;" & _  
    "MultipleActiveResultSets=True"  
```  
  
```csharp  
string connectionString = "Data Source=MSSQL1;" +
    "Initial Catalog=AdventureWorks;Integrated Security=SSPI;" +  
    "MultipleActiveResultSets=True";  
```  
  
 Sie können MARS deaktivieren, indem Sie das Schlüsselwortpaar „MultipleActiveResultSets=False“ zu Ihrer Verbindungszeichenfolge hinzufügen. „False“ ist der einzige gültige Wert zum Deaktivieren von MARS. Die folgende Verbindungszeichenfolge zeigt, wie MARS deaktiviert werden kann.  
  
```vb  
Dim connectionString As String = "Data Source=MSSQL1;" & _  
    "Initial Catalog=AdventureWorks;Integrated Security=SSPI;" & _  
    "MultipleActiveResultSets=False"  
```  
  
```csharp  
string connectionString = "Data Source=MSSQL1;" +
    "Initial Catalog=AdventureWorks;Integrated Security=SSPI;" +  
    "MultipleActiveResultSets=False";  
```  
  
## <a name="special-considerations-when-using-mars"></a>Besondere Überlegungen bei der Verwendung von MARS  

 Im Allgemeinen sollten bestehende Anwendungen nicht modifiziert werden müssen, um eine MARS-fähige Verbindung zu nutzen. Wenn Sie jedoch MARS-Features in Ihren Anwendungen verwenden möchten, sollten Sie mit den folgenden besonderen Aspekten vertraut sein.  
  
### <a name="statement-interleaving"></a>Überlappen von Anweisungen  

 MARS-Vorgänge werden auf dem Server synchron ausgeführt. Die Überlappung von SELECT- und BULK INSERT-Anweisungen ist zulässig. DML- (Data Manipulation Language) und DDL-Anweisungen (Data Definition Language) werden jedoch atomisch ausgeführt. Alle Anweisungen, die versuchen, während der Ausführung eines atomischen Batches ausgeführt zu werden, werden blockiert. Die parallele Ausführung auf dem Server ist kein MARS-Feature.  
  
 Wenn zwei Batches über eine MARS-Verbindung übermittelt werden, von denen einer eine SELECT-Anweisung und der andere eine DML-Anweisung enthält, kann DML mit der Ausführung innerhalb der Ausführung der SELECT-Anweisung beginnen. Die DML-Anweisung muss jedoch vollständig abgeschlossen werden, ehe die SELECT-Anweisung fortgesetzt werden kann. Wenn beide Anweisungen innerhalb derselben Transaktion ausgeführt werden, sind alle Änderungen, die durch eine DML-Anweisung nach Beginn der Ausführung der SELECT-Anweisung vorgenommen werden, für den Lesevorgang nicht sichtbar.  
  
 Eine WAITFOR-Anweisung innerhalb einer SELECT-Anweisung hält die Transaktion nicht an, während sie wartet, d. h. bis die erste Zeile erzeugt wird. Dies bedeutet, dass keine anderen Batches innerhalb der gleichen Verbindung ausgeführt werden können, während eine WAITFOR-Anweisung wartet.  
  
### <a name="mars-session-cache"></a>MARS-Sitzungscache  

 Wenn eine Verbindung mit aktiviertem MARS geöffnet wird, wird eine logische Sitzung erstellt, was zusätzlichen Aufwand bedeutet. Um den Mehraufwand zu minimieren und die Leistungsfähigkeit zu erhöhen, führt **SqlClient** eine Zwischenspeicherung der MARS-Sitzung in einer Verbindung durch. Der Cache enthält höchstens 10 MARS-Sitzungen. Dieser Wert kann nicht vom Benutzer angepasst werden. Bei Erreichen des Sitzungslimits wird eine neue Sitzung erstellt, ohne dass ein Fehler ausgegeben wird. Der Cache und die darin enthaltenen Sitzungen sind verbindungsbezogen. Daher werden sie nicht von verschiedenen Verbindungen gemeinsam genutzt. Sobald eine Sitzung freigegeben wird, wird sie an den Pool zurückgegeben, es sei denn, die Obergrenze des Pools ist erreicht. Wenn der Cachepool voll ist, wird die Sitzung geschlossen. MARS-Sitzungen laufen nicht ab. Sie werden lediglich bereinigt, wenn das Verbindungsobjekt verworfen wird. Der MARS-Sitzungscache wird nicht vorab geladen. Er wird geladen, sobald die Anwendung mehr Sitzungen benötigt.  
  
### <a name="thread-safety"></a>Threadsicherheit  

 MARS-Vorgänge sind nicht threadsicher.  
  
### <a name="connection-pooling"></a>Verbindungspooling  

 MARS-fähige Verbindungen lassen sich wie andere Verbindungen in einem Pool zusammenfassen. Wenn eine Anwendung zwei Verbindungen öffnet, eine mit aktiviertem und eine mit deaktiviertem MARS, befinden sich die beiden Verbindungen in getrennten Pools. Weitere Informationen finden Sie unter [SQL Server-Verbindungspooling (ADO.NET)](../sql-server-connection-pooling.md).  
  
### <a name="sql-server-batch-execution-environment"></a>SQL Server-Batchausführungsumgebung  

 Beim Öffnen einer Verbindung wird eine Standardumgebung definiert. Diese Umgebung wird dann in eine logische MARS-Sitzung kopiert.  
  
 Die Batchausführungsumgebung umfasst die folgenden Komponenten:  
  
- SET-Optionen (z. B. ANSI_NULLS, DATE_FORMAT, LANGUAGE und TEXTSIZE)  
  
- Sicherheitskontext (Benutzer/Anwendungsrolle)  
  
- Datenbankkontext (aktuelle Datenbank)  
  
- Ausführungszustandsvariablen (z. B. @@ERROR, @@ROWCOUNT, @@FETCH_STATUS @@IDENTITY)  
  
- Temporäre Tabellen der obersten Ebene  
  
 Bei MARS ist einer Verbindung eine Standardausführungsumgebung zugeordnet. Jeder neue Batch, dessen Ausführung unter einer bestimmten Verbindung gestartet wird, erhält eine Kopie der Standardumgebung. Bei Ausführung von Code in einem bestimmten Batch sind sämtliche an der Umgebung vorgenommenen Änderungen auf diesen speziellen Batch begrenzt. Beim Abschluss der Ausführung werden die Ausführungseinstellungen in die Standardumgebung kopiert. Bei einem einzelnen Batch, der mehrere Befehle enthält, die nacheinander in derselben Transaktion ausgeführt werden sollen, ist die Semantik die gleiche wie bei Verbindungen, die von früheren Clients oder Servern verfügbar gemacht werden.  
  
### <a name="parallel-execution"></a>Parallelausführung  

 MARS ist nicht so konzipiert, dass alle Anforderungen für mehrere Verbindungen in einer Anwendung entfallen. Wenn eine Anwendung eine tatsächliche parallele Ausführung von Befehlen auf einem Server benötigt, müssen mehrere Verbindungen verwendet werden.  
  
 Ein Beispiel: Es werden zwei Befehlsobjekte erstellt: eines zur Verarbeitung eines Resultsets und ein weiteres zur Aktualisierung von Daten. Beide nutzen eine gemeinsame Verbindung über MARS. In diesem Szenario kann `Transaction`.`Commit` erst erfolgreich ausgeführt werden, nachdem alle Ergebnisse des ersten Befehlsobjekts gelesen wurden. Daher wird eine entsprechende Ausnahme ausgelöst:  
  
 Meldung: Der Transaktionskontext wird von einer anderen Sitzung verwendet.  
  
 Quelle: .NET SqlClient-Datenanbieter  
  
 Erwartet: (NULL)  
  
 Empfangen: System.Data.SqlClient.SqlException  
  
 Es gibt zwei Optionen zum Umgang mit diesem Szenario:  
  
1. Starten Sie die Transaktion nach Erstellen des Readers so, dass sie nicht Teil der Transaktion ist. Jede Aktualisierung wird dann eine eigene Transaktion.  
  
2. Committen Sie alle Aufgaben nach Schließen des Readers. Dies birgt das Potenzial für einen beträchtlichen Batch von Aktualisierungen.  
  
3. Verwenden Sie nicht MARS sondern für jedes Befehlsobjekt eine separate Verbindung, so wie Sie es vor MARS getan hätten.  
  
### <a name="detecting-mars-support"></a>Ermitteln der MARS-Unterstützung  

 Eine Anwendung kann auf MARS-Unterstützung prüfen, indem sie den Wert `SqlConnection.ServerVersion` liest. Die Hauptnummer muss 9 für SQL Server 2005 und 10 für SQL Server 2008 lauten.  
  
## <a name="see-also"></a>Weitere Informationen

- [Mehrere aktive Resultsets (MARS)](multiple-active-result-sets-mars.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
