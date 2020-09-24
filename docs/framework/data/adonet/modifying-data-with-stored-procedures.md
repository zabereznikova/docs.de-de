---
title: Ändern von Daten mit gespeicherten Prozeduren
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7d8e9a46-1af6-4a02-bf61-969d77ae07e0
ms.openlocfilehash: 65116a48533fd6ce86894c6a4522929285f8e1f0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150751"
---
# <a name="modifying-data-with-stored-procedures"></a>Ändern von Daten mit gespeicherten Prozeduren

Gespeicherte Prozeduren können Daten als Eingabeparameter akzeptieren und Daten als Ausgabeparameter, Resultsets oder Rückgabewerte zurückgeben. Im Beispiel unten wird gezeigt, wie ADO.NET Eingabeparameter, Ausgabeparameter und Rückgabewerte sendet und empfängt. Das Beispiel fügt in eine Tabelle, deren Primärschlüsselspalte eine Identitätsspalte in einer SQL Server-Datenbank ist, einen neuen Datensatz ein.  
  
> [!NOTE]
> Wenn Sie zum Bearbeiten oder Löschen von Daten mit einem <xref:System.Data.SqlClient.SqlDataAdapter> gespeicherte SQL Server-Prozeduren verwenden, müssen Sie sicherstellen, dass in der Definition der gespeicherten Prozedur nicht SET NOCOUNT ON verwendet wird. Anderenfalls ist die zurückgegebene Anzahl der betroffenen Zeilen gleich Null (0), was der `DataAdapter` als Parallelitätskonflikt interpretiert. In diesem Fall wird eine <xref:System.Data.DBConcurrencyException> ausgelöst.  
  
## <a name="example"></a>Beispiel  

 Im Beispiel wird die folgende gespeicherte Prozedur verwendet, um eine neue Kategorie in die Tabelle " **Northwind** **Categories** " einzufügen. Die gespeicherte Prozedur übernimmt den Wert in der **CategoryName** -Spalte als Eingabeparameter und verwendet die SCOPE_IDENTITY ()-Funktion, um den neuen Wert des Identitäts Felds ( **CategoryID**) abzurufen und in einem Output-Parameter zurückzugeben. Die Return-Anweisung verwendet die @- @ROWCOUNT Funktion, um die Anzahl der eingefügten Zeilen zurückzugeben.  
  
```sql
CREATE PROCEDURE dbo.InsertCategory  
  @CategoryName nvarchar(15),  
  @Identity int OUT  
AS  
INSERT INTO Categories (CategoryName) VALUES(@CategoryName)  
SET @Identity = SCOPE_IDENTITY()  
RETURN @@ROWCOUNT  
```  
  
 Im folgenden Codebeispiel wird die oben beschriebene gespeicherte Prozedur `InsertCategory` als Quelle für den <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A> des <xref:System.Data.SqlClient.SqlDataAdapter> verwendet. Der `@Identity`-Ausgabeparameter erscheint im <xref:System.Data.DataSet>, nachdem der Datensatz in die Datenbank eingefügt und die `Update`-Methode des <xref:System.Data.SqlClient.SqlDataAdapter> aufgerufen wurde. Der Code ruft auch den Rückgabewert ab.  
  
> [!NOTE]
> Wenn Sie verwenden <xref:System.Data.OleDb.OleDbDataAdapter> , müssen Sie Parameter mit einem <xref:System.Data.ParameterDirection> von **ReturnValue** vor den anderen Parametern angeben.  
  
 [!code-csharp[DataWorks SqlClient.SprocIdentityReturn#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.SprocIdentityReturn/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.SprocIdentityReturn#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.SprocIdentityReturn/VB/source.vb#1)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Abrufen und Ändern von Daten in ADO.NET](retrieving-and-modifying-data.md)
- ["DataAdapters" und "DataReaders"](dataadapters-and-datareaders.md)
- [Ausführen eines Befehls](executing-a-command.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
