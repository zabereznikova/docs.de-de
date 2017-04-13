---
title: "Vorgehensweise: Einf&#252;gen von Zeilen in die Datenbank | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 44d99680-69c7-4879-a732-f6771b334211
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Vorgehensweise: Einf&#252;gen von Zeilen in die Datenbank
Sie können Zeilen in eine Datenbank einfügen, indem Sie der zugehörigen [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601>\-Auflistung Objekte hinzufügen und dann die Änderungen an die Datenbank übergeben. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] übersetzt Ihre Änderungen in die entsprechenden SQL `INSERT`\-Befehle.  
  
> [!NOTE]
>  Sie können [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]\-Standardmethoden für die Datenbankoperationen `Insert`, `Update` und `Delete` überschreiben.  Weitere Informationen finden Sie unter [Anpassen von Insert\-, Update\- und Delete\-Operationen](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).  
>   
>  Entwickler, die mit [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] arbeiten, können mithilfe von [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] gespeicherte Prozeduren für denselben Zweck entwickeln.  
  
 In den folgenden Schritten wird davon ausgegangen, dass Sie ein gültiger <xref:System.Data.Linq.DataContext> mit der Datenbank Northwind verbindet.  Weitere Informationen finden Sie unter [Vorgehensweise: Herstellen einer Verbindung zu einer Datenbank](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).  
  
### So fügen Sie eine Zeile in die Datenbank ein  
  
1.  Erstellen Sie ein neues Objekt, das die zu übermittelnden Spaltendaten enthält.  
  
2.  Fügen Sie das neue Objekt der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]\-Auflistung `Table` hinzu, die der Zieltabelle in der Datenbank zugeordnet ist.  
  
3.  Übergeben Sie die Änderung an die Datenbank.  
  
## Beispiel  
 Im folgenden Codebeispiel wird ein neues Objekt des Typs `Order` erstellt und mit entsprechenden Werten aufgefüllt.  Anschließend wird das neue Objekt der `Order`\-Auflistung hinzugefügt.  Schließlich wird die Änderung an der Datenbank als neue Zeile in der `Orders`\-Tabelle übergeben.  
  
 [!code-csharp[System.Data.Linq.Table#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.Table#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#1)]  
  
## Siehe auch  
 [Vorgehensweise: Verwalten von Änderungskonflikten](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)   
 [DataContext\-Methoden \(O\/R\-Designer\)](../Topic/DataContext%20Methods%20\(O-R%20Designer\).md)   
 [Vorgehensweise: Zuweisen von gespeicherten Prozeduren zur Durchführung von Update\-, Einfüge\- und Löschvorgängen \(O\/R\-Designer\)](../Topic/How%20to:%20Assign%20stored%20procedures%20to%20perform%20updates,%20inserts,%20and%20deletes%20\(O-R%20Designer\).md)   
 [Vornehmen und Übergeben von Datenänderungen](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)