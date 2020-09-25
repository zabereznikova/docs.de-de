---
title: EntityClient-Anbieter für Entity Framework
ms.date: 03/30/2017
ms.assetid: 8c5db787-78e6-4a34-8dc1-188bca0aca5e
ms.openlocfilehash: 9b3194e4a85eda6f405a3ab85723ac2cb9d00090
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181075"
---
# <a name="entityclient-provider-for-the-entity-framework"></a>EntityClient-Anbieter für Entity Framework

Der EntityClient-Anbieter ist ein von Entity Framework-Anwendungen verwendeter Datenanbieter für den Zugriff auf Daten, die in einem konzeptionellen Modell beschrieben sind. Weitere Informationen zu konzeptionellen Modellen finden Sie unter [Modellierung und Zuordnung](modeling-and-mapping.md). EntityClient greift mithilfe von anderen .NET Framework-Datenanbietern auf die Datenquelle zu. Beim Zugreifen (SqlClient) auf eine SQL Server-Datenbank verwendet EntityClient z. B. den .NET Framework-Datenanbieter für SQL Server. Weitere Informationen zum SqlClient-Anbieter finden Sie unter [SqlClient für die Entity Framework](sqlclient-for-the-entity-framework.md). Der EntityClient-Anbieter ist im <xref:System.Data.EntityClient>-Namespace implementiert.  
  
## <a name="managing-connections"></a>Verwalten von Verbindungen  

 Der Entity Framework baut auf Speicher spezifischen ADO.NET-Datenanbietern auf, indem er einem <xref:System.Data.EntityClient.EntityConnection> zugrunde liegenden Datenanbieter und einer relationalen Datenbank ein bereitstellt. Um ein Objekt zu erstellen <xref:System.Data.EntityClient.EntityConnection> , müssen Sie auf einen Satz von Metadaten verweisen, der die erforderlichen Modelle und die Zuordnung sowie einen Speicher spezifischen Datenanbieter Namen und eine Verbindungs Zeichenfolge enthält. Nachdem der <xref:System.Data.EntityClient.EntityConnection> vorhanden ist, kann auf Entitäten über die vom konzeptionellen Modell generierten Klassen zugegriffen werden.  
  
 In der Datei app.config kann eine Verbindungszeichenfolge angegeben werden.  
  
 Der <xref:System.Data.EntityClient> enthält auch die <xref:System.Data.EntityClient.EntityConnectionStringBuilder>-Klasse. Mithilfe dieser Klasse können Entwickler syntaktisch korrekte Verbindungszeichenfolgen programmgesteuert erstellen sowie vorhandene Verbindungszeichenfolgen analysieren und neu erstellen, indem sie Eigenschaften und Methoden der Klasse verwenden. Weitere Informationen finden Sie unter Gewusst [wie: Erstellen einer EntityConnection-Verbindungs Zeichenfolge](how-to-build-an-entityconnection-connection-string.md).  
  
## <a name="creating-queries"></a>Erstellen von Abfragen  

 Die [!INCLUDE[esql](../../../../../includes/esql-md.md)] Sprache ist ein Speicher unabhängiger Dialekt von SQL, der direkt mit konzeptionellen Entitäts Schemas arbeitet und Entity Data Model Konzepte wie Vererbung und Beziehungen unterstützt. Die- <xref:System.Data.EntityClient.EntityCommand> Klasse wird verwendet, um einen [!INCLUDE[esql](../../../../../includes/esql-md.md)] Befehl für ein Entitäts Modell auszuführen. Bei der Erstellung von <xref:System.Data.EntityClient.EntityCommand>-Objekten kann der Name einer gespeicherten Prozedur oder einen Abfragetext angegeben werden. Der Entity Framework arbeitet mit Speicher spezifischen Datenanbietern zusammen, um generische [!INCLUDE[esql](../../../../../includes/esql-md.md)] in Speicher spezifische Abfragen zu übersetzen. Weitere Informationen zum Schreiben von [!INCLUDE[esql](../../../../../includes/esql-md.md)] Abfragen finden Sie unter [Entity SQL Sprache](./language-reference/entity-sql-language.md).  
  
 Im folgenden Beispiel wird ein <xref:System.Data.EntityClient.EntityCommand> -Objekt erstellt und der- [!INCLUDE[esql](../../../../../includes/esql-md.md)] Eigenschaft ein Abfragetext zugewiesen <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType> . Diese [!INCLUDE[esql](../../../../../includes/esql-md.md)] Abfrage fordert Produkte nach dem Listenpreis aus dem konzeptionellen Modell an. Im folgenden Code werden keinerlei Annahmen über das Speichermodell vorausgesetzt.  
  
 ```csharp
EntityCommand cmd = conn.CreateCommand();
cmd.CommandText = @"SELECT VALUE p
  FROM AdventureWorksEntities.Product AS p
  ORDER BY p.ListPrice";
```
  
