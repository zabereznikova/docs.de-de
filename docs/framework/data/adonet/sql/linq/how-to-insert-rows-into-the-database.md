---
title: 'Vorgehensweise: Einfügen von Zeilen in der Datenbank'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 44d99680-69c7-4879-a732-f6771b334211
ms.openlocfilehash: 7c685d6e077c255c31d7aeec0594db9df721a21f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54507264"
---
# <a name="how-to-insert-rows-into-the-database"></a>Vorgehensweise: Einfügen von Zeilen in der Datenbank
Einfügen von Zeilen in einer Datenbank durch Hinzufügen von Objekten an die zugeordnete [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> Sammlung und übermitteln Sie dann die Änderungen an der Datenbank. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] übersetzt Ihre Änderungen in die entsprechenden SQL `INSERT` Befehle.  
  
> [!NOTE]
>  Sie können [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Standardmethoden für die Datenbankoperationen `Insert`, `Update` und `Delete` überschreiben. Weitere Informationen finden Sie unter [Anpassen von INSERT-, Update- und Delete-Operationen](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).  
>   
>  Können Entwickler mithilfe von Visual Studio die [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] gespeicherte Prozeduren für denselben Zweck entwickeln.  
  
 In den folgenden Schritten wird davon ausgegangen, dass Sie ein gültiger <xref:System.Data.Linq.DataContext> mit der Datenbank Northwind verbindet. Weitere Informationen finden Sie unter [Vorgehensweise: Herstellen einer Datenbankverbindung](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).  
  
### <a name="to-insert-a-row-into-the-database"></a>So fügen Sie eine Zeile in die Datenbank ein  
  
1.  Erstellen Sie ein neues Objekt, das die zu übermittelnden Spaltendaten enthält.  
  
2.  Fügen Sie das neue Objekt der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] `Table` Auflistung mit der Zieltabelle in der Datenbank zugeordnet ist.  
  
3.  Übergeben Sie die Änderung an die Datenbank.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird ein neues Objekt des Typs `Order` erstellt und mit entsprechenden Werten aufgefüllt. Anschließend wird das neue Objekt der `Order`-Auflistung hinzugefügt. Schließlich wird die Änderung an der Datenbank als neue Zeile in der `Orders`-Tabelle übergeben.  
  
 [!code-csharp[System.Data.Linq.Table#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.Table#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#1)]  
  
## <a name="see-also"></a>Siehe auch
- [Vorgehensweise: Verwalten von Änderungskonflikten](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
- [DataContext-Methoden (O/R-Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [Vorgehensweise: Zuweisen von gespeicherten Prozeduren zum Durchführen von Aktionen zum Aktualisieren, Einfügen und Löschen (O/R-Designer)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
- [Vornehmen und Übergeben von Datenänderungen](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
