---
title: Entity SQL-Sprache
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9e7d8837-28c5-429d-a824-7bafb59724cf
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 0485dc9ee1e1b6fa134e0a7518b7ae49748ae292
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="entity-sql-language"></a>Entity SQL-Sprache
Entity SQL ist eine speicherunabhängige Abfragesprache, die SQL ähnlich ist. Mit Entity SQL können Sie Entitätsdaten als Objekte oder in einem Tabellenformular abfragen. In den folgenden Fällen empfiehlt sich die Verwendung von Entity SQL:  
  
-   Eine Abfrage muss dynamisch zur Laufzeit erstellt werden. In diesem Fall sollten Sie ebenfalls erwägen, die Abfrage-Generator-Methoden von <xref:System.Data.Objects.ObjectQuery%601> zu verwenden, statt zur Laufzeit eine Entity SQL-Abfragezeichenfolge zu erstellen.  
  
-   Eine Abfrage soll als Teil der Modelldefinition definiert werden. In einem Datenmodell wird nur Entity SQL unterstützt. Weitere Informationen finden Sie unter [QueryView-Element (MSL)](http://msdn.microsoft.com/en-us/f0426b34-45cb-4fd7-9777-e0570c5e0e80)  
  
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
  
 [Vorgehensweise: Ausführen einer parametrisierten Entity SQL-Abfrage mithilfe von EntityCommand](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [Vorgehensweise: Ausführen einer parametrisierten gespeicherten Prozedur mithilfe von EntityCommand](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [Vorgehensweise: Ausführen einer polymorphen Abfrage](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-polymorphic-query.md)  
  
 [Vorgehensweise: Navigieren in Beziehungen mit dem Navigate-Operator](../../../../../../docs/framework/data/adonet/ef/how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## <a name="using-entity-sql-with-object-queries"></a>Verwenden von Entity SQL mit Objektabfragen  
 Weitere Informationen zum Verwenden von Entity SQL mit Objektabfragen finden Sie in den folgenden Themen:  
  
 [Vorgehensweise: Ausführen einer Abfrage, die Art von Entitätsobjekten zurückgibt.](http://msdn.microsoft.com/en-us/f73e137d-1534-42bb-9e31-99ca42c19b48)  
  
 [Vorgehensweise: Ausführen einer parametrisierten Abfrage](http://msdn.microsoft.com/en-us/42048f03-c65c-4d98-b50a-3e7d537a63e8)  
  
 [Vorgehensweise: Navigieren in Beziehungen mit Navigationseigenschaften](http://msdn.microsoft.com/en-us/b1d71c7d-16a7-4b46-96ac-690176bd5057)  
  
 [Vorgehensweise: Aufrufen eine benutzerdefinierten Funktion](http://msdn.microsoft.com/en-us/ad131b86-8b4e-4747-8605-d4fc64fb9d02)  
  
 [Vorgehensweise: Filtern von Daten](http://msdn.microsoft.com/en-us/776f8556-3350-4572-804a-b1513515c1b2)  
  
 [Vorgehensweise: Sortieren von Daten](http://msdn.microsoft.com/en-us/c05f2506-cb9d-4ebc-822b-300042ad53e7)  
  
 [Vorgehensweise: Gruppieren von Daten](http://msdn.microsoft.com/en-us/df801d9d-9a8a-4157-97a6-5016b18998e1)  
  
 [Vorgehensweise: Aggregieren von Daten](http://msdn.microsoft.com/en-us/4cf04ce8-3c0f-4f88-9d97-8fac8622598d)  
  
 [Vorgehensweise: Ausführen einer Abfrage, die Objekte des anonymen Typs zurückgibt.](http://msdn.microsoft.com/en-us/3b264025-e911-4d73-90ce-992d2b9d189d)  
  
 [Vorgehensweise: Ausführen einer Abfrage, die eine Auflistung von primitiven Typen zurückgibt.](http://msdn.microsoft.com/en-us/115b52c0-4f27-4253-8991-284b450000b5)  
  
 [Vorgehensweise: Abfragen von verbundenen Objekten in einer EntityCollection](http://msdn.microsoft.com/en-us/11ce946f-16f8-4c1d-9d80-f740853807ba)  
  
 [Vorgehensweise: Sortieren die Union von zwei Abfragen](http://msdn.microsoft.com/en-us/853c583a-eaba-4400-830d-be974e735313)  
  
 [Vorgehensweise: seitenweise durch Abfrageresultate navigieren](http://msdn.microsoft.com/en-us/ffc0f920-e7de-42e0-9b12-ef356421d030)  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Übersicht über Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
  
 [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
  
## <a name="see-also"></a>Siehe auch  
 [ADO.NET Entity Framework](../../../../../../docs/framework/data/adonet/ef/index.md)  
 [Sprachreferenz](../../../../../../docs/framework/data/adonet/ef/language-reference/index.md)
