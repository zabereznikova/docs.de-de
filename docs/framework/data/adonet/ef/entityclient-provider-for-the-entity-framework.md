---
title: EntityClient-Anbieter für Entity Framework
ms.date: 03/30/2017
ms.assetid: 8c5db787-78e6-4a34-8dc1-188bca0aca5e
ms.openlocfilehash: 268608c82070e60007bc09f97a775918e0d950f3
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65583694"
---
# <a name="entityclient-provider-for-the-entity-framework"></a>EntityClient-Anbieter für Entity Framework
Der EntityClient-Anbieter ist ein von Entity Framework-Anwendungen verwendeter Datenanbieter für den Zugriff auf Daten, die in einem konzeptionellen Modell beschrieben sind. Weitere Informationen zu konzeptionellen Modellen finden Sie unter [modellieren und zuordnen](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md). EntityClient greift mithilfe von anderen .NET Framework-Datenanbietern auf die Datenquelle zu. Beim Zugreifen (SqlClient) auf eine SQL Server-Datenbank verwendet EntityClient z. B. den .NET Framework-Datenanbieter für SQL Server. Weitere Informationen zu den SqlClient-Anbieter, finden Sie unter [SqlClient für Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-the-entity-framework.md). Der EntityClient-Anbieter ist im <xref:System.Data.EntityClient>-Namespace implementiert.  
  
## <a name="managing-connections"></a>Verwalten von Verbindungen  
 Die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] baut auf speicherspezifischen [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)] Datenanbieter durch die Bereitstellung einer <xref:System.Data.EntityClient.EntityConnection> zu einem zugrunde liegenden Datenanbieter und der relationalen Datenbank. Zum Erstellen einer <xref:System.Data.EntityClient.EntityConnection> -Objekts muss auf einen Satz von Metadaten zu verweisen, die notwendigen Modelle und Zuordnung sowie einen speicherspezifischen-Anbieterzeichenfolge an Namen und eine Verbindung enthält. Nach der <xref:System.Data.EntityClient.EntityConnection> ist vorhanden, können Entitäten über die aus dem konzeptionellen Modell generierten Klassen zugegriffen werden.  
  
 In der Datei app.config kann eine Verbindungszeichenfolge angegeben werden.  
  
 Der <xref:System.Data.EntityClient> enthält auch die <xref:System.Data.EntityClient.EntityConnectionStringBuilder>-Klasse. Mithilfe dieser Klasse können Entwickler syntaktisch korrekte Verbindungszeichenfolgen programmgesteuert erstellen sowie vorhandene Verbindungszeichenfolgen analysieren und neu erstellen, indem sie Eigenschaften und Methoden der Klasse verwenden. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen einer EntityConnection-Verbindungszeichenfolge](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md).  
  
## <a name="creating-queries"></a>Erstellen von Abfragen  
 Die [!INCLUDE[esql](../../../../../includes/esql-md.md)] Sprache ist ein speicherunabhängiger Dialekt von SQL, verwendet direkt konzeptionelle Entitätsschemas und unterstützt Entity Data Model-Konzepte wie Vererbung und Beziehungen. Die <xref:System.Data.EntityClient.EntityCommand> Klasse dient zum Ausführen einer [!INCLUDE[esql](../../../../../includes/esql-md.md)] Befehl für ein Entitätsmodell. Bei der Erstellung von <xref:System.Data.EntityClient.EntityCommand>-Objekten kann der Name einer gespeicherten Prozedur oder einen Abfragetext angegeben werden. Das [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] arbeitet mit speicherspezifischen Datenanbietern, um generisches [!INCLUDE[esql](../../../../../includes/esql-md.md)] in speicherspezifische Abfragen zu übersetzen. Weitere Informationen zum Schreiben von [!INCLUDE[esql](../../../../../includes/esql-md.md)] Abfragen finden Sie [Entity SQL-Sprache](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md).  
  
 Das folgende Beispiel erstellt eine <xref:System.Data.EntityClient.EntityCommand> Objekt und weist ihm eine [!INCLUDE[esql](../../../../../includes/esql-md.md)] -Abfragetext seine <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType> Eigenschaft. Dies [!INCLUDE[esql](../../../../../includes/esql-md.md)] abfrageanforderungen Produkte, sortiert nach dem Listenpreis aus dem konzeptionellen Modell. Im folgenden Code werden keinerlei Annahmen über das Speichermodell vorausgesetzt.  
  
 ```csharp
EntityCommand cmd = conn.CreateCommand();
cmd.CommandText = @"SELECT VALUE p
  FROM AdventureWorksEntities.Product AS p
  ORDER BY p.ListPrice";
```
  
