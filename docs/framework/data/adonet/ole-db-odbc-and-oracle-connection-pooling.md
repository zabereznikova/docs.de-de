---
title: OLE DB-, ODBC- und Oracle-Verbindungspooling
ms.date: 03/30/2017
ms.assetid: 2bd83b1e-3ea9-43c4-bade-d9cdb9bbbb04
ms.openlocfilehash: 7552f4a95af51774071f0a4017637570d648dd86
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929254"
---
# <a name="ole-db-odbc-and-oracle-connection-pooling"></a>OLE DB-, ODBC- und Oracle-Verbindungspooling
Durch Verbindungspooling kann die Leistung und Skalierbarkeit einer Anwendung wesentlich erhöht werden. In diesem Abschnitt wird das Verbindungspooling für die .NET Framework-Datenanbieter für OLE DB, ODBC und Oracle erläutert.  
  
## <a name="connection-pooling-for-oledb"></a>Verbindungspooling für OLE DB  
 Der .NET Framework-Datenanbieter für OLE DB vereinigt automatisch Verbindungen mithilfe des OLE DB-Sitzungspoolings. Mithilfe von Argumenten für Verbindungszeichenfolgen können OLE DB-Dienste, einschließlich Pooling, aktiviert und deaktiviert werden. Beispielsweise werden mit der folgenden Verbindungszeichenfolge das OLE DB-Sitzungspooling und die automatische Eintragung von Transaktionen deaktiviert.  
  
