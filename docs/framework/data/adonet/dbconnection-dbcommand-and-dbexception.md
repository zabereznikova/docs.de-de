---
title: "\"DbConnection\", \"DbCommand\" und \"DbException\""
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 58aab611-7e6f-4749-b983-28ab7ae87dbe
ms.openlocfilehash: 3075999c15fccc3a41c191297a146c362b3638e8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183324"
---
# <a name="dbconnection-dbcommand-and-dbexception"></a>"DbConnection", "DbCommand" und "DbException"

Wenn Sie eine <xref:System.Data.Common.DbProviderFactory> und eine <xref:System.Data.Common.DbConnection> erstellt haben, können Sie mithilfe von Befehlen und Datenlesern Daten aus der Datenquelle abrufen.  
  
## <a name="retrieving-data-example"></a>Abrufen eines Datenbeispiels  

 In diesem Beispiel wird ein `DbConnection`-Objekt als Argument verwendet. Zum Auswählen der Daten aus der &lt;legacyBold&gt;Categories&lt;/legacyBold&gt;-Tabelle wird ein <xref:System.Data.Common.DbCommand> erstellt. Dazu wird der <xref:System.Data.Common.DbCommand.CommandText%2A> auf eine SQL SELECT-Anweisung gesetzt. Der Code geht davon aus, dass die &lt;legacyBold&gt;Categories&lt;/legacyBold&gt;-Tabelle in der Datenquelle vorhanden ist. Die Verbindung wird geöffnet, und die Daten werden mit einem <xref:System.Data.Common.DbDataReader> abgerufen.  
  
 [!code-csharp[DataWorks DbProviderFactories.DbCommandData#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbCommandData/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories.DbCommandData#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbCommandData/VB/source.vb#1)]  
  
## <a name="executing-a-command-example"></a>Ausführen eines Befehlsbeispiels  

 In diesem Beispiel wird ein `DbConnection`-Objekt als Argument verwendet. Wenn die `DbConnection` gültig ist, wird die Verbindung geöffnet, und es wird ein <xref:System.Data.Common.DbCommand> erstellt und ausgeführt. Der <xref:System.Data.Common.DbCommand.CommandText%2A> wird auf eine SQL INSERT-Anweisung gesetzt, die in der &lt;legacyBold&gt;Categories&lt;/legacyBold&gt;-Tabelle der &lt;legacyBold&gt;Northwind&lt;/legacyBold&gt;-Datenbank eine Einfügung vornimmt. Der Code geht davon aus, dass die Northwind-Datenbank in der Datenquelle vorhanden und die in der INSERT-Anweisung verwendete SQL-Syntax für den angegebenen Anbieter gültig ist. Fehler, die in der Datenquelle auftreten, werden vom <xref:System.Data.Common.DbException>-Codeblock behandelt, alle anderen Ausnahmen im <xref:System.Exception>-Block.  
  
 [!code-csharp[DataWorks DbProviderFactories.DbCommand#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbCommand/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories.DbCommand#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbCommand/VB/source.vb#1)]  
  
## <a name="handling-data-errors-with-dbexception"></a>Behandeln von Datenfehlern mit "DbException"  

 Die <xref:System.Data.Common.DbException>-Klasse ist die Basisklasse für alle im Namen einer Datenquelle ausgelösten Ausnahmen. Sie können diese Klasse in Ihrem Ausnahmebehandlungscode verwenden, um Ausnahmen zu behandeln, ohne dazu auf eine spezielle Ausnahmeklasse zu verweisen. Das folgende Codefragment zeigt, wie Sie mithilfe von <xref:System.Data.Common.DbException> und unter Verwendung der Eigenschaften <xref:System.Exception.GetType%2A>, <xref:System.Exception.Source%2A>, <xref:System.Runtime.InteropServices.ExternalException.ErrorCode%2A> und <xref:System.Exception.Message%2A> Fehlerinformationen anzeigen können, die von der Datenquelle zurückgegeben werden. Die Ausgabe umfasst folgende Informationen: Art des Fehlers, Quelle des Fehlers mit dem Namen des Anbieters, Fehlercode und die entsprechende Fehlermeldung.  
  
```vb  
Try  
    ' Do work here.  
Catch ex As DbException  
    ' Display information about the exception.  
    Console.WriteLine("GetType: {0}", ex.GetType())  
    Console.WriteLine("Source: {0}", ex.Source)  
    Console.WriteLine("ErrorCode: {0}", ex.ErrorCode)  
    Console.WriteLine("Message: {0}", ex.Message)  
Finally  
    ' Perform cleanup here.  
End Try  
```  
  
```csharp  
try  
{  
    // Do work here.  
}  
catch (DbException ex)  
{  
    // Display information about the exception.  
    Console.WriteLine("GetType: {0}", ex.GetType());  
    Console.WriteLine("Source: {0}", ex.Source);  
    Console.WriteLine("ErrorCode: {0}", ex.ErrorCode);  
    Console.WriteLine("Message: {0}", ex.Message);  
}  
finally  
{  
    // Perform cleanup here.  
}  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [DbProviderFactories](dbproviderfactories.md)
- [Abrufen einer "DbProviderFactory"](obtaining-a-dbproviderfactory.md)
- [Ändern von Daten mit "DbDataAdapter"](modifying-data-with-a-dbdataadapter.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
