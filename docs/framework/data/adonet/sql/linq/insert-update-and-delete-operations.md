---
title: Insert-, Update- und Delete-Operationen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 26a43a4f-83c9-4732-806d-bb23aad0ff6b
ms.openlocfilehash: e0d2889ef0aeab4a1ca60b1b44a067a221ab541c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956840"
---
# <a name="insert-update-and-delete-operations"></a>Insert-, Update- und Delete-Operationen
Sie führen die Operationen `Insert`, `Update` und `Delete` in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] aus, indem Sie Objekte dem Objektmodell hinzufügen, diese ändern oder entfernen. Standardmäßig übersetzt [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Ihre Aktionen in SQL und übergibt die Änderungen an die Datenbank.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]bietet maximale Flexibilität bei der Bearbeitung und Beibehaltung von Änderungen, die Sie an ihren Objekten vorgenommen haben. Sobald Entitätsobjekte zur Verfügung stehen (entweder durch Abrufen in einer Abfrage oder durch Neuzusammenstellung), können Sie diese wie typische Objekte in Ihrer Anwendung ändern. Das heißt, Sie können ihre Werte ändern, Sie ihren Sammlungen hinzufügen und Sie aus ihren Sammlungen entfernen. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] verfolgt Ihre Änderungen und kann diese zurück in die Datenbank übertragen, wenn Sie <xref:System.Data.Linq.DataContext.SubmitChanges%2A> aufrufen.  
  
> [!NOTE]
> Kaskadierte Löschvorgänge werden von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] nicht unterstützt bzw. erkannt. Wenn Sie eine Zeile in einer Tabelle löschen möchten, für die Einschränkungen gelten, müssen Sie entweder die `ON DELETE CASCADE` Regel in der FOREIGN KEY-Einschränkung in der Datenbank festlegen oder ihren eigenen Code verwenden, um zuerst die untergeordneten Objekte zu löschen, die das Löschen des übergeordneten Objekts verhindern. Andernfalls wird eine Ausnahme ausgelöst. Weitere Informationen finden Sie unter [Vorgehensweise: Löschen von Zeilen aus der](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md)Datenbank.  
  
 Die folgenden Auszüge verwenden die `Customer`-Klasse und die `Order`-Klasse aus der Beispieldatenbank Northwind. Klassendefinitionen werden zur besseren Übersicht nicht angezeigt.  
  
 [!code-csharp[DLinqCRUDOps#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCRUDOps/cs/Program.cs#1)]
 [!code-vb[DLinqCRUDOps#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCRUDOps/vb/Module1.vb#1)]  
  
 Wenn Sie <xref:System.Data.Linq.DataContext.SubmitChanges%2A> aufrufen, übernimmt [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] automatisch die Erzeugung und Ausführung der SQL-Befehle, die zur Übertragung Ihrer Änderungen in die Datenbank erforderlich sind.  
  
> [!NOTE]
> Sie können dieses Verhalten überschreiben, indem Sie Ihre eigene Logik verwenden (typischerweise in Form einer gespeicherten Prozedur). Weitere Informationen finden Sie unter [Zuständigkeiten des Entwicklers beim Überschreiben des Standard Verhaltens](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md).  
>   
>  Entwickler, die Visual Studio verwenden, können den objektrelationaler Designer verwenden, um gespeicherte Prozeduren zu diesem Zweck zu entwickeln.  
  
## <a name="see-also"></a>Siehe auch

- [Downloading Sample Databases (Herunterladen von Beispieldatenbanken)](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
- [Anpassen von Insert-, Update- und Delete-Operationen](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)
