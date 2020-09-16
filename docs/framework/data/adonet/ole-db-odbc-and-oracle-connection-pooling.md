---
title: OLE DB-, ODBC- und Oracle-Verbindungspooling
ms.date: 03/30/2017
ms.assetid: 2bd83b1e-3ea9-43c4-bade-d9cdb9bbbb04
ms.openlocfilehash: c19f341d869ee983531fa5c90c0d7c94978dadb1
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90535370"
---
# <a name="ole-db-odbc-and-oracle-connection-pooling"></a>OLE DB-, ODBC-und Oracle-Verbindungspooling

Durch Verbindungspooling kann die Leistung und Skalierbarkeit einer Anwendung wesentlich erhöht werden. In diesem Abschnitt wird das Verbindungspooling für die .NET Framework-Datenanbieter für OLE DB, ODBC und Oracle erläutert.

## <a name="oledb"></a>OLEDB

Der .NET Framework-Datenanbieter für OLE DB vereinigt automatisch Verbindungen mithilfe des OLE DB-Sitzungspoolings. Mithilfe von Argumenten für Verbindungszeichenfolgen können OLE DB-Dienste, einschließlich Pooling, aktiviert und deaktiviert werden. Beispielsweise werden mit der folgenden Verbindungszeichenfolge das OLE DB-Sitzungspooling und die automatische Eintragung von Transaktionen deaktiviert.

```csharp
Provider=SQLOLEDB;OLE DB Services=-4;Data Source=localhost;Integrated Security=SSPI;
```

 Es wird empfohlen, nach Abschluss der Verwendung einer Verbindung diese immer zu schließen oder zu verwerfen, um die Verbindung an den Pool zurückzugeben. Verbindungen, die nicht explizit geschlossen werden, werden möglicherweise nicht an den Pool zurückgegeben. Beispielsweise wird eine Verbindung, die sich nicht mehr im Gültigkeitsbereich befindet, aber nicht explizit geschlossen wurde, nur dann an den Verbindungspool zurückgegeben, wenn die maximale Poolgröße erreicht wurde und die Verbindung immer noch gültig ist.

 Weitere Informationen zum OLE DB-Sitzungs-oder Ressourcen Pooling sowie zum Deaktivieren des Poolings durch Überschreiben der Standardwerte für den OLE DB Anbieter Dienst finden Sie im [OLE DB Programmer es Guide](/previous-versions/windows/desktop/ms713643(v=vs.85)).

## <a name="odbc"></a>ODBC
 Das Verbindungspooling für .NET Framework-Datenanbieter für ODBC wird von dem für die Verbindung verwendeten ODBC-Treiber-Manager verwaltet und wird nicht vom .NET Framework-Datenanbieter für ODBC beeinflusst.

 Um das Verbindungspooling zu aktivieren oder zu deaktivieren, öffnen Sie in der Systemsteuerung im Ordnerverwaltung den **ODBC-Datenquellen-Administrator** . Auf der Registerkarte **Verbindungspooling** können Sie Verbindungspooling-Parameter für jeden installierten ODBC-Treiber angeben. Verbindungspooling-Änderungen für einen bestimmten ODBC-Treiber wirken sich auf alle Anwendungen aus, die diesen ODBC-Treiber verwenden.

## <a name="oracleclient"></a>OracleClient
 Der .NET Framework-Datenanbieter für Oracle stellt das Verbindungspooling für die ADO.NET-Clientanwendung automatisch bereit. Sie können auch mehrere Modifizierer für Verbindungszeichenfolgen angeben, um das Verbindungspoolingverhalten zu steuern (siehe "Steuern von Verbindungspooling mit Verbindungszeichenfolgen-Schlüsselwörtern" weiter unten in diesem Thema).

### <a name="create-and-assign-pools"></a>Erstellen und Zuweisen von Pools
 Wenn eine Verbindung hergestellt wird, wird ein Verbindungspool basierend auf einem exakt übereinstimmenden Algorithmus erstellt. Damit wird der Pool der Verbindungszeichenfolge in der Verbindung zugewiesen. Jedem Verbindungspool wird eine eindeutige Verbindungszeichenfolge zugeordnet. Wenn beim Öffnen einer neuen Verbindung die Verbindungszeichenfolge nicht genau mit einem vorhanden Pool übereinstimmt, wird ein neuer Pool erstellt.

 Erstellte Verbindungspools werden erst zerstört, wenn der aktive Prozess beendet wird. Das Beibehalten inaktiver oder leerer Pools verbraucht nur geringe Systemressourcen.

### <a name="connection-addition"></a>Hinzufügen einer Verbindung
 Für jede eindeutige Verbindungszeichenfolge wird ein Verbindungspool erstellt. Wenn ein Pool erstellt wird, werden mehrere Verbindungsobjekte erstellt und dem Pool hinzugefügt wird, sodass die minimalen Anforderungen für die Größe eines Pools erfüllt sind. Verbindungen werden dem Pool nach Bedarf hinzugefügt, bis die maximale Poolgröße erreicht ist.

 Wenn ein <xref:System.Data.OracleClient.OracleConnection>-Objekt angefordert wird, wird es aus dem Pool abgerufen, wenn eine verwendbare Verbindung verfügbar ist. Eine Verbindung ist dann verwendbar, wenn sie aktuell nicht verwendet wird, einen übereinstimmenden Transaktionskontext aufweist oder keinem Transaktionskontext zugeordnet ist sowie über eine gültige Verknüpfung zum Server verfügt.

 Wenn die maximale Poolgröße erreicht ist und keine verwendbare Verbindung verfügbar ist, wird die Anforderung in die Warteschlange gestellt. Die Verbindungspoolfunktion erfüllt diese Anforderungen, indem Verbindungen erneut zugewiesen werden, sobald sie wieder für den Pool freigegeben werden. Verbindungen werden wieder für den Pool freigegeben, wenn sie geschlossen oder verworfen werden.

