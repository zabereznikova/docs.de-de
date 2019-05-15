---
title: Parallele Ausführung in ADO.NET
ms.date: 03/30/2017
ms.assetid: 9f9ba96d-9f89-4f65-bb2f-6860879f4393
ms.openlocfilehash: 377af3c72b0a9a8eb26c8713d98f114803f08356
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65583624"
---
# <a name="side-by-side-execution-in-adonet"></a>Parallele Ausführung in ADO.NET
Seite-an-Seite-Ausführung in .NET Framework ist die Möglichkeit, eine Anwendung auf einem Computer ausführen, die mehrere Versionen von .NET Framework installiert ist, ausschließlich mit der Version, die für die die Anwendung kompiliert wurde. Ausführliche Informationen zum Konfigurieren von Seite-an-Seite-Ausführung finden Sie unter [Seite-an-Seite-Ausführung](../../../../docs/framework/deployment/side-by-side-execution.md).  
  
 Mit einer Version von .NET Framework kompilierte Anwendung kann auf eine andere Version von .NET Framework ausgeführt. Allerdings empfiehlt es sich, dass Sie eine Version der Anwendung für jede installierte Version von .NET Framework kompilieren und diese separat ausführen. In beiden Szenarien sind die Änderungen zwischen den verschiedenen [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]-Versionen zu berücksichtigen, die die Aufwärts- und Abwärtskompatibilität Ihrer Anwendung beeinträchtigen können.  
  
## <a name="forward-compatibility-and-backward-compatibility"></a>Aufwärts- und Abwärtskompatibilität  
 Aufwärtskompatibilität bedeutet, dass eine Anwendung mit einer früheren Version von .NET Framework kompiliert werden kann, sondern unter einer höheren Version von .NET Framework Ausführbarkeit. [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] Code für .NET Framework, Version 1.1 ist aufwärtskompatibel mit höheren Versionen.  
  
 Abwärtskompatibilität bedeutet, dass eine Anwendung für eine neuere Version von .NET Framework kompiliert wird, sondern weiterhin auf früheren Versionen von .NET Framework ohne Beeinträchtigung der Funktionalität ausgeführt. Natürlich wird dies nicht der Fall für Funktionen, die in einer neuen Version von .NET Framework sein.  
  
