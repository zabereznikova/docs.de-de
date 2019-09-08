---
title: 'Vorgehensweise: Direktes Ausführen von SQL-Abfragen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e491b9bf-741a-4296-9f51-76c25ddf6a82
ms.openlocfilehash: a4971bc05b22c38790c5fd1493e70cccf5eaae16
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793785"
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
  
 Die Parameter werden im Abfragetext mithilfe der gleichen verschachtelten Schreibweise wie in `Console.WriteLine()` und `String.Format()` ausgedrückt. Tatsächlich wird tatsächlich für die von Ihnen bereitgestellte Abfrage Zeichenfolge aufgerufen, wobei die Parameter mit den geschweiften Klammern durch generierte Parameternamen @p0ersetzt @p1 werden, wie z @p. b.,..., (n). `String.Format()`  
  
## <a name="see-also"></a>Siehe auch

- [Hintergrundinformationen](background-information.md)
- [Abfragen der Datenbank](querying-the-database.md)
