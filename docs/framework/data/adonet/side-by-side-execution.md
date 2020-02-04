---
title: Parallele Ausführung
ms.date: 03/30/2017
ms.assetid: 9f9ba96d-9f89-4f65-bb2f-6860879f4393
ms.openlocfilehash: a624aac2ed1f3ab124973c84bc74e39297600c8b
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980014"
---
# <a name="side-by-side-execution-in-adonet"></a>Parallele Ausführung in ADO.NET
Die parallele Ausführung in der .NET Framework ist die Möglichkeit, eine Anwendung auf einem Computer auszuführen, auf dem mehrere Versionen des .NET Framework installiert sind, wobei exklusiv die Version verwendet wird, für die die Anwendung kompiliert wurde. Ausführliche Informationen zum Konfigurieren der parallelen Ausführung finden Sie unter parallele [Ausführung](../../deployment/side-by-side-execution.md).  
  
 Eine Anwendung, die mit einer Version des .NET Framework kompiliert wurde, kann in einer anderen Version der .NET Framework ausgeführt werden. Es wird jedoch empfohlen, eine Version der Anwendung für jede installierte Version des .NET Framework zu kompilieren und separat auszuführen. In beiden Szenarien sollten Sie die Änderungen in ADO.net zwischen Releases beachten, die sich auf die Vorwärtskompatibilität oder die Abwärtskompatibilität Ihrer Anwendung auswirken können.  
  
## <a name="forward-compatibility-and-backward-compatibility"></a>Aufwärts- und Abwärtskompatibilität  
 Vorwärtskompatibilität bedeutet, dass eine Anwendung mit einer früheren Version des .NET Framework kompiliert werden kann, jedoch in einer späteren Version des .NET Framework weiterhin erfolgreich ausgeführt werden kann. ADO.NET-Code, der für die .NET Framework Version 1,1 geschrieben wurde, ist vorwärts kompatibel mit neueren Versionen.  
  
 Abwärtskompatibilität bedeutet, dass eine Anwendung für eine neuere Version des .NET Framework kompiliert wird, aber weiterhin in früheren Versionen der .NET Framework ausgeführt wird, ohne dass die Funktionalität verloren geht. Dies ist natürlich nicht der Fall bei Features, die in einer neuen Version der .NET Framework eingeführt werden.  
  
## <a name="the-net-framework-data-provider-for-odbc"></a>Der .NET Framework-Datenanbieter für ODBC  
 Ab Version 1,1 ist die .NET Framework Datenanbieter für ODBC (<xref:System.Data.Odbc>) als Teil der .NET Framework enthalten.
  
 Wenn Sie über eine Anwendung verfügen, die für die .NET Framework Version 1,0 entwickelt wurde, die den ODBC-Datenanbieter verwendet, um eine Verbindung mit der Datenquelle herzustellen, und Sie diese Anwendung auf der .NET Framework Version 1,1 oder höher ausführen möchten, müssen Sie den Namespace für den ODBC-Datenanbieter auf **System. Data. ODBC**aktualisieren. Sie müssen diese dann für die neuere Version des .NET Framework neu kompilieren.  
  
 Wenn Sie über eine Anwendung verfügen, die für die .NET Framework Version 2,0 oder höher entwickelt wurde, die den ODBC-Datenanbieter verwendet, um eine Verbindung mit Ihrer Datenquelle herzustellen, und Sie diese Anwendung auf der .NET Framework Version 1,0 ausführen möchten, müssen Sie den ODBC-Datenanbieter herunterladen und installieren. auf dem .NET Framework-System, Version 1,0. Anschließend müssen Sie den Namespace für den ODBC-Datenanbieter in **Microsoft. Data. ODBC**ändern und die Anwendung für den .NET Framework, Version 1,0, neu kompilieren.  
  
## <a name="the-net-framework-data-provider-for-oracle"></a>Der .NET Framework-Datenanbieter für Oracle  
 Ab Version 1,1 ist die .NET Framework Datenanbieter für Oracle (<xref:System.Data.OracleClient>) als Teil der .NET Framework enthalten.
  
 Wenn Sie über eine Anwendung verfügen, die für die .NET Framework Version 2,0 oder höher entwickelt wurde, die den Datenanbieter verwendet, um eine Verbindung mit der Datenquelle herzustellen, und Sie diese Anwendung auf der .NET Framework-Version 1,0 ausführen möchten, müssen Sie den Datenanbieter herunterladen und auf der Datei ". ne" installieren. T Framework, Version 1,0, System.  
  
