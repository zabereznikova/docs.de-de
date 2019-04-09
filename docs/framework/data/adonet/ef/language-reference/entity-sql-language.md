---
title: Entity SQL-Sprache
ms.date: 03/30/2017
ms.assetid: 9e7d8837-28c5-429d-a824-7bafb59724cf
ms.openlocfilehash: 09ec1a5518ec0847b54394449f32b3068c811577
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59140932"
---
# <a name="entity-sql-language"></a>Entity SQL-Sprache
Entity SQL ist eine speicherunabhängige Abfragesprache, die SQL ähnlich ist. Mit Entity SQL können Sie Entitätsdaten als Objekte oder in einem Tabellenformular abfragen. In den folgenden Fällen empfiehlt sich die Verwendung von Entity SQL:  
  
-   Eine Abfrage muss dynamisch zur Laufzeit erstellt werden. In diesem Fall sollten Sie ebenfalls erwägen, die Abfrage-Generator-Methoden von <xref:System.Data.Objects.ObjectQuery%601> zu verwenden, statt zur Laufzeit eine Entity SQL-Abfragezeichenfolge zu erstellen.  
  
-   Eine Abfrage soll als Teil der Modelldefinition definiert werden. In einem Datenmodell wird nur Entity SQL unterstützt. Weitere Informationen finden Sie unter [QueryView-Element (MSL)](/ef/ef6/modeling/designer/advanced/edmx/msl-spec#queryview-element-msl)  
  
-   EntityClient wird zur Rückgabe von schreibgeschützten Entitätsdaten als Rowsets mithilfe von <xref:System.Data.EntityClient.EntityDataReader> verwendet. Weitere Informationen finden Sie unter [EntityClient-Anbieter für Entity Framework](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).  
  
-   Wenn Sie Experte für SQL-basierte Abfragesprachen sind, sind Sie mit Entity SQL möglicherweise bereits vertraut.  
  
## <a name="using-entity-sql-with-the-entityclient-provider"></a>Verwenden von Entity SQL mit dem EntityClient-Anbieter  
 Weitere Informationen zum Verwenden von Entity SQL mit dem EntityClient-Anbieter finden Sie in den folgenden Themen:  
  
 [EntityClient-Anbieter für Entity Framework](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)  
  
 [Vorgehensweise: Erstellen einer EntityConnection-Verbindungszeichenfolge](../../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)  
  
 [Vorgehensweise: Ausführen einer Abfrage, die PrimitiveType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [Vorgehensweise: Ausführen einer Abfrage, die StructuralType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [Vorgehensweise: Ausführen einer Abfrage, die RefType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [Vorgehensweise: Ausführen einer Abfrage, die komplexe Typen zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-complex-types.md)  
  
 [Vorgehensweise: Ausführen einer Abfrage, die geschachtelte Auflistungen zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [Vorgehensweise: Ausführen einer parametrisierten Entity SQL-Abfrage mithilfe von „EntityCommand“](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [Vorgehensweise: Ausführen einer parametrisierten gespeicherten Prozedur mithilfe von „EntityCommand“](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [Vorgehensweise: Ausführen einer polymorphen Abfrage](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-polymorphic-query.md)  
  
 [Vorgehensweise: Navigieren in Beziehungen mit dem Navigate-Operator](../../../../../../docs/framework/data/adonet/ef/how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## <a name="using-entity-sql-with-object-queries"></a>Verwenden von Entity SQL mit Objektabfragen  
 Weitere Informationen zum Verwenden von Entity SQL mit Objektabfragen finden Sie in den folgenden Themen:  
  
 [Vorgehensweise: Ausführen einer Abfrage, die Entitätstypobjekte zurückgibt](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738694(v=vs.100))  
  
 [Vorgehensweise: Ausführen einer parametrisierten Abfrage](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738521(v=vs.100))  
  
 [Vorgehensweise: Navigieren Sie in Beziehungen mithilfe von Navigationseigenschaften](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896321(v=vs.100))  
  
 [Vorgehensweise: Aufrufen einer benutzerdefinierten Funktion](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))  
  
 [Vorgehensweise: Filtern von Daten](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716755(v=vs.100))  
  
 [Vorgehensweise: Sortieren von Daten](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716784(v=vs.100))  
  
 [Vorgehensweise: Gruppieren von Daten](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896341(v=vs.100))  
  
 [Vorgehensweise: Aggregieren von Daten](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716738(v=vs.100))  
  
 [Vorgehensweise: Ausführen einer Abfrage, die Objekte anonymer Typen zurückgibt](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738512(v=vs.100))  
  
 [Vorgehensweise: Ausführen einer Abfrage, die eine Auflistung von primitiven Typen zurückgibt](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738451(v=vs.100))  
  
 [Vorgehensweise: Fragen Sie verbundener Objekte in einer "EntityCollection ab"](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716708(v=vs.100))  
  
 [Vorgehensweise: Reihenfolge der Union von zwei Abfragen](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896299(v=vs.100))  
  
 [Vorgehensweise: Seitenweise Abfrageresultate durch Navigieren](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Übersicht über Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
  
 [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
  
## <a name="see-also"></a>Siehe auch

- [ADO.NET Entity Framework](../../../../../../docs/framework/data/adonet/ef/index.md)
- [Sprachreferenz](../../../../../../docs/framework/data/adonet/ef/language-reference/index.md)
