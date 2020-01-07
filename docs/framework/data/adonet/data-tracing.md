---
title: Datenablaufverfolgung in ADO.NET
ms.date: 03/30/2017
ms.assetid: a6a752a5-d2a9-4335-a382-b58690ccb79f
ms.openlocfilehash: be82500920ce9d5f8bc7ee979cf8ec5006f4f12b
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347798"
---
# <a name="data-tracing-in-adonet"></a>Datenablaufverfolgung in ADO.NET

ADO.net bietet integrierte Funktionen für die Datenablauf Verfolgung, die von den .NET-Datenanbietern für SQL Server, Oracle, OLE DB und ODBC sowie die ADO.net-<xref:System.Data.DataSet>und die SQL Server Netzwerkprotokolle unterstützt werden.

Die Ablaufverfolgung von Aufrufen der Datenzugriffs-API kann bei der Diagnose der folgenden Probleme helfen:

- Fehlende Schemaübereinstimmung zwischen Clientprogramm und Datenbank.

- Nicht verfügbare Datenbank oder Probleme mit der Netzwerkbibliothek.

- Fehlerhafte SQL-Anweisungen (sowohl hart codiert als auch von einer Anwendung generiert).

- Fehlerhafte Programmierlogik.

- Probleme, die sich aus der Interaktion mehrerer ADO.NET-Komponenten oder aus der Interaktion zwischen ADO.NET und Ihren eigenen Komponenten ergeben.

Zur Unterstützung verschiedener Ablaufverfolgungstechnologien ist die Ablaufverfolgung erweiterbar, sodass Entwickler eine Ablaufverfolgung für Probleme auf jeder Ebene des Anwendungsstapels ausführen können. Obwohl die Ablaufverfolgung nicht auf ADO.NET beschränkt ist, nutzen Microsoft-Anbieter die Vorteile generalisierter Ablaufverfolgungs- und Instrumentierungs-APIs.

Weitere Informationen zum Festlegen und Konfigurieren der verwalteten Ablauf Verfolgung in ADO.net finden Sie unter [Tracing Data Access](https://docs.microsoft.com/previous-versions/sql/sql-server-2012/hh880086(v=msdn.10)).

## <a name="accessing-diagnostic-information-in-the-extended-events-log"></a>Zugriff auf Diagnoseinformationen im Protokoll für erweiterte Ereignisse

In der .NET Framework Datenanbieter für SQL Server wurde die Datenzugriffs-Ablauf Verfolgung ([Datenzugriffs](https://docs.microsoft.com/previous-versions/sql/sql-server-2012/hh880086(v=msdn.10))-Ablauf Verfolgung) aktualisiert, um das korrelieren von Client Ereignissen mit Diagnoseinformationen (z. b. Verbindungsfehlern) aus dem konnektivitätsringpuffer des Servers und den Informationen zur Anwendungsleistung im Protokoll für erweiterte Ereignisse zu vereinfachen. Informationen dazu, wie Sie das Protokoll für erweiterte Ereignisse lesen, finden Sie unter [View Event Session Data](https://docs.microsoft.com/previous-versions/sql/sql-server-2012/hh710068(v=sql.110)).

Für Verbindungsvorgänge sendet ADO.NET eine Clientverbindungs-ID. Wenn die Verbindung nicht hergestellt werden kann, können Sie auf den konnektivitätsringpuffer zugreifen ([Problembehandlung bei der Konnektivität in SQL Server 2008 mit dem konnektivitätsringpuffer](https://blogs.msdn.microsoft.com/sql_protocols/2008/05/20/connectivity-troubleshooting-in-sql-server-2008-with-the-connectivity-ring-buffer/)) und das `ClientConnectionID` Feld Suchen und Diagnoseinformationen zum Verbindungsfehler abrufen. Clientverbindungs-IDs werden nur im Ringpuffer protokolliert, wenn ein Fehler auftritt. (Wenn eine Verbindung nicht hergestellt werden kann, bevor das Paket für die Vorab Anmeldung gesendet wird, wird keine Clientverbindungs-ID generiert.) Die Clientverbindungs-ID ist eine 16-Byte-GUID. Sie finden die Clientverbindungs-ID auch in der Zielausgabe für erweiterte Ereignisse, wenn die `client_connection_id`-Aktion den Ereignissen in einer Sitzung für erweiterte Ereignisse hinzugefügt wurde. Sie können die Ablaufverfolgung für den Datenzugriff aktivieren, den Verbindungsbefehl erneut ausführen und das `ClientConnectionID`-Feld in der Datenzugriffs-Ablaufverfolgung beobachten, wenn Sie weitere Diagnoseinformationen zum Clienttreiber benötigen.

Sie können die Clientverbindungs-ID programmgesteuert abrufen, indem Sie die `SqlConnection.ClientConnectionID`-Eigenschaft verwenden.

`ClientConnectionID` ist für ein <xref:System.Data.SqlClient.SqlConnection>-Objekt verfügbar, das erfolgreich eine Verbindung herstellt. Wenn ein Verbindungsfehler auftritt, ist `ClientConnectionID` u. U. über `SqlException.ToString` verfügbar.

ADO.NET sendet zudem eine threadspezifische Aktivitäts-ID. Die Aktivitäts-ID wird in den Sitzungen für erweiterte Ereignisse aufgezeichnet, wenn die Sitzungen mit aktivierter TRACK_CAUSALITY Option gestartet werden. Bei Leistungsproblemen mit einer aktiven Verbindung können Sie die Aktivitäts-ID aus der Datenzugriffs-Ablaufverfolgung des Clients (`ActivityID`-Feld) abrufen und die Aktivitäts-ID in der Ausgabe der erweiterten Ereignisse suchen. Die Aktivitäts-ID in erweiterten Ereignissen ist eine 16-Byte-GUID (entspricht nicht der GUID für die Clientverbindungs-ID), an die eine 4-Byte-Sequenznummer angehängt ist. Die Sequenznummer stellt die Reihenfolge einer Anforderung innerhalb eines Threads dar und gibt die relative Reihenfolge der Batch- und RPC-Anweisungen für den Thread an. `ActivityID` wird derzeit optional für SQL-Batchanweisungen und RPC-Anforderungen gesendet, wenn die Ablaufverfolgung für den Datenzugriff aktiviert ist und das 18. Bit im Konfigurationswort der Datenzugriffs-Ablaufverfolgung ON lautet.

Im folgenden Beispiel wird Transact-SQL verwendet, um eine Sitzung für erweiterte Ereignisse zu starten, die in einem Ringpuffer gespeichert wird, und die von einem Client in RPC-und Batch-Vorgängen gesendete Aktivitäts-ID aufzeichnen.

```sql
create event session MySession on server
add event connectivity_ring_buffer_recorded,
add event sql_statement_starting (action (client_connection_id)),
add event sql_statement_completed (action (client_connection_id)),
add event rpc_starting (action (client_connection_id)),
add event rpc_completed (action (client_connection_id))
add target ring_buffer with (track_causality=on)
```

## <a name="see-also"></a>Siehe auch

- [Netzwerkablaufverfolgung in .NET Framework](../../network-programming/network-tracing.md)
- [Ablaufverfolgung und Instrumentieren von Anwendungen](../../debug-trace-profile/tracing-and-instrumenting-applications.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
