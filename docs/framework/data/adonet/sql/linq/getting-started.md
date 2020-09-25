---
title: Erste Schritte
description: Mit diesem Beispielcode können Sie LINQ to SQL verwenden, um die LINQ-Technologie für den Zugriff auf SQL-Datenbanken zu verwenden, so wie Sie auf eine in-Memory-Sammlung zugreifen würden.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: db8a557a-fef8-4f4f-bb91-8cff7250ee25
ms.openlocfilehash: b886518d4cff687a18f363c3e3ba43b40631a22f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194374"
---
# <a name="getting-started"></a>Erste Schritte

Mithilfe von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] können Sie die LINQ-Technologie verwenden, um auf SQL-Datenbanken genauso zuzugreifen wie auf eine Auflistung im Arbeitsspeicher.  
  
 Beispielsweise wird das `nw`-Objekt im folgenden Code zur Darstellung der `Northwind`-Datenbank erzeugt. Das Ziel ist die `Customers`-Tabelle, die Zeilen werden nach `Customers` (Kunden) aus `London`, gefiltert, und die `CompanyName`-Zeichenfolge wird zum Abrufen ausgewählt.  
  
 Bei Ausführung der Schleife wird die Auflistung von `CompanyName`-Werten abgerufen.  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## <a name="next-steps"></a>Nächste Schritte  

 Weitere Beispiele, einschließlich einfügen und aktualisieren, finden Sie unter [was Sie mit LINQ to SQL tun können](what-you-can-do-with-linq-to-sql.md).  
  
 Versuchen Sie danach, anhand einiger exemplarischer Vorgehensweisen und Lernprogramme einen praktischen Eindruck der Verwendung von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] zu gewinnen. Weitere Informationen finden Sie [unter Learning by Walkthrough](learning-by-walkthroughs.md).  
  
 Schließlich erfahren Sie, wie Sie mit den ersten Schritten für Ihr eigenes Projekt beginnen, indem Sie die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] [typischen Schritte zum Verwenden von LINQ to SQL](typical-steps-for-using-linq-to-sql.md)lesen.  
  
## <a name="see-also"></a>Weitere Informationen

- [LINQ to SQL](index.md)
- [Einführung in LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/index.md)
- [Introduction to LINQ (Visual Basic) (Einführung in LINQ (Visual Basic))](../../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)
- [Das LINQ to SQL-Objektmodell](the-linq-to-sql-object-model.md)
