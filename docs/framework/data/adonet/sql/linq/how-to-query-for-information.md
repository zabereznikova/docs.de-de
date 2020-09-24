---
title: 'Vorgehensweise: Abfragen von Informationen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
ms.openlocfilehash: d45fdfa8b8976e3cdc86b905443bf7bcea578714
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166403"
---
# <a name="how-to-query-for-information"></a>Vorgehensweise: Abfragen von Informationen

Bei Abfragen in wird [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] dieselbe Syntax verwendet wie bei Abfragen in LINQ. Der einzige Unterschied besteht darin, dass die Objekte, auf die in Abfragen verwiesen wird [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , Elementen in einer Datenbank zugeordnet werden. Weitere Informationen finden Sie unter [Introduction to LINQ queries (C#) (Einführung in LINQ-Abfragen (C#))](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] übersetzt die Abfragen, die Sie in entsprechende SQL-Abfragen schreiben, und sendet diese zur Verarbeitung an den Server.  
  
 Einige Features von LINQ-Abfragen erfordern unter Umständen besondere Aufmerksamkeit bei [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Anwendungen. Weitere Informationen finden Sie unter [Abfrage Konzepte](query-concepts.md).  
  
## <a name="example"></a>Beispiel  

 Die folgende Abfrage fordert eine Liste von Kunden aus London an. In diesem Beispiel ist `Customers` eine Tabelle in der Northwind-Beispieldatenbank.  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Erstellen des Objektmodells](creating-the-object-model.md)
- [Herunterladen von Beispieldatenbanken](downloading-sample-databases.md)
- [Abfragen der Datenbank](querying-the-database.md)