## <a name="code-access-security"></a>Codezugriffssicherheit  
 Die .NET Framework-Datenanbieter in der .NET Framework Version 1,0 (<xref:System.Data.SqlClient>, <xref:System.Data.OleDb>) müssen mit der FullTrust-Berechtigung ausgeführt werden. Bei jedem Versuch, die .NET Framework k-Datenanbieter aus der .NET Framework Version 1,0 in einer Zone mit der Berechtigung "weniger als FullTrust" zu verwenden, wird ein <xref:System.Security.SecurityException>ausgelöst.  
  
 Ab der .NET Framework Version 2,0 können alle .NET Framework Datenanbieter jedoch in teilweise vertrauenswürdigen Zonen verwendet werden. Außerdem wurde ein neues Sicherheits Feature zu den .NET Framework-Datenanbietern in der .NET Framework-Version 1,1 hinzugefügt. Mithilfe dieser Funktion können Sie die Verbindungszeichenfolgen einschränken, die in einer bestimmten Sicherheitszone verwendet werden dürfen. Es kann auch die Verwendung leerer Kennwörter für eine bestimmte Sicherheitszone deaktiviert werden. Weitere Informationen finden Sie unter [Code Access Security and ADO.NET](code-access-security.md).  
  
 Da jede Installation des .NET Framework über eine separate Security. config-Datei verfügt, gibt es keine Kompatibilitätsprobleme mit Sicherheitseinstellungen. Wenn Ihre Anwendung jedoch von den zusätzlichen Sicherheitsfunktionen von ADO.net abhängig ist, die in der .NET Framework Version 1,1 und höher enthalten sind, können Sie Sie nicht an ein System der Version 1,0 verteilen.  
  
## <a name="sqlcommand-execution"></a>"SqlCommand"-Ausführung  
 Beginnend mit der .NET Framework Version 1,1 wurde die Methode, mit der <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> Befehle an der Datenquelle ausführt, geändert.  
  
 In der .NET Framework Version 1,0 hat <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> alle Befehle im Kontext der gespeicherten Prozedur **sp_executesql** ausgeführt. Dadurch gelten Befehle, die den Zustand der Verbindung betreffen (z. B. SET NOCOUNT ON), nur für die Ausführung des aktuellen Befehls. Der Zustand der Verbindung wird bei offener Verbindung für keinen der nachfolgenden ausgeführten Befehle verändert.  
  
 In der .NET Framework Version 1,1 und höher führt <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> nur einen Befehl im Kontext der gespeicherten Prozedur **sp_executesql** aus, wenn der Befehl Parameter enthält, was einen Leistungsvorteil bietet. Dadurch verändern Befehle, die den Zustand der Verbindung betreffen und die zu einem Befehl ohne Parameter gehören, den Zustand der Verbindung für alle nachfolgenden, bei offener Verbindung ausgeführten Befehle.  
  
 Betrachten Sie den folgenden Batch von Befehlen, die in einem Aufruf an <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> ausgeführt werden.  
  
```sql
SET NOCOUNT ON;  
SELECT * FROM dbo.Customers;  
```  
  
 In der .NET Framework Version 1,1 und höher verbleibt NOCOUNT für alle nachfolgenden Befehle, die ausgeführt werden, während die Verbindung geöffnet ist. In der .NET Framework Version 1,0 ist NOCOUNT nur für die aktuelle Befehlsausführung auf on.  
  
 Diese Änderung kann sowohl die vorwärts-als auch die Abwärtskompatibilität Ihrer Anwendung beeinträchtigen, wenn Sie vom Verhalten der <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> für eine der .NET Framework Versionen abhängig sind.  
  
 Bei Anwendungen, die sowohl in früheren als auch höheren Versionen der .NET Framework ausgeführt werden, können Sie Ihren Code schreiben, um sicherzustellen, dass das Verhalten unabhängig von der Version, auf der Sie ausgeführt werden, identisch ist. Um sicherzustellen, dass ein Befehl den Zustand der Verbindung für alle nachfolgenden Befehle verändert, wird empfohlen, den Befehl mit <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> auszuführen. Wenn Sie sicherstellen möchten, dass ein Befehl die Verbindung für alle nachfolgenden Befehle nicht verändert, wird empfohlen, in den Befehl die Befehle zu integrieren, mit denen der Zustand der Verbindung zurückgesetzt wird. Beispiel:  
  
```sql
SET NOCOUNT ON;  
SELECT * FROM dbo.Customers;  
SET NOCOUNT OFF;  
```  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über ADO.NET](ado-net-overview.md)
- [Abrufen und Ändern von Daten in ADO.NET](retrieving-and-modifying-data.md)
