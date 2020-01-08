---
title: Erste Schritte
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: db8a557a-fef8-4f4f-bb91-8cff7250ee25
ms.openlocfilehash: 3bff4e9f268e9eac84c244cb58eed8b4384e717d
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634689"
---
# <a name="getting-started"></a>Erste Schritte
Mithilfe von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]können Sie die LINQ-Technologie verwenden, um auf SQL-Datenbanken zuzugreifen, so wie Sie auf eine in-Memory-Sammlung zugreifen würden.  
  
 Beispielsweise wird das `nw`-Objekt im folgenden Code zur Darstellung der `Northwind`-Datenbank erzeugt. Das Ziel ist die `Customers`-Tabelle, die Zeilen werden nach `Customers` (Kunden) aus `London`, gefiltert, und die `CompanyName`-Zeichenfolge wird zum Abrufen ausgewählt.  
  
 Bei Ausführung der Schleife wird die Auflistung von `CompanyName`-Werten abgerufen.  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## <a name="next-steps"></a>Nächste Schritte  
 Weitere Beispiele, einschließlich einfügen und aktualisieren, finden Sie unter [was Sie mit LINQ to SQL tun können](what-you-can-do-with-linq-to-sql.md).  
  
 Versuchen Sie danach, anhand einiger exemplarischer Vorgehensweisen und Lernprogramme einen praktischen Eindruck der Verwendung von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] zu gewinnen. Weitere Informationen finden Sie [unter Learning by Walkthrough](learning-by-walkthroughs.md).  
  
 Schließlich erfahren Sie, wie Sie mit Ihrem eigenen [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Projekt beginnen, indem Sie [typische Schritte für die Verwendung von LINQ to SQL](typical-steps-for-using-linq-to-sql.md)lesen.  
  
## <a name="see-also"></a>Siehe auch

- [LINQ to SQL](index.md)
- [Einführung in LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/index.md)
- [Introduction to LINQ (Visual Basic) (Einführung in LINQ (Visual Basic))](../../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)
- [Das LINQ to SQL-Objektmodell](the-linq-to-sql-object-model.md)
