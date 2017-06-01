---
title: "Insert-, Update- und Delete-Operationen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 26a43a4f-83c9-4732-806d-bb23aad0ff6b
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Insert-, Update- und Delete-Operationen
Sie führen die Operationen `Insert`, `Update` und `Delete` in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] aus, indem Sie Objekte dem Objektmodell hinzufügen, diese ändern oder entfernen.  Standardmäßig übersetzt [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Ihre Aktionen in SQL und übergibt die Änderungen an die Datenbank.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] bietet maximale Flexibilität für die Bearbeitung und den Erhalt von Änderungen, die Sie an Ihren Objekten vorgenommen haben.  Sobald Entitätsobjekte zur Verfügung stehen \(entweder durch Abrufen in einer Abfrage oder durch Neuzusammenstellung\), können Sie diese wie typische Objekte in Ihrer Anwendung ändern.  Dies bedeutet, dass Sie deren Werte ändern, die Objekte Auflistungen hinzufügen und aus diesen entfernen können.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] verfolgt Ihre Änderungen und kann diese zurück in die Datenbank übertragen, wenn Sie <xref:System.Data.Linq.DataContext.SubmitChanges%2A> aufrufen.  
  
> [!NOTE]
>  Kaskadierte Löschvorgänge werden von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] nicht unterstützt bzw. erkannt.  Wenn Sie eine Zeile in einer Tabelle löschen möchten, für die Einschränkungen gelten, legen Sie die `ON DELETE CASCADE`\-Regel in der Fremdschlüsseleinschränkung in der Datenbank fest, oder verwenden Sie eigenen Code, um zunächst die untergeordneten Objekte zu löschen, die das Löschen des übergeordneten Objekts verhindern. Andernfalls wird eine Ausnahme ausgelöst.  Weitere Informationen finden Sie unter [Vorgehensweise: Löschen von Zeilen aus der Datenbank](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md).  
  
 Die folgenden Auszüge verwenden die `Customer`\-Klasse und die `Order`\-Klasse aus der Beispieldatenbank Northwind.  Klassendefinitionen werden zur besseren Übersicht nicht angezeigt.  
  
 [!code-csharp[DLinqCRUDOps#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCRUDOps/cs/Program.cs#1)]
 [!code-vb[DLinqCRUDOps#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCRUDOps/vb/Module1.vb#1)]  
  
 Wenn Sie <xref:System.Data.Linq.DataContext.SubmitChanges%2A> aufrufen, übernimmt [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] automatisch die Erzeugung und Ausführung der SQL\-Befehle, die zur Übertragung Ihrer Änderungen in die Datenbank erforderlich sind.  
  
> [!NOTE]
>  Sie können dieses Verhalten überschreiben, indem Sie Ihre eigene Logik verwenden \(typischerweise in Form einer gespeicherten Prozedur\).  Weitere Informationen finden Sie unter [Aufgaben des Entwicklers beim Überschreiben des Standardverhaltens](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md).  
>   
>  Entwickler, die mit [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] arbeiten, können mithilfe von [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] gespeicherte Prozeduren zu diesem Zweck entwickeln.  
  
## Siehe auch  
 [Herunterladen von Beispieldatenbanken](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)   
 [Anpassen von Insert\-, Update\- und Delete\-Operationen](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)