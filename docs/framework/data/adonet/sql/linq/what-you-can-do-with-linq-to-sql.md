---
title: Möglichkeiten von LINQ to SQL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 061d98b2-baa7-4336-8ad2-c14de8134d91
ms.openlocfilehash: a2e65cb558eec3cec21ea0efbcc66bb8c56ec7b5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91163920"
---
# <a name="what-you-can-do-with-linq-to-sql"></a>Möglichkeiten von LINQ to SQL

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterstützt alle wichtigen Funktionen, die Sie als SQL-Entwickler erwarten würden. Sie können Informationen abfragen und Informationen in Tabellen einfügen, aktualisieren und löschen.  
  
## <a name="selecting"></a>Wählen Sie Folgendes aus:  

 Die Auswahl (*Projektion*) wird erreicht, indem Sie einfach eine LINQ-Abfrage in ihrer eigenen Programmiersprache schreiben und diese Abfrage anschließend ausführen, um die Ergebnisse abzurufen. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] übersetzt die Operationen in die entsprechenden SQL-Operationen, die bekannt sind. Weitere Informationen finden Sie unter [LINQ to SQL](index.md).  
  
 Im folgenden Beispiel werden die Firmennamen von Kunden aus London abgerufen und im Konsolenfenster dargestellt.  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## <a name="inserting"></a>Einfügen  

 Zum Ausführen eines SQL- `Insert`können Sie einfach dem erstellten Objektmodell Objekte hinzufügen und <xref:System.Data.Linq.DataContext.SubmitChanges%2A> im <xref:System.Data.Linq.DataContext>aufrufen.  
  
 Im folgenden Beispiel werden ein Kunde und Informationen zu diesem in die `Customers` -Tabelle eingefügt (mithilfe von <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>).  
  
 [!code-csharp[DLinqGettingStarted#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#2)]
 [!code-vb[DLinqGettingStarted#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#2)]  
  
## <a name="updating"></a>Wird aktualisiert  

 Zum Aktualisieren eines Datenbankeintrags mit `Update` , rufen Sie zuerst das Element ab und bearbeiten es direkt im Objektmodell. Nachdem Sie das Objekt geändert haben, rufen Sie <xref:System.Data.Linq.DataContext.SubmitChanges%2A> im <xref:System.Data.Linq.DataContext> auf, um die Datenbank zu aktualisieren.  
  
 Im folgenden Beispiel werden alle Kunden aus London abgerufen. Dann wird der Name des Orts von „London“ in „London - Metro“ geändert. Schließlich wird <xref:System.Data.Linq.DataContext.SubmitChanges%2A> aufgerufen, um die Änderungen an die Datenbank zu senden.  
  
 [!code-csharp[DLinqGettingStarted#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#3)]
 [!code-vb[DLinqGettingStarted#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#3)]  
  
## <a name="deleting"></a>Wird gelöscht  

 Wenn Sie ein Element löschen möchten ( `Delete` ), entfernen Sie dieses aus der entsprechenden Auflistung, und rufen Sie dann <xref:System.Data.Linq.DataContext.SubmitChanges%2A> im <xref:System.Data.Linq.DataContext> auf, um die Änderung zu bestätigen.  
  
> [!NOTE]
> Kaskadierte Löschvorgänge werden von[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] nicht erkannt. Wenn Sie eine Zeile in einer Tabelle löschen möchten, für die Einschränkungen gelten, finden Sie weitere Informationen unter Vorgehens [Weise: Löschen von Zeilen aus der Datenbank](how-to-delete-rows-from-the-database.md).  
  
 Im folgenden Beispiel wird der Kunde mit der `CustomerID``98128` aus der Datenbank abgerufen. Nach dem Bestätigen des Abrufs wird <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> aufgerufen, um das Objekt aus der Auflistung zu entfernen. Schließlich wird <xref:System.Data.Linq.DataContext.SubmitChanges%2A> aufgerufen, um die Löschung an die Datenbank weiterzuleiten.  
  
 [!code-csharp[DLinqGettingStarted#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#4)]
 [!code-vb[DLinqGettingStarted#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#4)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Programmierhandbuch](programming-guide.md)
- [Das LINQ to SQL-Objektmodell](the-linq-to-sql-object-model.md)
- [Erste Schritte](getting-started.md)