### <a name="connection-removal"></a>Entfernen von Verbindungen
 Der Verbindungspool entfernt eine Verbindung aus dem Pool, nachdem Sie sich für einen längeren Zeitraum im Leerlauf befunden hat, oder wenn der Pool Funktion feststellt, dass die Verbindung mit dem Server unterbrochen wurde. Dies kann nur erkannt werden, nachdem versucht wurde, mit dem Server zu kommunizieren. Wenn eine Verbindung gefunden wird, die nicht mehr mit dem Server verbunden ist, wird sie als ungültig markiert. Die Verbindungspoolfunktion durchsucht Verbindungspools in regelmäßigen Abständen nach Objekten, die dem Pool übergeben wurden und als ungültig markiert sind. Diese Verbindungen werden dann endgültig entfernt.

 Wenn eine Verbindung zu einem nicht mehr vorhandenen Server besteht, kann diese Verbindung auch ohne dass die Verbindungspoolfunktion die unterbrochene Verbindung gefunden und als ungültig markiert hat aus dem Pool genommen werden. In diesem Fall wird eine Ausnahme ausgelöst. Sie müssen die Verbindung dennoch trennen, um sie an den Pool zurückzugeben.

 Rufen Sie nicht `Close` oder `Dispose` für eine `Connection`, einen `DataReader` oder ein anderes verwaltetes Objekt in der `Finalize`-Methode der Klasse auf. Geben Sie in einer Finalize-Methode nur nicht verwaltete Ressourcen frei, die der Klasse direkt gehören. Wenn die Klasse keine nicht verwalteten Ressourcen besitzt, definieren Sie in der Klasse keine `Finalize`-Methode. Weitere Informationen finden Sie unter [Garbage Collection](../../../standard/garbage-collection/index.md).

### <a name="transaction-support"></a>Transaktionsunterstützung
 Verbindungen werden aus dem Pool entnommen und basierend auf dem Transaktionskontext zugewiesen. Der Kontext des anfordernden Threads und der zugewiesenen Verbindung müssen übereinstimmen. Daher wird jeder Verbindungspool in Verbindungen ohne zugeordneten Transaktionskontext und in *N* untergeordnete Bereiche unterteilt, die jeweils Verbindungen mit einem bestimmten Transaktionskontext enthalten.

 Wenn eine Verbindung geschlossen wird, wird sie an den Pool und an den entsprechenden Teilbereich auf der Grundlage des Transaktionskontexts zurückgegeben. Sie können die Verbindung daher trennen, ohne einen Fehler zu generieren, auch wenn eine verteilte Transaktion noch aussteht. So haben Sie die Möglichkeit, die verteilte Transaktion zu einem späteren Zeitpunkt durchzuführen oder abzubrechen.

### <a name="control-connection-pooling-with-connection-string-keywords"></a>Steuern von Verbindungs Pooling mit Verbindungs Zeichenfolgen-Schlüsselwörtern
 Die <xref:System.Data.OracleClient.OracleConnection.ConnectionString%2A>-Eigenschaft des <xref:System.Data.OracleClient.OracleConnection>-Objekts unterstützt Schlüssel-Wert-Paare für Verbindungszeichenfolgen, mit denen das Verhalten der Verbindungspoolinglogik angepasst werden kann.

 In der folgenden Tabelle werden die <xref:System.Data.OracleClient.OracleConnection.ConnectionString%2A>-Werte beschrieben, die zum Anpassen des Verbindungspoolingverhaltens verwendet werden können.

|Name|Standard|BESCHREIBUNG|
|----------|-------------|-----------------|
|`Connection Lifetime`|0|Wenn eine Verbindung an den Pool zurückgegeben wird, wird die Erstellungszeit mit der aktuellen Zeit verglichen. Wenn diese Zeitspanne (in Sekunden) größer ist als der für die `Connection Lifetime` angegebene Wert, wird die Verbindung zerstört. Dies ist hilfreich bei Gruppenkonfigurationen, um einen Lastenausgleich zwischen einem bereits aktiven Server und einem Server zu erzwingen, der gerade erst online gegangen ist.<br /><br /> Der Wert 0 (null) bewirkt, dass an den Pool zurückgegebene Verbindungen den maximalen Timeout besitzen.|
|`Enlist`|"true"|Im Falle von `true` wird die Verbindung automatisch von der Poolfunktion im aktuellen Transaktionskontext des Erstellungsthreads aufgelistet, wenn ein Transaktionskontext vorhanden ist.|
|`Max Pool Size`|100|Die maximale Anzahl der im Pool zulässigen Verbindungen.|
|`Min Pool Size`|0|Die minimale Anzahl der im Pool beibehaltenen Verbindungen.|
|`Pooling`|"true"|Im Falle von `true` wird die Verbindung aus dem entsprechenden Pool entnommen oder bei Bedarf erstellt und dem entsprechenden Pool hinzugefügt.|

## <a name="see-also"></a>Siehe auch

- [Verbindungspooling](connection-pooling.md)
- [Leistungsindikatoren](performance-counters.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
