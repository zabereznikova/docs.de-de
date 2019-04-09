---
title: Erste Schritte
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: db8a557a-fef8-4f4f-bb91-8cff7250ee25
ms.openlocfilehash: 506257c13bbaada98dffa9d3a15c834037c1d971
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59155232"
---
# <a name="getting-started"></a>Erste Schritte
Mithilfe von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], können Sie die [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] -Technologie für den Zugriff auf SQL-Datenbanken so, wie Sie eine Auflistung im Arbeitsspeicher zugreifen würden.  
  
 Beispielsweise wird das `nw`-Objekt im folgenden Code zur Darstellung der `Northwind`-Datenbank erzeugt. Das Ziel ist die `Customers`-Tabelle, die Zeilen werden nach `Customers` (Kunden) aus `London`, gefiltert, und die `CompanyName`-Zeichenfolge wird zum Abrufen ausgewählt.  
  
 Bei Ausführung der Schleife wird die Auflistung von `CompanyName`-Werten abgerufen.  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## <a name="next-steps"></a>Nächste Schritte  
 Weitere Beispiele, auch zum Einfügen und aktualisieren, finden Sie unter [was Sie können werden mit LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/what-you-can-do-with-linq-to-sql.md).  
  
 Versuchen Sie danach, anhand einiger exemplarischer Vorgehensweisen und Lernprogramme einen praktischen Eindruck der Verwendung von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] zu gewinnen. Finden Sie unter [lernen durch Exemplarische Vorgehensweisen](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md).  
  
 Abschließend erfahren Sie, wie Sie eigene beginnen [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] -Projekt, indem Sie beim Lesen der [Typische Schritte bei der Verwendung von LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/typical-steps-for-using-linq-to-sql.md).  
  
## <a name="see-also"></a>Siehe auch

- [LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/index.md)
- [Einführung in LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq.md)
- [Einführung in LINQ (Visual Basic)](../../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)
- [Das LINQ to SQL-Objektmodell](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
