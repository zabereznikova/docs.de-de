---
title: Parallele Ausführung in ADO.NET
ms.date: 03/30/2017
ms.assetid: 9f9ba96d-9f89-4f65-bb2f-6860879f4393
ms.openlocfilehash: a8747d749ed7e751ba577a2cd29c2048065f2645
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136759"
---
# <a name="side-by-side-execution-in-adonet"></a>Parallele Ausführung in ADO.NET
Parallele Ausführung in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] ist die Fähigkeit, eine Anwendung auf einem Computer, auf dem mehrere Versionen von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] installiert sind, ausschließlich mit der Version auszuführen, für die die Anwendung kompiliert wurde. Ausführliche Informationen zum Konfigurieren von Seite-an-Seite-Ausführung finden Sie unter [Seite-an-Seite-Ausführung](../../../../docs/framework/deployment/side-by-side-execution.md).  
  
 Eine Anwendung, die für die Verwendung einer Version von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] kompiliert wurde, kann unter einer anderen Version von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] ausgeführt werden. Es wird jedoch empfohlen, dass Sie für jede installierte Version von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] eine eigene Version der Anwendung kompilieren und diese separat ausführen. In beiden Szenarien sind die Änderungen zwischen den verschiedenen [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]-Versionen zu berücksichtigen, die die Aufwärts- und Abwärtskompatibilität Ihrer Anwendung beeinträchtigen können.  
  
## <a name="forward-compatibility-and-backward-compatibility"></a>Aufwärts- und Abwärtskompatibilität  
 Aufwärtskompatibilität bedeutet, dass eine Anwendung mit einer früheren Version von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] kompiliert werden kann, ohne dass sich dies negativ auf ihre Ausführbarkeit unter einer späteren Version von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] auswirkt. [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] Code für die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Version 1.1 ist aufwärtskompatibel mit höheren Versionen.  
  
 Abwärtskompatibilität bedeutet, dass eine Anwendung für eine neuere Version von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] kompiliert wird, aber ohne Beeinträchtigung der Funktionalität weiterhin auch unter älteren Versionen von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] ausgeführt werden kann. Dies gilt natürlich nicht für Funktionen, die erst in einer neuen Version von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] eingeführt wurden.  
  