## <a name="executing-queries"></a>Ausführen von Abfragen  

 Wenn eine Abfrage ausgeführt wird, wird sie analysiert und in eine kanonische Befehlsstruktur konvertiert. Die darauf folgende Verarbeitung wird mit der Befehlsstruktur ausgeführt. Die Befehlsstruktur ist die Mittel der Kommunikation zwischen dem <xref:System.Data.EntityClient> und dem zugrunde liegenden .NET Framework-Datenanbieter, wie z <xref:System.Data.SqlClient> . b..  
  
 Der <xref:System.Data.EntityClient.EntityDataReader> stellt die Ergebnisse eines für ein konzeptionelles Modell ausgeführten <xref:System.Data.EntityClient.EntityCommand> zur Verfügung. Zum Ausführen des Befehls, das den <xref:System.Data.EntityClient.EntityDataReader> zurückgibt, rufen Sie <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A> auf. Der <xref:System.Data.EntityClient.EntityDataReader> implementiert <xref:System.Data.IExtendedDataRecord>, um umfangreiche strukturierte Ergebnisse zu beschreiben.  
  
## <a name="managing-transactions"></a>Verwalten von Transaktionen  

 Im Entity Framework gibt es zwei Möglichkeiten zur Verwendung von Transaktionen: automatisch und explizit. Automatische Transaktionen verwenden den <xref:System.Transactions>-Namespace, und explizite Transaktionen verwenden die <xref:System.Data.EntityClient.EntityTransaction>-Klasse.  
  
 Informationen zum Aktualisieren von Daten, die über ein konzeptionelles Modell verfügbar gemacht werden, finden Sie unter Gewusst [wie: Verwalten von Transaktionen in der Entity Framework](/previous-versions/dotnet/netframework-4.0/bb738523(v=vs.100)).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [Vorgehensweise: Erstellen einer EntityConnection-Verbindungszeichenfolge](how-to-build-an-entityconnection-connection-string.md)  
  
 [Vorgehensweise: Ausführen einer Abfrage, die PrimitiveType-Ergebnisse zurückgibt](how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [Vorgehensweise: Ausführen einer Abfrage, die StructuralType-Ergebnisse zurückgibt](how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [Vorgehensweise: Ausführen einer Abfrage, die RefType-Ergebnisse zurückgibt](how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [Vorgehensweise: Ausführen einer Abfrage, die komplexe Typen zurückgibt](how-to-execute-a-query-that-returns-complex-types.md)  
  
 [Vorgehensweise: Ausführen einer Abfrage, die geschachtelte Auflistungen zurückgibt](how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [Vorgehensweise: Ausführen einer parametrisierten Entity SQL-Abfrage mithilfe von „EntityCommand“](how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [Vorgehensweise: Ausführen einer parametrisierten gespeicherten Prozedur mithilfe von „EntityCommand“](how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [Vorgehensweise: Ausführen einer polymorphen Abfrage](how-to-execute-a-polymorphic-query.md)  
  
 [Vorgehensweise: Navigieren in Beziehungen mit dem Navigate-Operator](how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## <a name="see-also"></a>Weitere Informationen

- [Verwalten von Verbindungen und Transaktionen](/previous-versions/dotnet/netframework-4.0/bb896325(v=vs.100))
- [ADO.NET Entity Framework](index.md)
- [Sprachreferenz](./language-reference/index.md)
