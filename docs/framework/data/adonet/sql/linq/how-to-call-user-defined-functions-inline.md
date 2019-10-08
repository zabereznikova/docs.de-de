---
title: 'Vorgehensweise: Inline-Aufrufen von benutzerdefinierten Funktionen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f80d4327-b6a5-4aa8-a743-e95d09a2a02e
ms.openlocfilehash: 01ba9ab4359cbd124b2207c87d5dae904641911a
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002986"
---
# <a name="how-to-call-user-defined-functions-inline"></a>Vorgehensweise: Inline-Aufrufen von benutzerdefinierten Funktionen
Obwohl Sie benutzerdefinierte Funktionen inline aufrufen können, werden in einer Abfrage enthaltene Funktionen, deren Ausführung umgeleitet wird, bis zur Ausführung der Abfrage verzögert. Weitere Informationen finden Sie unter [Introduction to LINQ queries (C#) (Einführung in LINQ-Abfragen (C#))](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
 Wenn Sie die gleiche Funktion außerhalb einer Abfrage ausführen, erstellt [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] eine einfache Abfrage aus der call expression-Methode. Folgendes befindet sich in der SQL-Syntax (der `@p0`-Parameter ist an die übergebene Konstante gebunden):  
  
```sql  
SELECT dbo.ReverseCustName(@p0)  
```  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] erstellt Folgendes:  
  
 [!code-csharp[DLinqUDFS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#4)]
 [!code-vb[DLinqUDFS#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#4)]  
  
## <a name="example"></a>Beispiel  
 In der folgenden [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Abfrage sehen Sie einen Inline-Aufrufder generierten benutzerdefinierten Funktions Methode `ReverseCustName`. Die Funktion wird nicht sofort ausgeführt, da die Abfrageausführung verzögert wird. Die für diese Abfrage erstellte SQL-Anweisung wird in einen Aufruf der benutzerdefinierten Funktion in der Datenbank übersetzt (siehe SQL-Code nach der Abfrage).  
  
 [!code-csharp[DLinqUDFS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#5)]
 [!code-vb[DLinqUDFS#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#5)]  
  
```sql  
SELECT [t0].[ContactName],  
    dbo.ReverseCustName([t0].[ContactTitle]) AS [Title]  
FROM [Customers] AS [t0]  
```  
  
## <a name="see-also"></a>Siehe auch

- [Benutzerdefinierte Funktionen](user-defined-functions.md)
