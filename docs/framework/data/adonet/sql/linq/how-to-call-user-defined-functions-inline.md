---
title: 'Vorgehensweise: Benutzerdefinierte Funktionen Inline aufrufen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f80d4327-b6a5-4aa8-a743-e95d09a2a02e
ms.openlocfilehash: 76a41ded52ac29b4a8b597188171333a888be5cd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54692768"
---
# <a name="how-to-call-user-defined-functions-inline"></a>Vorgehensweise: Benutzerdefinierte Funktionen Inline aufrufen
Obwohl Sie benutzerdefinierte Funktionen inline aufrufen können, werden in einer Abfrage enthaltene Funktionen, deren Ausführung umgeleitet wird, bis zur Ausführung der Abfrage verzögert. Weitere Informationen finden Sie unter [Introduction to LINQ queries (C#) (Einführung in LINQ-Abfragen (C#))](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
 Wenn Sie die gleiche Funktion außerhalb einer Abfrage ausführen, erstellt [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] eine einfache Abfrage aus der call expression-Methode. Folgendes befindet sich in der SQL-Syntax (der `@p0`-Parameter ist an die übergebene Konstante gebunden):  
  
```  
SELECT dbo.ReverseCustName(@p0)  
```  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] erstellt Folgendes:  
  
 [!code-csharp[DLinqUDFS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#4)]
 [!code-vb[DLinqUDFS#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#4)]  
  
## <a name="example"></a>Beispiel  
 In der folgenden [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Abfrage sehen Sie eine Inline Aufrufen an die Methode der generierten User-defined Function, `ReverseCustName`. Die Funktion wird nicht sofort ausgeführt, da die Abfrageausführung verzögert wird. Die für diese Abfrage erstellte SQL-Anweisung wird in einen Aufruf der benutzerdefinierten Funktion in der Datenbank übersetzt (siehe SQL-Code nach der Abfrage).  
  
 [!code-csharp[DLinqUDFS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#5)]
 [!code-vb[DLinqUDFS#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#5)]  
  
```  
SELECT [t0].[ContactName],  
    dbo.ReverseCustName([t0].[ContactTitle]) AS [Title]  
FROM [Customers] AS [t0]  
```  
  
## <a name="see-also"></a>Siehe auch
- [Benutzerdefinierte Funktionen](../../../../../../docs/framework/data/adonet/sql/linq/user-defined-functions.md)
