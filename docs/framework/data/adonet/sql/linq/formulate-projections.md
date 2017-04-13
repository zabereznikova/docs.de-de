---
title: "Formulieren von Projektionen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 745742df-0eda-479b-83f8-29bd8a80db96
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Formulieren von Projektionen
Das folgende Beispiel zeigt, wie die `select`\-Anweisung in C\# und die `Select`\-Anweisung in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] mit anderen Funktionen kombiniert werden können, um Abfrageprojektionen zu bilden.  
  
## Beispiel  
 Die folgenden Beispiele verwenden die `Select`\-Klausel in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] \(`select`\-Klausel in C\#\), um eine Sequenz mit Kontaktnamen für `Customers` zurückzugeben.  
  
 [!code-csharp[DLinqQueryExamples#57](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#57)]
 [!code-vb[DLinqQueryExamples#57](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#57)]  
  
## Beispiel  
 Das folgende Beispiel verwendet die `Select`\-Klausel in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] \(`select`\-Klausel in C\#\) und *anonyme Typen*, um eine Sequenz von Kontaktnamen und Telefonnummern für `Customers` zurückzugeben.  
  
 [!code-csharp[DLinqQueryExamples#58](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#58)]
 [!code-vb[DLinqQueryExamples#58](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#58)]  
  
## Beispiel  
 Das folgende Beispiel verwendet die `Select`\-Klausel in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] \(`select`\-Klausel in C\#\) und *anonyme Typen*, um eine Sequenz mit Namen und Telefonnummern für Mitarbeiter zurückzugeben.  Das `FirstName`\-Feld und das `LastName`\-Feld werden zu einem Feld \(`Name`\) kombiniert, und das `HomePhone`\-Feld wird in der resultierenden Sequenz in `Phone` umbenannt.  
  
 [!code-csharp[DLinqQueryExamples#59](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#59)]
 [!code-vb[DLinqQueryExamples#59](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#59)]  
  
## Beispiel  
 Das folgende Beispiel verwendet die `Select`\-Klausel in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] \(`select`\-Klausel in C\#\) und *anonyme Typen*, um eine Sequenz aller `ProductID`s und einen berechneten Wert namens `HalfPrice` zurückzugeben.  Dieser Wert wird auf den `UnitPrice`, geteilt durch 2, festgelegt.  
  
 [!code-csharp[DLinqQueryExamples#60](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#60)]
 [!code-vb[DLinqQueryExamples#60](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#60)]  
  
## Beispiel  
 Das folgende Beispiel verwendet die `Select`\-Klausel in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] \(`select`\-Klausel in C\#\) und eine *Bedingungsanweisung*, um eine Sequenz mit Produktnamen und Produktverfügbarkeit zurückzugeben.  
  
 [!code-csharp[DLinqQueryExamples#61](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#61)]
 [!code-vb[DLinqQueryExamples#61](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#61)]  
  
## Beispiel  
 Das folgende Beispiel verwendet die [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] `Select`\-Klausel \(`select`\-Klausel in C\#\) und einen *bekannten Typ* \(Name\), um eine Sequenz mit den Namen der Mitarbeiter zurückzugeben.  
  
 [!code-csharp[DLinqQueryExamples#62](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#62)]
 [!code-vb[DLinqQueryExamples#62](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#62)]  
  
## Beispiel  
 Das folgende Beispiel verwendet `Select` und `Where` in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] \(`select` und `where` in C\#\), um eine *gefilterte Sequenz* mit Kontaktnamen von Kunden in London zurückzugeben.  
  
 [!code-csharp[DLinqQueryExamples#63](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#63)]
 [!code-vb[DLinqQueryExamples#63](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#63)]  
  
## Beispiel  
 Das folgende Beispiel verwendet die `Select`\-Klausel in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] \(`select`\-Klausel in C\#\) und *anonyme Typen*, um eine *geformte Teilmenge* der Daten über Kunden zurückzugeben.  
  
 [!code-csharp[DLinqQueryExamples#64](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#64)]
 [!code-vb[DLinqQueryExamples#64](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#64)]  
  
## Beispiel  
 Im folgenden Beispiel werden geschachtelte Abfragen verwendet, um die folgenden Ergebnisse zurückzugeben:  
  
-   Eine Sequenz aller Bestellungen und der entsprechenden `OrderID`s.  
  
-   Eine Untersequenz der Elemente in der Bestellung, für die es einen Rabatt gibt.  
  
-   Der gesparte Betrag, wenn die Lieferkosten nicht eingeschlossen werden.  
  
 [!code-csharp[DLinqQueryExamples#65](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#65)]
 [!code-vb[DLinqQueryExamples#65](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#65)]  
  
## Siehe auch  
 [Abfragebeispiele](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)