## <a name="the-net-framework-data-provider-for-odbc"></a>Der .NET Framework-Datenanbieter für ODBC  
 Ab Version 1.1, die .NET Framework-Datenanbieter für ODBC (<xref:System.Data.Odbc>) als Teil von .NET Framework enthalten ist. Der ODBC-Datenanbieter ist verfügbar für Entwickler von .NET Framework Version 1.0 als Webdownload aus der [Data Access and Storage Developer Center](https://go.microsoft.com/fwlink/?linkid=4173). Der Namespace für die heruntergeladenen .NET Framework-Datenanbieter für ODBC lautet **Microsoft.Data.Odbc**.  
  
 Wenn eine Anwendung entwickelt, die für .NET Framework, Version 1.0, die den ODBC-Datenanbieter für die Verbindung mit der Datenquelle verwendet, und die Anwendung auf .NET Framework, Version 1.1 oder höher ausgeführt werden soll, müssen Sie den Namespace für die ODBC-DAT-Dateien aktualisieren. Ein Anbieter **System.Data.Odbc**. Sie müssen dann für die neuere Version von .NET Framework neu kompilieren.  
  
 Wenn eine Anwendung entwickelt, die für .NET Framework Version 2.0 oder höher, die den ODBC-Datenanbieter für die Verbindung mit der Datenquelle verwendet und Sie die Anwendung auf .NET Framework, Version 1.0 ausführen möchten, müssen Sie den ODBC-Datenanbieter herunterladen und installieren es Klicken Sie auf dem System mit .NET Framework Version 1.0. Sie müssen den Namespace dann ändern, für den ODBC-Datenanbieter auf **Microsoft.Data.Odbc**, und die Anwendung für .NET Framework, Version 1.0 neu kompilieren.  
  
## <a name="the-net-framework-data-provider-for-oracle"></a>Der .NET Framework-Datenanbieter für Oracle  
 Ab Version 1.1, die .NET Framework-Datenanbieter für Oracle (<xref:System.Data.OracleClient>) als Teil von .NET Framework enthalten ist. Der Datenanbieter ist verfügbar für Entwickler von .NET Framework Version 1.0 als Webdownload aus der [Data Access and Storage Developer Center](https://go.microsoft.com/fwlink/?linkid=4173).  
  
 Wenn eine Anwendung entwickelt, die für .NET Framework Version 2.0 oder höher, die den Datenanbieter für die Verbindung mit der Datenquelle verwendet und Sie die Anwendung auf .NET Framework, Version 1.0 ausführen möchten, müssen Sie die Oracle-Datenanbieter herunterladen und installieren es auf die .NE System T-Framework, Version 1.0.  
  
## <a name="code-access-security"></a>Codezugriffssicherheit  
 Die .NET Framework-Datenanbieter in .NET Framework, Version 1.0 (<xref:System.Data.SqlClient>, <xref:System.Data.OleDb>) sind erforderlich, um mit FullTrust-Berechtigung ausgeführt. Ein Versuch, die .NET Framework-k-Datenanbieter von .NET Framework, Version 1.0 in einer Zone mit weniger als FullTrust-Berechtigung wird einem <xref:System.Security.SecurityException>.  
  
 Allerdings kann ab .NET Framework, Version 2.0, alle von .NET Framework-Datenanbietern in teilweise vertrauenswürdigen Zonen verwendet werden. Darüber hinaus wurde eine neue Sicherheitsfunktion, die .NET Framework-Datenanbieter in .NET Framework, Version 1.1 hinzugefügt. Mithilfe dieser Funktion können Sie die Verbindungszeichenfolgen einschränken, die in einer bestimmten Sicherheitszone verwendet werden dürfen. Es kann auch die Verwendung leerer Kennwörter für eine bestimmte Sicherheitszone deaktiviert werden. Weitere Informationen finden Sie unter [Code Access Security and ADO.NET](../../../../docs/framework/data/adonet/code-access-security.md).  
  
 Da jede Installation von .NET Framework eine separate Security.config-Datei hat, gibt es keine Kompatibilitätsprobleme mit Sicherheitseinstellungen. Aber wenn Ihre Anwendung, auf den zusätzlichen Sicherheitsfunktionen von abhängt [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] in .NET Framework, Version 1.1 und höher enthalten, Sie ist nicht möglich, ein System mit Version 1.0 verteilen.  
  
## <a name="sqlcommand-execution"></a>"SqlCommand"-Ausführung  
 Ab .NET Framework, Version 1.1, die Möglichkeit, <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> führt Befehle auf die Daten der Datenquelle wurde geändert.  
  
 In .NET Framework, Version 1.0 <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> alle Befehle im Kontext der Ausführung der **Sp_executesql** gespeicherte Prozedur. Dadurch gelten Befehle, die den Zustand der Verbindung betreffen (z. B. SET NOCOUNT ON), nur für die Ausführung des aktuellen Befehls. Der Zustand der Verbindung wird bei offener Verbindung für keinen der nachfolgenden ausgeführten Befehle verändert.  
  
 In .NET Framework, Version 1.1 und höher <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> nur ausgeführt wird, einen Befehl im Kontext der **Sp_executesql** gespeicherte Prozedur aus, wenn der Befehl Parameter enthält einen Leistungsvorteil bietet. Dadurch verändern Befehle, die den Zustand der Verbindung betreffen und die zu einem Befehl ohne Parameter gehören, den Zustand der Verbindung für alle nachfolgenden, bei offener Verbindung ausgeführten Befehle.  
  
 Betrachten Sie den folgenden Batch von Befehlen, die in einem Aufruf an <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> ausgeführt werden.  
  
```sql
SET NOCOUNT ON;  
SELECT * FROM dbo.Customers;  
```  
  
 In .NET Framework Version 1.1 und höher bleibt NOCOUNT für alle nachfolgenden Befehle ausgeführt, während die Verbindung geöffnet ist. In .NET Framework Version 1.0 ist NOCOUNT nur auf für die Ausführung des aktuellen Befehls.  
  
 Diese Änderung kann die Kompatibilität Aufwärts- und Abwärtskompatibilität Ihrer Anwendung beeinflussen, wenn Sie das Verhalten des abhängig <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> bei jeder Version von .NET Framework.  
  
 Für Anwendungen, die auf frühere und späteren Versionen von .NET Framework ausgeführt werden, können Sie Ihren Code, um sicherzustellen, dass das Verhalten unabhängig von der Version, die Sie übereinstimmt auf Ausführen, schreiben. Um sicherzustellen, dass ein Befehl den Zustand der Verbindung für alle nachfolgenden Befehle verändert, wird empfohlen, den Befehl mit <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> auszuführen. Wenn Sie sicherstellen möchten, dass ein Befehl die Verbindung für alle nachfolgenden Befehle nicht verändert, wird empfohlen, in den Befehl die Befehle zu integrieren, mit denen der Zustand der Verbindung zurückgesetzt wird. Zum Beispiel:  
  
```sql
SET NOCOUNT ON;  
SELECT * FROM dbo.Customers;  
SET NOCOUNT OFF;  
```  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über ADO.NET](../../../../docs/framework/data/adonet/ado-net-overview.md)
- [Abrufen und Ändern von Daten in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
