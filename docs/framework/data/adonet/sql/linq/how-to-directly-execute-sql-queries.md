---
title: 'Vorgehensweise: Direktes Ausführen von SQL-Abfragen'
description: Erfahren Sie, wie Sie mithilfe von ExecuteQuery eine Abfrage ausführen und die Ergebnisse in Fällen, in denen eine LINQ to SQL Abfrage unzureichend ist, direkt in Objekte konvertieren.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e491b9bf-741a-4296-9f51-76c25ddf6a82
ms.openlocfilehash: 7ebd02581d789266396b58296bbd6ad312dd468e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200575"
---
# <a name="how-to-directly-execute-sql-queries"></a>Vorgehensweise: Direktes Ausführen von SQL-Abfragen

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] übersetzt die Abfragen, die von Ihnen (in Textform) in parametrisierte SQL-Abfragen geschrieben wurden, und sendet diese zur Verarbeitung an den SQL-Server.  
  
 SQL kann nicht alle lokal für Ihre Anwendung verfügbaren Varianten ausführen. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] versucht, diese lokalen Methoden in äquivalente Operationen und Funktionen zu konvertieren, die in der SQL-Umgebung verfügbar sind. Die meisten Methoden und Operatoren in .NET Framework integrierten Typen weisen direkte Übersetzungen in SQL-Befehle auf. Einige können von den verfügbaren Funktionen erzeugt werden. Jene, die nicht erzeugt werden können, generieren Laufzeitausnahmen. Weitere Informationen finden Sie unter [SQL-CLR-Typzuordnung](sql-clr-type-mapping.md).  
  
 In Fällen, in denen eine [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Abfrage für spezielle Aufgaben nicht ausreicht, können Sie die <xref:System.Data.Linq.DataContext.ExecuteQuery%2A>-Methode zur Ausführung einer SQL-Abfrage verwenden und das Ergebnis anschließend direkt in Objekte konvertieren.  
  
## <a name="example"></a>Beispiel  

 Nehmen Sie im folgenden Beispiel an, dass die Daten für die `Customer`-Klasse auf zwei Tabellen (Customer1 und Customer2) verteilt sind. Die Abfrage gibt eine Sequenz von `Customer`-Objekten zurück.  
  
 [!code-csharp[DLinqQuerying#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#4)]
 [!code-vb[DLinqQuerying#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#4)]  
  
 Solange die Spaltennamen im tabellarischen Ergebnis den Spalten Eigenschaften ihrer Entitäts Klasse entsprechen, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] erstellt die Objekte aus einer beliebigen SQL-Abfrage.  
  
## <a name="example"></a>Beispiel  

 Die <xref:System.Data.Linq.DataContext.ExecuteQuery%2A>-Methode berücksichtigt auch Parameter. Verwenden Sie Code wie den folgenden, um eine parametrisierte Abfrage auszuführen.  
  
 [!code-csharp[DLinqQuerying#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#5)]
 [!code-vb[DLinqQuerying#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#5)]  
  
 Die Parameter werden im Abfragetext mithilfe der gleichen verschachtelten Schreibweise wie in `Console.WriteLine()` und `String.Format()` ausgedrückt. Tatsächlich `String.Format()` wird tatsächlich für die von Ihnen bereitgestellte Abfrage Zeichenfolge aufgerufen, wobei die Parameter mit den geschweiften Klammern durch generierte Parameternamen ersetzt werden, wie z. b @p0 @p1 .,..., @p (n).  
  
## <a name="see-also"></a>Weitere Informationen

- [Hintergrundinformationen](background-information.md)
- [Abfragen der Datenbank](querying-the-database.md)