```  
Provider=SQLOLEDB;OLE DB Services=-4;Data Source=localhost;Integrated Security=SSPI;  
```  
  
 Es wird empfohlen, nach Abschluss der Verwendung einer Verbindung diese immer zu schließen oder zu verwerfen, um die Verbindung an den Pool zurückzugeben. Verbindungen, die nicht explizit geschlossen werden, werden möglicherweise nicht an den Pool zurückgegeben. Beispielsweise wird eine Verbindung, die sich nicht mehr im Gültigkeitsbereich befindet, aber nicht explizit geschlossen wurde, nur dann an den Verbindungspool zurückgegeben, wenn die maximale Poolgröße erreicht wurde und die Verbindung immer noch gültig ist.  
  
 Weitere Informationen zum OLE DB-Sitzungs-oder Ressourcen Pooling sowie zum Deaktivieren des Poolings durch Überschreiben der Standardwerte für den OLE DB Anbieter Dienst finden Sie im [OLE DB Programmer es Guide](https://go.microsoft.com/fwlink/?linkid=45232).  
  
## <a name="connection-pooling-for-odbc"></a>Verbindungspooling für ODBC  
 Das Verbindungspooling für .NET Framework-Datenanbieter für ODBC wird von dem für die Verbindung verwendeten ODBC-Treiber-Manager verwaltet und wird nicht vom .NET Framework-Datenanbieter für ODBC beeinflusst.  
  
 Um das Verbindungspooling zu aktivieren oder zu deaktivieren, öffnen Sie in der Systemsteuerung im Ordnerverwaltung den **ODBC-Datenquellen-Administrator** . Auf der Registerkarte **Verbindungspooling** können Sie Verbindungspooling-Parameter für jeden installierten ODBC-Treiber angeben. Beachten Sie, dass im Fall von Verbindungspoolingänderungen für einen bestimmten ODBC-Treiber alle Anwendungen betroffen sind, die diesen ODBC-Treiber verwenden.  
  
## <a name="connection-pooling-for-oracleclient"></a>Verbindungspooling für OracleClient  
 Der .NET Framework-Datenanbieter für Oracle stellt das Verbindungspooling für die ADO.NET-Clientanwendung automatisch bereit. Sie können auch mehrere Modifizierer für Verbindungszeichenfolgen angeben, um das Verbindungspoolingverhalten zu steuern (siehe "Steuern von Verbindungspooling mit Verbindungszeichenfolgen-Schlüsselwörtern" weiter unten in diesem Thema).  
  
### <a name="pool-creation-and-assignment"></a>Erstellen und Zuweisen von Pools  
 Wenn eine Verbindung hergestellt wird, wird ein Verbindungspool basierend auf einem exakt übereinstimmenden Algorithmus erstellt. Damit wird der Pool der Verbindungszeichenfolge in der Verbindung zugewiesen. Jedem Verbindungspool wird eine eindeutige Verbindungszeichenfolge zugeordnet. Wenn beim Öffnen einer neuen Verbindung die Verbindungszeichenfolge nicht genau mit einem vorhanden Pool übereinstimmt, wird ein neuer Pool erstellt.  
  
 Erstellte Verbindungspools werden erst zerstört, wenn der aktive Prozess beendet wird. Das Beibehalten inaktiver oder leerer Pools verbraucht nur geringe Systemressourcen.  
  
### <a name="connection-addition"></a>Hinzufügen einer Verbindung  
 Für jede eindeutige Verbindungszeichenfolge wird ein Verbindungspool erstellt. Wenn ein Pool erstellt wird, werden mehrere Verbindungsobjekte erstellt und dem Pool hinzugefügt wird, sodass die minimalen Anforderungen für die Größe eines Pools erfüllt sind. Verbindungen werden dem Pool nach Bedarf hinzugefügt, bis die maximale Poolgröße erreicht ist.  
  
 Wenn ein <xref:System.Data.OracleClient.OracleConnection>-Objekt angefordert wird, wird es aus dem Pool abgerufen, wenn eine verwendbare Verbindung verfügbar ist. Eine Verbindung ist dann verwendbar, wenn sie aktuell nicht verwendet wird, einen übereinstimmenden Transaktionskontext aufweist oder keinem Transaktionskontext zugeordnet ist sowie über eine gültige Verknüpfung zum Server verfügt.  
  
 Wenn die maximale Poolgröße erreicht ist und keine verwendbare Verbindung verfügbar ist, wird die Anforderung in die Warteschlange gestellt. Die Verbindungspoolfunktion erfüllt diese Anforderungen, indem Verbindungen erneut zugewiesen werden, sobald sie wieder für den Pool freigegeben werden. Verbindungen werden wieder für den Pool freigegeben, wenn sie geschlossen oder verworfen werden.  
  
### <a name="connection-removal"></a>Entfernen von Verbindungen  
 Die Verbindungspoolfunktion entfernt eine Verbindung aus dem Pool, nachdem sie für eine längere Zeitspanne nicht verwendet wurde oder wenn festgestellt wird, dass die Verbindung mit dem Server unterbrochen wurde. Beachten Sie, dass dies nur durch den Versuch, mit dem Server zu kommunizieren, festgestellt werden kann. Wenn eine Verbindung gefunden wird, die nicht mehr mit dem Server verbunden ist, wird sie als ungültig markiert. Die Verbindungspoolfunktion durchsucht Verbindungspools in regelmäßigen Abständen nach Objekten, die dem Pool übergeben wurden und als ungültig markiert sind. Diese Verbindungen werden dann endgültig entfernt.  
  
 Wenn eine Verbindung zu einem nicht mehr vorhandenen Server besteht, kann diese Verbindung auch ohne dass die Verbindungspoolfunktion die unterbrochene Verbindung gefunden und als ungültig markiert hat aus dem Pool genommen werden. In diesem Fall wird eine Ausnahme ausgelöst. Sie müssen die Verbindung dennoch trennen, um sie an den Pool zurückzugeben.  
  
 Rufen Sie nicht `Close` oder `Dispose` für eine `Connection`, einen `DataReader` oder ein anderes verwaltetes Objekt in der `Finalize`-Methode der Klasse auf. Geben Sie in einer Finalize-Methode nur nicht verwaltete Ressourcen frei, die der Klasse direkt gehören. Wenn die Klasse keine nicht verwalteten Ressourcen besitzt, definieren Sie in der Klasse keine `Finalize`-Methode. Weitere Informationen finden Sie unter [Garbage Collection](../../../standard/garbage-collection/index.md).  
  
### <a name="transaction-support"></a>Transaktionsunterstützung  
 Verbindungen werden aus dem Pool entnommen und basierend auf dem Transaktionskontext zugewiesen. Der Kontext des anfordernden Threads und der zugewiesenen Verbindung müssen übereinstimmen. Daher wird jeder Verbindungspool tatsächlich in Verbindungen unterteilt, denen kein Transaktionskontext zugeordnet ist, und in *N* Unterteilungen, die jeweils Verbindungen mit einem bestimmten Transaktionskontext enthalten.  
  
 Wenn eine Verbindung geschlossen wird, wird sie an den Pool und an den entsprechenden Teilbereich auf der Grundlage des Transaktionskontexts zurückgegeben. Sie können die Verbindung daher trennen, ohne einen Fehler zu generieren, auch wenn eine verteilte Transaktion noch aussteht. So haben Sie die Möglichkeit, die verteilte Transaktion zu einem späteren Zeitpunkt durchzuführen oder abzubrechen.  
  
### <a name="controlling-connection-pooling-with-connection-string-keywords"></a>Steuern von Verbindungspooling mit Verbindungszeichenfolgen-Schlüsselwörtern  
 Die <xref:System.Data.OracleClient.OracleConnection.ConnectionString%2A>-Eigenschaft des <xref:System.Data.OracleClient.OracleConnection>-Objekts unterstützt Schlüssel-Wert-Paare für Verbindungszeichenfolgen, mit denen das Verhalten der Verbindungspoolinglogik angepasst werden kann.  
  
 In der folgenden Tabelle werden die <xref:System.Data.OracleClient.OracleConnection.ConnectionString%2A>-Werte beschrieben, die zum Anpassen des Verbindungspoolingverhaltens verwendet werden können.  
  
|Name|Default|Beschreibung|  
|----------|-------------|-----------------|  
|`Connection Lifetime`|0|Wenn eine Verbindung an den Pool zurückgegeben wird, wird die Erstellungszeit mit der aktuellen Zeit verglichen. Wenn diese Zeitspanne (in Sekunden) größer ist als der für die `Connection Lifetime` angegebene Wert, wird die Verbindung zerstört. Dies ist hilfreich bei Gruppenkonfigurationen, um einen Lastenausgleich zwischen einem bereits aktiven Server und einem Server zu erzwingen, der gerade erst online gegangen ist.<br /><br /> Der Wert 0 (null) bewirkt, dass an den Pool zurückgegebene Verbindungen den maximalen Timeout besitzen.|  
|`Enlist`|"true"|Im Falle von `true` wird die Verbindung automatisch von der Poolfunktion im aktuellen Transaktionskontext des Erstellungsthreads aufgelistet, wenn ein Transaktionskontext vorhanden ist.|  
|`Max Pool Size`|100|Die maximale Anzahl der im Pool zulässigen Verbindungen.|  
|`Min Pool Size`|0|Die minimale Anzahl der im Pool beibehaltenen Verbindungen.|  
|`Pooling`|"true"|Im Falle von `true` wird die Verbindung aus dem entsprechenden Pool entnommen oder bei Bedarf erstellt und dem entsprechenden Pool hinzugefügt.|  
  
## <a name="see-also"></a>Siehe auch

- [Verbindungspooling](../../../../docs/framework/data/adonet/connection-pooling.md)
- [Leistungsindikatoren](../../../../docs/framework/data/adonet/performance-counters.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
