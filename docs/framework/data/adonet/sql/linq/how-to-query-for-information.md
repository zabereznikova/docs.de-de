---
title: 'Vorgehensweise: Abfragen von Informationen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
ms.openlocfilehash: aedf89f1e570b34d31050fabb91842cefe351488
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62033734"
---
# <a name="how-to-query-for-information"></a>Vorgehensweise: Abfragen von Informationen
Abfragen in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] verwenden die gleiche Syntax wie Abfragen in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]. Der einzige Unterschied ist, dass die Objekte in verwiesen [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Abfragen Elementen in einer Datenbank zugeordnet sind. Weitere Informationen finden Sie unter [Introduction to LINQ queries (C#) (Einführung in LINQ-Abfragen (C#))](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] übersetzt die Abfragen, die Sie in entsprechende SQL-Abfragen schreiben, und sendet diese zur Verarbeitung an den Server.  
  
 Einige Funktionen von [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]-Abfragen benötigen in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Anwendungen besondere Aufmerksamkeit. Weitere Informationen finden Sie unter [Abfragekonzepte](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md).  
  
## <a name="example"></a>Beispiel  
 Die folgende Abfrage fordert eine Liste von Kunden aus London an. In diesem Beispiel ist `Customers` eine Tabelle in der Northwind-Beispieldatenbank.  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen des Objektmodells](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
- [Downloading Sample Databases (Herunterladen von Beispieldatenbanken)](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
- [Abfragen der Datenbank](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
