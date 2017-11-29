---
title: "Gewusst wie: Direktes Ausführen von SQL-Abfragen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: e491b9bf-741a-4296-9f51-76c25ddf6a82
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0ccc47a1ea740c5106517f6f53620ddc8097c531
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-directly-execute-sql-queries"></a>Gewusst wie: Direktes Ausführen von SQL-Abfragen
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] übersetzt die Abfragen, die von Ihnen (in Textform) in parametrisierte SQL-Abfragen geschrieben wurden, und sendet diese zur Verarbeitung an den SQL-Server.  
  
 SQL kann nicht alle lokal für Ihre Anwendung verfügbaren Varianten ausführen. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] versucht, diese lokalen Methoden in äquivalente Operationen und Funktionen zu konvertieren, die in der SQL-Umgebung verfügbar sind. Die meisten Methoden und die Operatoren in [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)]-internen Datentypen verfügen über direkte Übersetzungen zu SQL-Befehlen. Einige können von den verfügbaren Funktionen erzeugt werden. Jene, die nicht erzeugt werden können, generieren Laufzeitausnahmen. Weitere Informationen finden Sie unter [SQL-CLR-Typzuordnung](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).  
  
 In Fällen, in denen eine [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Abfrage für spezielle Aufgaben nicht ausreicht, können Sie die <xref:System.Data.Linq.DataContext.ExecuteQuery%2A>-Methode zur Ausführung einer SQL-Abfrage verwenden und das Ergebnis anschließend direkt in Objekte konvertieren.  
  
## <a name="example"></a>Beispiel  
 Nehmen Sie im folgenden Beispiel an, dass die Daten für die `Customer`-Klasse auf zwei Tabellen (Customer1 und Customer2) verteilt sind. Die Abfrage gibt eine Sequenz von `Customer`-Objekten zurück.  
  
 [!code-csharp[DLinqQuerying#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#4)]
 [!code-vb[DLinqQuerying#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#4)]  
  
 Solange die Spaltennamen im tabellarischen Ergebnis den Spalteneigenschaften Ihrer Entitätsklasse entsprechen [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] erstellt die Objekte aus einer SQL-Abfrage.  
  
## <a name="example"></a>Beispiel  
 Die <xref:System.Data.Linq.DataContext.ExecuteQuery%2A>-Methode berücksichtigt auch Parameter. Verwenden Sie Code wie den folgenden, um eine parametrisierte Abfrage auszuführen.  
  
 [!code-csharp[DLinqQuerying#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#5)]
 [!code-vb[DLinqQuerying#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#5)]  
  
 Die Parameter werden im Abfragetext mithilfe der gleichen verschachtelten Schreibweise wie in `Console.WriteLine()` und `String.Format()` ausgedrückt. In der Tat `String.Format()` aufgerufen wird in der Abfragezeichenfolge, die Sie bereitstellen, ersetzen die Parameter durch erzeugte Parameternamen wie z. B. @p0, @p1 ..., @p(n).  
  
## <a name="see-also"></a>Siehe auch  
 [Hintergrundinformationen](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [Abfragen der Datenbank](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
