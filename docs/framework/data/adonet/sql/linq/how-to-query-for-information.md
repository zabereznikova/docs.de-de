---
title: 'Gewusst wie: Abfragen von Informationen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
ms.openlocfilehash: 3380b486da33a5dc083ed51f6705e666978df197
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634650"
---
# <a name="how-to-query-for-information"></a>Gewusst wie: Abfragen von Informationen
Bei Abfragen in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] wird dieselbe Syntax wie bei Abfragen in LINQ verwendet. Der einzige Unterschied besteht darin, dass die Objekte, auf die in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Abfragen verwiesen wird, Elementen in einer Datenbank zugeordnet werden. Weitere Informationen finden Sie unter [Introduction to LINQ queries (C#) (Einführung in LINQ-Abfragen (C#))](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] übersetzt die Abfragen, die Sie in entsprechende SQL-Abfragen schreiben, und sendet diese zur Verarbeitung an den Server.  
  
 Einige Features von LINQ-Abfragen erfordern unter Umständen besondere Aufmerksamkeit in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Anwendungen. Weitere Informationen finden Sie unter [Abfrage Konzepte](query-concepts.md).  
  
## <a name="example"></a>Beispiel  
 Die folgende Abfrage fordert eine Liste von Kunden aus London an. In diesem Beispiel ist `Customers` eine Tabelle in der Northwind-Beispieldatenbank.  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen des Objektmodells](creating-the-object-model.md)
- [Downloading Sample Databases (Herunterladen von Beispieldatenbanken)](downloading-sample-databases.md)
- [Abfragen der Datenbank](querying-the-database.md)