## <a name="executing-queries"></a>Ausführen von Abfragen  
 Wenn eine Abfrage ausgeführt wird, wird sie analysiert und in eine kanonische Befehlsstruktur konvertiert. Die darauf folgende Verarbeitung wird mit der Befehlsstruktur ausgeführt. Die Befehlsstruktur ist das Mittel der Kommunikation zwischen den <xref:System.Data.EntityClient> und der zugrunde liegenden .NET Framework-Datenanbieter, wie z. B. <xref:System.Data.SqlClient>.  
  
 Der <xref:System.Data.EntityClient.EntityDataReader> stellt die Ergebnisse eines für ein konzeptionelles Modell ausgeführten <xref:System.Data.EntityClient.EntityCommand> zur Verfügung. Zum Ausführen des Befehls, das den <xref:System.Data.EntityClient.EntityDataReader> zurückgibt, rufen Sie <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A> auf. Der <xref:System.Data.EntityClient.EntityDataReader> implementiert <xref:System.Data.IExtendedDataRecord>, um umfangreiche strukturierte Ergebnisse zu beschreiben.  
  
## <a name="managing-transactions"></a>Verwalten von Transaktionen  
 Im Entity Framework gibt es zwei Möglichkeiten zur Verwendung von Transaktionen: automatisch und explizit. Automatische Transaktionen verwenden den <xref:System.Transactions>-Namespace, und explizite Transaktionen verwenden die <xref:System.Data.EntityClient.EntityTransaction>-Klasse.  
  
 Um Daten zu aktualisieren, die über ein konzeptionelles Modell verfügbar gemacht wird, finden Sie unter [Vorgehensweise: Verwalten von Transaktionen in Entitätsframework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738523(v=vs.100)).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Vorgehensweise: Erstellen einer EntityConnection-Verbindungszeichenfolge](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)  
  
 [Vorgehensweise: Ausführen einer Abfrage, die PrimitiveType-Ergebnisse zurückgibt](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [Vorgehensweise: Ausführen einer Abfrage, die StructuralType-Ergebnisse zurückgibt](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [Vorgehensweise: Ausführen einer Abfrage, die RefType-Ergebnisse zurückgibt](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [Vorgehensweise: Ausführen einer Abfrage, die komplexe Typen zurückgibt](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-complex-types.md)  
  
 [Vorgehensweise: Ausführen einer Abfrage, die geschachtelte Auflistungen zurückgibt](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [Vorgehensweise: Ausführen einer parametrisierten Entity SQL-Abfrage mithilfe von EntityCommand](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [Vorgehensweise: Ausführen einer parametrisierten gespeicherten Prozedur mithilfe von EntityCommand](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [Vorgehensweise: Ausführen einer polymorphen Abfrage](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-polymorphic-query.md)  
  
 [Vorgehensweise: Navigieren in Beziehungen mit dem Navigate-Operator](../../../../../docs/framework/data/adonet/ef/how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## <a name="see-also"></a>Siehe auch

- [Verwalten von Verbindungen und Transaktionen](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896325(v=vs.100))
- [ADO.NET Entity Framework](../../../../../docs/framework/data/adonet/ef/index.md)
- [Sprachreferenz](../../../../../docs/framework/data/adonet/ef/language-reference/index.md)
