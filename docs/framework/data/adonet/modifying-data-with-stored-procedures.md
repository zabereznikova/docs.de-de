---
title: "Ändern von Daten mit gespeicherten Prozeduren"
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
ms.assetid: 7d8e9a46-1af6-4a02-bf61-969d77ae07e0
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 1f8f0c37e5ac84d878f1d443d2bcc1e8ded099a6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="modifying-data-with-stored-procedures"></a>Ändern von Daten mit gespeicherten Prozeduren
Gespeicherte Prozeduren können Daten als Eingabeparameter akzeptieren und Daten als Ausgabeparameter, Resultsets oder Rückgabewerte zurückgeben. Im Beispiel unten wird gezeigt, wie ADO.NET Eingabeparameter, Ausgabeparameter und Rückgabewerte sendet und empfängt. Das Beispiel fügt in eine Tabelle, deren Primärschlüsselspalte eine Identitätsspalte in einer SQL Server-Datenbank ist, einen neuen Datensatz ein.  
  
> [!NOTE]
>  Wenn Sie zum Bearbeiten oder Löschen von Daten mit einem <xref:System.Data.SqlClient.SqlDataAdapter> gespeicherte SQL Server-Prozeduren verwenden, müssen Sie sicherstellen, dass in der Definition der gespeicherten Prozedur nicht SET NOCOUNT ON verwendet wird. Anderenfalls ist die zurückgegebene Anzahl der betroffenen Zeilen gleich Null (0), was der `DataAdapter` als Parallelitätskonflikt interpretiert. In diesem Fall wird eine <xref:System.Data.DBConcurrencyException> ausgelöst.  
  
## <a name="example"></a>Beispiel  
 Das Beispiel verwendet die folgende gespeicherte Prozedur zum Einfügen einer neuen Kategorie in den **Northwind** **Kategorien** Tabelle. Die gespeicherte Prozedur nimmt den Wert in der **CategoryName** Spalte als Eingabeparameter, verwendet die SCOPE_IDENTITY()-Funktion,-Funktion zum Abrufen des neuen Werts des Identitätsfelds **CategoryID**, löschen und Gerät in einer Output-Parameter. Die RETURN-Anweisung verwendet die @@ROWCOUNT Funktion, um die Anzahl der eingefügten Zeilen zurück.  
  
```  
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
>  Bei Verwendung der <xref:System.Data.OleDb.OleDbDataAdapter>, geben Sie Parameter mit einem <xref:System.Data.ParameterDirection> von **ReturnValue** vor den anderen Parametern.  
  
 [!code-csharp[DataWorks SqlClient.SprocIdentityReturn#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.SprocIdentityReturn/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.SprocIdentityReturn#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.SprocIdentityReturn/VB/source.vb#1)]  
  
## <a name="see-also"></a>Siehe auch  
 [Abrufen und Ändern von Daten in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 ["DataAdapters" und "DataReaders"](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [Ausführen eines Befehls](../../../../docs/framework/data/adonet/executing-a-command.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