## <a name="the-net-framework-data-provider-for-odbc"></a>Der .NET Framework-Datenanbieter für ODBC  
 Der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Datenanbieter für ODBC (<xref:System.Data.Odbc>) gehört seit Version 1.1 zum Lieferumfang von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]. Der ODBC-Datenanbieter steht [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Entwickler Version 1.0 herunterladen aus der [Data Access and Storage Developer Center](https://go.microsoft.com/fwlink/?linkid=4173). Der Namespace für den heruntergeladenen [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datenanbieter für ODBC ist **Microsoft.Data.Odbc**.  
  
 Wenn Sie eine Anwendung, die für entwickelt haben die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Version 1.0, die den ODBC-Datenanbieter verwendet wird, zur Verbindung mit Ihrer Datenquelle, und Sie die Anwendung ausführen möchten die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Version 1.1 oder höher, aktualisieren Sie den Namespace für den ODBC Datenanbieter **System.Data.Odbc**. Anschließend müssen Sie die Anwendung für die neuere Version von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] neu kompilieren.  
  
 Wenn Sie eine für [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 2.0 oder höher entwickelte Anwendung haben, die zum Herstellen einer Verbindung mit Ihrer Datenquelle den ODBC-Datenanbieter verwendet, und Sie diese Anwendung mit [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 1.0 ausführen möchten, müssen Sie den ODBC-Datenanbieter herunterladen und ihn auf dem [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 1.0-System installieren. Sie müssen den Namespace dann ändern, für den ODBC-Datenanbieter auf **Microsoft.Data.Odbc**, und kompilieren Sie die Anwendung für die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Version 1.0.  
  
## <a name="the-net-framework-data-provider-for-oracle"></a>Der .NET Framework-Datenanbieter für Oracle  
 Der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Datenanbieter für Oracle (<xref:System.Data.OracleClient>) gehört seit Version 1.1 zum Lieferumfang von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]. Der Datenanbieter ist zur [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Entwickler Version 1.0 herunterladen aus der [Data Access and Storage Developer Center](https://go.microsoft.com/fwlink/?linkid=4173).  
  
 Wenn Sie eine Anwendung, die für entwickelt haben die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Version 2.0 oder höher, die den Datenanbieter verwendet wird, um die Verbindung mit Ihrer Datenquelle, und Sie die Anwendung ausführen möchten die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] , Version 1.0, müssen Sie die Oracle-Datenanbieter herunterladen und installieren Sie es auf die < C4 > [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]  -System, Version 1.0.  
  
## <a name="code-access-security"></a>Codezugriffssicherheit  
 Die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Datenanbieter in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 1.0 (<xref:System.Data.SqlClient>, <xref:System.Data.OleDb>) müssen mit FullTrust-Berechtigung ausgeführt werden. Ein Versuch, den [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datenanbieter aus der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Version 1.0 in einer Zone mit weniger als FullTrust-Berechtigung wird einem <xref:System.Security.SecurityException>.  
  
 Ab [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]  2.0 können jedoch alle [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Datenanbieter in teilweise vertrauenswürdigen Zonen verwendet werden. Außerdem wurde den [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Datenanbietern in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 1.1 eine neue Sicherheitsfunktion hinzugefügt. Mithilfe dieser Funktion können Sie die Verbindungszeichenfolgen einschränken, die in einer bestimmten Sicherheitszone verwendet werden dürfen. Es kann auch die Verwendung leerer Kennwörter für eine bestimmte Sicherheitszone deaktiviert werden. Weitere Informationen finden Sie unter [Code Access Security and ADO.NET](../../../../docs/framework/data/adonet/code-access-security.md).  
  
 Da jede Installation von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] über eine eigene Security.config-Datei verfügt, treten bei Sicherheitseinstellungen keine Probleme bezüglich der Kompatibilität auf. Wenn die Anwendung jedoch von den zusätzlichen Sicherheitsfunktionen von [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 1.1 oder höher abhängig ist, können Sie sie nicht an ein System mit Version 1.0 verteilen.  
  
## <a name="sqlcommand-execution"></a>"SqlCommand"-Ausführung  
 Ab [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 1.1 wurde das Verfahren geändert, mit dem der <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> Befehle an der Datenquelle ausführt.  
  
 In der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] , Version 1.0, <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> alle Befehle im Kontext der Ausführung der **Sp_executesql** gespeicherte Prozedur. Dadurch gelten Befehle, die den Zustand der Verbindung betreffen (z. B. SET NOCOUNT ON), nur für die Ausführung des aktuellen Befehls. Der Zustand der Verbindung wird bei offener Verbindung für keinen der nachfolgenden ausgeführten Befehle verändert.  
  
 In der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Version 1.1 und höher, <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> nur ausgeführt wird, einen Befehl im Kontext der **Sp_executesql** gespeicherte Prozedur aus, wenn der Befehl Parameter enthält einen Leistungsvorteil bietet. Dadurch verändern Befehle, die den Zustand der Verbindung betreffen und die zu einem Befehl ohne Parameter gehören, den Zustand der Verbindung für alle nachfolgenden, bei offener Verbindung ausgeführten Befehle.  
  
 Betrachten Sie den folgenden Batch von Befehlen, die in einem Aufruf an <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> ausgeführt werden.  
  
```sql
SET NOCOUNT ON;  
SELECT * FROM dbo.Customers;  
```  
  
 In [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 1.1 und höher bleibt NOCOUNT für alle nachfolgenden Befehle, die bei offener Verbindung ausgeführt werden, auf ON festgelegt. In [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 1.0 ist NOCOUNT nur für die jeweils aktuelle Befehlsausführung auf ON gesetzt.  
  
 Diese Änderung kann sowohl die Aufwärts- als auch die Abwärtskompatibilität der Anwendung beeinträchtigen, sofern eine Abhängigkeit vom Verhalten des <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> für eine der beiden [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Versionen besteht.  
  
 Bei Anwendungen, die sowohl mit älteren als auch mit neueren Versionen von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] ausführbar sind, können Sie den Code so schreiben, dass ein identisches Verhalten gewährleistet ist, egal, welche Version verwendet wird. Um sicherzustellen, dass ein Befehl den Zustand der Verbindung für alle nachfolgenden Befehle verändert, wird empfohlen, den Befehl mit <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> auszuführen. Wenn Sie sicherstellen möchten, dass ein Befehl die Verbindung für alle nachfolgenden Befehle nicht verändert, wird empfohlen, in den Befehl die Befehle zu integrieren, mit denen der Zustand der Verbindung zurückgesetzt wird. Zum Beispiel:  
  
```sql
SET NOCOUNT ON;  
SELECT * FROM dbo.Customers;  
SET NOCOUNT OFF;  
```  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über ADO.NET](../../../../docs/framework/data/adonet/ado-net-overview.md)
- [Abrufen und Ändern von Daten in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
