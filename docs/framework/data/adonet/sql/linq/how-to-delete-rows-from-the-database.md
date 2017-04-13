---
title: "Vorgehensweise: L&#246;schen von Zeilen aus der Datenbank | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2144c99b-8055-4080-a5c6-1ea14335e2a3
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Vorgehensweise: L&#246;schen von Zeilen aus der Datenbank
Zeilen einer Datenbank können gelöscht werden, indem die entsprechenden [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]\-Objekte aus der mit der Tabelle verknüpften Auflistung entfernt werden. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] übersetzt die Änderungen in die entsprechenden SQL `DELETE`\-Befehle.  
  
 Kaskadierte Löschvorgänge werden von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] nicht unterstützt bzw. erkannt.  Wenn Sie eine Zeile in einer Tabelle löschen möchten, für die Einschränkungen gelten, führen Sie eines der folgenden Verfahren aus:  
  
-   Legen Sie die `ON DELETE CASCADE`\-Regel in der Fremdschlüsseleinschränkung in der Datenbank fest.  
  
-   Verwenden Sie eigenen Code, um zunächst die untergeordneten Objekte zu löschen, die das Löschen des übergeordneten Objekts verhindern.  
  
 Andernfalls wird eine Ausnahme ausgelöst.  Siehe das zweite Codebeispiel weiter unten in diesem Thema.  
  
> [!NOTE]
>  Sie können [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]\-Standardmethoden für die Datenbankoperationen `Insert`, `Update` und `Delete` überschreiben.  Weitere Informationen finden Sie unter [Anpassen von Insert\-, Update\- und Delete\-Operationen](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).  
>   
>  Entwickler, die mit [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] arbeiten, können mithilfe von [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] gespeicherte Prozeduren für denselben Zweck entwickeln.  
  
 In den folgenden Schritten wird davon ausgegangen, dass Sie ein gültiger <xref:System.Data.Linq.DataContext> mit der Datenbank Northwind verbindet.  Weitere Informationen finden Sie unter [Vorgehensweise: Herstellen einer Verbindung zu einer Datenbank](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).  
  
### So löschen Sie eine Zeile aus der Datenbank  
  
1.  Rufen Sie die zu löschende Zeile aus der Datenbank ab.  
  
2.  Rufen Sie die <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A>\-Methode auf.  
  
3.  Übergeben Sie die Änderung an die Datenbank.  
  
## Beispiel  
 Im ersten Codebeispiel wird die Datenbank nach Bestelldetails durchsucht, die sich auf die Bestellung 11000 beziehen. Diese Bestelldetails werden dann zum Löschen markiert und diese Änderungen an die Datenbank übergeben.  
  
 [!code-csharp[System.Data.Linq.Table#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#3)]
 [!code-vb[System.Data.Linq.Table#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#3)]  
  
## Beispiel  
 In diesem zweiten Beispiel besteht das Ziel darin, eine Bestellung \(10250\) zu entfernen.  Der Code durchsucht zunächst die `OrderDetails`\-Tabelle, um zu prüfen, ob die zu entfernende Bestellung untergeordnete Elemente enthält.  Wenn die Bestellung untergeordnete Elemente enthält, werden zunächst die untergeordneten Elemente und dann die Bestellung zum Entfernen markiert.  <xref:System.Data.Linq.DataContext> bringt die tatsächlichen Löschvorgänge in die richtige Reihenfolge, sodass die an die Datenbank übertragenen Löschbefehle die Datenbankbeschränkungen erfüllen.  
  
 [!code-csharp[DLinqCascadeWorkaround#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCascadeWorkaround/cs/Program.cs#1)]
 [!code-vb[DLinqCascadeWorkaround#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCascadeWorkaround/vb/Module1.vb#1)]  
  
## Siehe auch  
 [Vorgehensweise: Verwalten von Änderungskonflikten](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)   
 [Vorgehensweise: Zuweisen von gespeicherten Prozeduren zur Durchführung von Update\-, Einfüge\- und Löschvorgängen \(O\/R\-Designer\)](../Topic/How%20to:%20Assign%20stored%20procedures%20to%20perform%20updates,%20inserts,%20and%20deletes%20\(O-R%20Designer\).md)   
 [Vornehmen und Übergeben von Datenänderungen](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)