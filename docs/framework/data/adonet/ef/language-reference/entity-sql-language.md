---
title: Entity SQL-Sprache
ms.date: 03/30/2017
ms.assetid: 9e7d8837-28c5-429d-a824-7bafb59724cf
ms.openlocfilehash: 721a4cd9d4e5618c083392bbe1ae203f285f8feb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148113"
---
# <a name="entity-sql-language"></a>Entity SQL-Sprache

Entity SQL ist eine speicherunabhängige Abfragesprache, die SQL ähnlich ist. Mit Entity SQL können Sie Entitätsdaten als Objekte oder in einem Tabellenformular abfragen. In den folgenden Fällen empfiehlt sich die Verwendung von Entity SQL:  
  
- Eine Abfrage muss dynamisch zur Laufzeit erstellt werden. In diesem Fall sollten Sie ebenfalls erwägen, die Abfrage-Generator-Methoden von <xref:System.Data.Objects.ObjectQuery%601> zu verwenden, statt zur Laufzeit eine Entity SQL-Abfragezeichenfolge zu erstellen.  
  
- Eine Abfrage soll als Teil der Modelldefinition definiert werden. In einem Datenmodell wird nur Entity SQL unterstützt. Weitere Informationen finden Sie unter [QueryView-Element (MSL)](/ef/ef6/modeling/designer/advanced/edmx/msl-spec#queryview-element-msl) .  
  
- EntityClient wird zur Rückgabe von schreibgeschützten Entitätsdaten als Rowsets mithilfe von <xref:System.Data.EntityClient.EntityDataReader> verwendet. Weitere Informationen finden Sie unter [EntityClient-Anbieter für das Entity Framework](../entityclient-provider-for-the-entity-framework.md).  
  
- Wenn Sie Experte für SQL-basierte Abfragesprachen sind, sind Sie mit Entity SQL möglicherweise bereits vertraut.  
  
## <a name="using-entity-sql-with-the-entityclient-provider"></a>Verwenden von Entity SQL mit dem EntityClient-Anbieter  

 Weitere Informationen zum Verwenden von Entity SQL mit dem EntityClient-Anbieter finden Sie in den folgenden Themen:  
  
 [EntityClient-Anbieter für Entity Framework](../entityclient-provider-for-the-entity-framework.md)  
  
 [Vorgehensweise: Erstellen einer EntityConnection-Verbindungszeichenfolge](../how-to-build-an-entityconnection-connection-string.md)  
  
 [Vorgehensweise: Ausführen einer Abfrage, die PrimitiveType-Ergebnisse zurückgibt](../how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [Vorgehensweise: Ausführen einer Abfrage, die StructuralType-Ergebnisse zurückgibt](../how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [Vorgehensweise: Ausführen einer Abfrage, die RefType-Ergebnisse zurückgibt](../how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [Vorgehensweise: Ausführen einer Abfrage, die komplexe Typen zurückgibt](../how-to-execute-a-query-that-returns-complex-types.md)  
  
 [Vorgehensweise: Ausführen einer Abfrage, die geschachtelte Auflistungen zurückgibt](../how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [Vorgehensweise: Ausführen einer parametrisierten Entity SQL-Abfrage mithilfe von „EntityCommand“](../how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [Vorgehensweise: Ausführen einer parametrisierten gespeicherten Prozedur mithilfe von „EntityCommand“](../how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [Vorgehensweise: Ausführen einer polymorphen Abfrage](../how-to-execute-a-polymorphic-query.md)  
  
 [Vorgehensweise: Navigieren in Beziehungen mit dem Navigate-Operator](../how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## <a name="using-entity-sql-with-object-queries"></a>Verwenden von Entity SQL mit Objektabfragen  

 Weitere Informationen zum Verwenden von Entity SQL mit Objektabfragen finden Sie in den folgenden Themen:  
  
 [Gewusst wie: Ausführen einer Abfrage, die Entitätstypobjekte zurückgibt](/previous-versions/dotnet/netframework-4.0/bb738694(v=vs.100))  
  
 [Gewusst wie: Ausführen einer parametrisierten Abfrage](/previous-versions/dotnet/netframework-4.0/bb738521(v=vs.100))  
  
 [Gewusst wie: Navigieren von Beziehungen mithilfe von Navigationseigenschaften](/previous-versions/dotnet/netframework-4.0/bb896321(v=vs.100))  
  
 [Gewusst wie: Aufrufen einer benutzerdefinierten Funktion](/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))  
  
 [Gewusst wie: Filtern von Daten](/previous-versions/dotnet/netframework-4.0/cc716755(v=vs.100))  
  
 [Gewusst wie: Sortieren von Daten](/previous-versions/dotnet/netframework-4.0/cc716784(v=vs.100))  
  
 [Gewusst wie: Gruppieren von Daten](/previous-versions/dotnet/netframework-4.0/bb896341(v=vs.100))  
  
 [Gewusst wie: Aggregieren von Daten](/previous-versions/dotnet/netframework-4.0/cc716738(v=vs.100))  
  
 [Gewusst wie: Ausführen einer Abfrage, die Objekte anonymer Typen zurückgibt](/previous-versions/dotnet/netframework-4.0/bb738512(v=vs.100))  
  
 [Gewusst wie: Ausführen einer Abfrage, die eine Auflistung primitiver Typen zurückgibt](/previous-versions/dotnet/netframework-4.0/bb738451(v=vs.100))  
  
 [Gewusst wie: Abfragen verbundener Objekte in einer "EntityCollection"](/previous-versions/dotnet/netframework-4.0/cc716708(v=vs.100))  
  
 [Gewusst wie: Sortieren zweier mit dem Union-Befehl zusammengefasster Abfragen](/previous-versions/dotnet/netframework-4.0/bb896299(v=vs.100))  
  
 [Gewusst wie: Seitenweise durch Abfrageresultate navigieren](/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [Übersicht über Entity SQL](entity-sql-overview.md)  
  
 [Entity SQL-Referenz](entity-sql-reference.md)  
  
## <a name="see-also"></a>Weitere Informationen

- [ADO.NET Entity Framework](../index.md)
- [Sprachreferenz](index.md)
