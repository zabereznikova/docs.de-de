---
title: Datenablaufverfolgung in ADO.NET
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a6a752a5-d2a9-4335-a382-b58690ccb79f
caps.latest.revision: 9
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 377c69feda356aee9e11720cf12c9c97158d45a7
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="data-tracing-in-adonet"></a>Datenablaufverfolgung in ADO.NET
ADO.NET bietet integrierte Datenablaufverfolgungsfunktionen, die von den .NET-Datenanbietern für SQL Server, Oracle, OLE DB und ODBC sowie ADO.NET unterstützt wird <xref:System.Data.DataSet>, und die SQL Server-Netzwerkprotokolle.  
  
 Die Ablaufverfolgung von Aufrufen der Datenzugriffs-API kann bei der Diagnose der folgenden Probleme helfen:  
  
-   Fehlende Schemaübereinstimmung zwischen Clientprogramm und Datenbank.  
  
-   Nicht verfügbare Datenbank oder Probleme mit der Netzwerkbibliothek.  
  
-   Fehlerhafte SQL-Anweisungen (sowohl hart codiert als auch von einer Anwendung generiert).  
  
-   Fehlerhafte Programmierlogik.  
  
-   Probleme, die sich aus der Interaktion mehrerer ADO.NET-Komponenten oder aus der Interaktion zwischen ADO.NET und Ihren eigenen Komponenten ergeben.  
  
 Zur Unterstützung verschiedener Ablaufverfolgungstechnologien ist die Ablaufverfolgung erweiterbar, sodass Entwickler eine Ablaufverfolgung für Probleme auf jeder Ebene des Anwendungsstapels ausführen können. Obwohl die Ablaufverfolgung nicht auf ADO.NET beschränkt ist, nutzen Microsoft-Anbieter die Vorteile generalisierter Ablaufverfolgungs- und Instrumentierungs-APIs.  
  
 Weitere Informationen zum Festlegen und Konfigurieren der verwalteten Ablaufverfolgung in ADO.NET finden Sie unter [Tracing Data Access](http://msdn.microsoft.com/library/hh880086.aspx).  
  
## <a name="accessing-diagnostic-information-in-the-extended-events-log"></a>Zugriff auf Diagnoseinformationen im Protokoll für erweiterte Ereignisse  
 In der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datenanbieter für SQL Server, Datenzugriff tracing ([Datenzugriffsablaufverfolgung](http://msdn.microsoft.com/library/hh880086.aspx)) wurde aktualisiert, um einfacher mit Diagnoseinformationen, z. B. Verbindungsfehlern, aus korreliert erleichtern die Serverzertifikat konnektivitätsringpuffer und den anwendungsbezogenen Leistungsinformationen in das Protokoll für erweiterte Ereignisse. Informationen zum Auswerten der erweiterten Ereignisprotokolle finden Sie unter [View Event Session Data](http://msdn.microsoft.com/library/hh710068\(SQL.110\).aspx).  
  
 Für Verbindungsvorgänge sendet ADO.NET eine Clientverbindungs-ID. Wenn die Verbindung fehlschlägt, können Sie dem konnektivitätsringpuffer zugreifen ([Connectivity troubleshooting in SQL Server 2008 with the Connectivity Ring Buffer](http://go.microsoft.com/fwlink/?LinkId=207752)) und suchen Sie nach der `ClientConnectionID` Feld und Abrufen von Diagnoseinformationen über die Verbindungsfehler. Clientverbindungs-IDs werden nur im Ringpuffer protokolliert, wenn ein Fehler auftritt. (Wenn eine Verbindung fehlschlägt, bevor das Voranmeldungspaket gesendet wird, wird keine Clientverbindungs-ID generiert). Die Clientverbindungs-ID ist eine 16-Byte-GUID. Sie finden die Clientverbindungs-ID auch in der Zielausgabe für erweiterte Ereignisse, wenn die `client_connection_id`-Aktion den Ereignissen in einer Sitzung für erweiterte Ereignisse hinzugefügt wurde. Sie können die Ablaufverfolgung für den Datenzugriff aktivieren, den Verbindungsbefehl erneut ausführen und das `ClientConnectionID`-Feld in der Datenzugriffs-Ablaufverfolgung beobachten, wenn Sie weitere Diagnoseinformationen zum Clienttreiber benötigen.  
  
 Sie können die Clientverbindungs-ID programmgesteuert abrufen, indem Sie die `SqlConnection.ClientConnectionID`-Eigenschaft verwenden.  
  
 `ClientConnectionID` ist für ein <xref:System.Data.SqlClient.SqlConnection>-Objekt verfügbar, das erfolgreich eine Verbindung herstellt. Wenn ein Verbindungsfehler auftritt, ist `ClientConnectionID` u. U. über `SqlException.ToString` verfügbar.  
  
 ADO.NET sendet zudem eine threadspezifische Aktivitäts-ID. Die Aktivitäts-ID wird in Sitzungen für erweiterte Ereignisse aufgezeichnet, wenn die Sitzungen mit aktivierter TRACK_CAUSAILITY-Option gestartet werden. Bei Leistungsproblemen mit einer aktiven Verbindung können Sie die Aktivitäts-ID aus der Datenzugriffs-Ablaufverfolgung des Clients (`ActivityID`-Feld) abrufen und die Aktivitäts-ID in der Ausgabe der erweiterten Ereignisse suchen. Die Aktivitäts-ID in den erweiterten Ereignissen ist eine 16-Byte-GUID (nicht identisch mit der GUID für die Clientverbindungs-ID), an die eine 4-Byte-Sequenznummer angefügt wurde. Die Sequenznummer stellt die Reihenfolge einer Anforderung innerhalb eines Threads dar und gibt die relative Reihenfolge der Batch- und RPC-Anweisungen für den Thread an. `ActivityID` wird derzeit optional für SQL-Batchanweisungen und RPC-Anforderungen gesendet, wenn die Ablaufverfolgung für den Datenzugriff aktiviert ist und das 18. Bit im Konfigurationswort der Datenzugriffs-Ablaufverfolgung ON lautet.  
  
 Im folgenden Beispiel wird [!INCLUDE[tsql](../../../../includes/tsql-md.md)] verwendet, um eine Sitzung für erweiterte Ereignisse zu starten, die in einem Ringpuffer gespeichert wird und die von einem Client für RPC- und Batchvorgänge gesendete Aktivitäts-ID aufzeichnet.  
  
```  
create event session MySession on server   
add event connectivity_ring_buffer_recorded,   
add event sql_statement_starting (action (client_connection_id)),   
add event sql_statement_completed (action (client_connection_id)),   
add event rpc_starting (action (client_connection_id)),   
add event rpc_completed (action (client_connection_id))  
add target ring_buffer with (track_causality=on)  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Netzwerkablaufverfolgung in .NET Framework](../../../../docs/framework/network-programming/network-tracing.md)  
 [Ablaufverfolgung und Instrumentieren von Anwendungen](../../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
