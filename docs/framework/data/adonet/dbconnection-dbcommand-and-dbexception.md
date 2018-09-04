---
title: "\"DbConnection\", \"DbCommand\" und \"DbException\""
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 58aab611-7e6f-4749-b983-28ab7ae87dbe
ms.openlocfilehash: 1bbc155e1c77c3512455816d2b66e7d4b55e57b7
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43508172"
---
# <a name="dbconnection-dbcommand-and-dbexception"></a><span data-ttu-id="3588e-102">"DbConnection", "DbCommand" und "DbException"</span><span class="sxs-lookup"><span data-stu-id="3588e-102">DbConnection, DbCommand and DbException</span></span>
<span data-ttu-id="3588e-103">Wenn Sie eine <xref:System.Data.Common.DbProviderFactory> und eine <xref:System.Data.Common.DbConnection> erstellt haben, können Sie mithilfe von Befehlen und Datenlesern Daten aus der Datenquelle abrufen.</span><span class="sxs-lookup"><span data-stu-id="3588e-103">Once you have created a <xref:System.Data.Common.DbProviderFactory> and a <xref:System.Data.Common.DbConnection>, you can then work with commands and data readers to retrieve data from the data source.</span></span>  
  
## <a name="retrieving-data-example"></a><span data-ttu-id="3588e-104">Abrufen eines Datenbeispiels</span><span class="sxs-lookup"><span data-stu-id="3588e-104">Retrieving Data Example</span></span>  
 <span data-ttu-id="3588e-105">In diesem Beispiel wird ein `DbConnection`-Objekt als Argument verwendet.</span><span class="sxs-lookup"><span data-stu-id="3588e-105">This example takes a `DbConnection` object as an argument.</span></span> <span data-ttu-id="3588e-106">Zum Auswählen der Daten aus der <legacyBold>Categories</legacyBold>-Tabelle wird ein <xref:System.Data.Common.DbCommand> erstellt. Dazu wird der <xref:System.Data.Common.DbCommand.CommandText%2A> auf eine SQL SELECT-Anweisung gesetzt.</span><span class="sxs-lookup"><span data-stu-id="3588e-106">A <xref:System.Data.Common.DbCommand> is created to select data from the Categories table by setting the <xref:System.Data.Common.DbCommand.CommandText%2A> to a SQL SELECT statement.</span></span> <span data-ttu-id="3588e-107">Der Code geht davon aus, dass die <legacyBold>Categories</legacyBold>-Tabelle in der Datenquelle vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="3588e-107">The code assumes that the Categories table exists at the data source.</span></span> <span data-ttu-id="3588e-108">Die Verbindung wird geöffnet, und die Daten werden mit einem <xref:System.Data.Common.DbDataReader> abgerufen.</span><span class="sxs-lookup"><span data-stu-id="3588e-108">The connection is opened and the data is retrieved using a <xref:System.Data.Common.DbDataReader>.</span></span>  
  
 [!code-csharp[DataWorks DbProviderFactories.DbCommandData#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbCommandData/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories.DbCommandData#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbCommandData/VB/source.vb#1)]  
  
## <a name="executing-a-command-example"></a><span data-ttu-id="3588e-109">Ausführen eines Befehlsbeispiels</span><span class="sxs-lookup"><span data-stu-id="3588e-109">Executing a Command Example</span></span>  
 <span data-ttu-id="3588e-110">In diesem Beispiel wird ein `DbConnection`-Objekt als Argument verwendet.</span><span class="sxs-lookup"><span data-stu-id="3588e-110">This example takes a `DbConnection` object as an argument.</span></span> <span data-ttu-id="3588e-111">Wenn die `DbConnection` gültig ist, wird die Verbindung geöffnet, und es wird ein <xref:System.Data.Common.DbCommand> erstellt und ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3588e-111">If the `DbConnection` is valid, the connection is opened and a <xref:System.Data.Common.DbCommand> is created and executed.</span></span> <span data-ttu-id="3588e-112">Der <xref:System.Data.Common.DbCommand.CommandText%2A> wird auf eine SQL INSERT-Anweisung gesetzt, die in der <legacyBold>Categories</legacyBold>-Tabelle der <legacyBold>Northwind</legacyBold>-Datenbank eine Einfügung vornimmt.</span><span class="sxs-lookup"><span data-stu-id="3588e-112">The <xref:System.Data.Common.DbCommand.CommandText%2A> is set to a SQL INSERT statement that performs an insert to the Categories table in the Northwind database.</span></span> <span data-ttu-id="3588e-113">Der Code geht davon aus, dass die <legacyBold>Northwind</legacyBold>-Datenbank in der Datenquelle vorhanden und die in der INSERT-Anweisung verwendete SQL-Syntax für den angegebenen Anbieter gültig ist.</span><span class="sxs-lookup"><span data-stu-id="3588e-113">The code assumes that the Northwind database exists at the data source, and that the SQL syntax used in the INSERT statement is valid for the specified provider.</span></span> <span data-ttu-id="3588e-114">Fehler, die in der Datenquelle auftreten, werden vom <xref:System.Data.Common.DbException>-Codeblock behandelt, alle anderen Ausnahmen im <xref:System.Exception>-Block.</span><span class="sxs-lookup"><span data-stu-id="3588e-114">Errors occurring at the data source are handled by the <xref:System.Data.Common.DbException> code block, and all other exceptions are handled in the <xref:System.Exception> block.</span></span>  
  
 [!code-csharp[DataWorks DbProviderFactories.DbCommand#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbCommand/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories.DbCommand#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbCommand/VB/source.vb#1)]  
  
## <a name="handling-data-errors-with-dbexception"></a><span data-ttu-id="3588e-115">Behandeln von Datenfehlern mit "DbException"</span><span class="sxs-lookup"><span data-stu-id="3588e-115">Handling Data Errors with DbException</span></span>  
 <span data-ttu-id="3588e-116">Die <xref:System.Data.Common.DbException>-Klasse ist die Basisklasse für alle im Namen einer Datenquelle ausgelösten Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="3588e-116">The <xref:System.Data.Common.DbException> class is the base class for all exceptions thrown on behalf of a data source.</span></span> <span data-ttu-id="3588e-117">Sie können diese Klasse in Ihrem Ausnahmebehandlungscode verwenden, um Ausnahmen zu behandeln, ohne dazu auf eine spezielle Ausnahmeklasse zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="3588e-117">You can use it in your exception handling code to handle exceptions thrown by different providers without having to reference a specific exception class.</span></span> <span data-ttu-id="3588e-118">Das folgende Codefragment zeigt, wie Sie mithilfe von <xref:System.Data.Common.DbException> und unter Verwendung der Eigenschaften <xref:System.Exception.GetType%2A>, <xref:System.Exception.Source%2A>, <xref:System.Runtime.InteropServices.ExternalException.ErrorCode%2A> und <xref:System.Exception.Message%2A> Fehlerinformationen anzeigen können, die von der Datenquelle zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="3588e-118">The following code fragment demonstrates how to use <xref:System.Data.Common.DbException> to display error information returned by the data source using <xref:System.Exception.GetType%2A>, <xref:System.Exception.Source%2A>, <xref:System.Runtime.InteropServices.ExternalException.ErrorCode%2A>, and <xref:System.Exception.Message%2A> properties.</span></span> <span data-ttu-id="3588e-119">Die Ausgabe umfasst folgende Informationen: Art des Fehlers, Quelle des Fehlers mit dem Namen des Anbieters, Fehlercode und die entsprechende Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="3588e-119">The output will display the type of error, the source indicating the provider name, an error code, and the message associated with the error.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3588e-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3588e-120">See Also</span></span>  
 [<span data-ttu-id="3588e-121">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="3588e-121">DbProviderFactories</span></span>](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 [<span data-ttu-id="3588e-122">Abrufen einer DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="3588e-122">Obtaining a DbProviderFactory</span></span>](../../../../docs/framework/data/adonet/obtaining-a-dbproviderfactory.md)  
 [<span data-ttu-id="3588e-123">Ändern von Daten mit DbDataAdapter</span><span class="sxs-lookup"><span data-stu-id="3588e-123">Modifying Data with a DbDataAdapter</span></span>](../../../../docs/framework/data/adonet/modifying-data-with-a-dbdataadapter.md)  
 [<span data-ttu-id="3588e-124">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="3588e-124">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
