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
# <a name="modifying-data-with-stored-procedures"></a><span data-ttu-id="90eb5-102">Ändern von Daten mit gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="90eb5-102">Modifying Data with Stored Procedures</span></span>

<span data-ttu-id="90eb5-103">Gespeicherte Prozeduren können Daten als Eingabeparameter akzeptieren und Daten als Ausgabeparameter, Resultsets oder Rückgabewerte zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="90eb5-103">Stored procedures can accept data as input parameters and can return data as output parameters, result sets, or return values.</span></span> <span data-ttu-id="90eb5-104">Im Beispiel unten wird gezeigt, wie ADO.NET Eingabeparameter, Ausgabeparameter und Rückgabewerte sendet und empfängt.</span><span class="sxs-lookup"><span data-stu-id="90eb5-104">The sample below illustrates how ADO.NET sends and receives input parameters, output parameters, and return values.</span></span> <span data-ttu-id="90eb5-105">Das Beispiel fügt in eine Tabelle, deren Primärschlüsselspalte eine Identitätsspalte in einer SQL Server-Datenbank ist, einen neuen Datensatz ein.</span><span class="sxs-lookup"><span data-stu-id="90eb5-105">The example inserts a new record into a table where the primary key column is an identity column in a SQL Server database.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="90eb5-106">Wenn Sie zum Bearbeiten oder Löschen von Daten mit einem <xref:System.Data.SqlClient.SqlDataAdapter> gespeicherte SQL Server-Prozeduren verwenden, müssen Sie sicherstellen, dass in der Definition der gespeicherten Prozedur nicht SET NOCOUNT ON verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="90eb5-106">If you are using SQL Server stored procedures to edit or delete data using a <xref:System.Data.SqlClient.SqlDataAdapter>, make sure that you do not use SET NOCOUNT ON in the stored procedure definition.</span></span> <span data-ttu-id="90eb5-107">Anderenfalls ist die zurückgegebene Anzahl der betroffenen Zeilen gleich Null (0), was der `DataAdapter` als Parallelitätskonflikt interpretiert.</span><span class="sxs-lookup"><span data-stu-id="90eb5-107">This causes the rows affected count returned to be zero, which the `DataAdapter` interprets as a concurrency conflict.</span></span> <span data-ttu-id="90eb5-108">In diesem Fall wird eine <xref:System.Data.DBConcurrencyException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="90eb5-108">In this event, a <xref:System.Data.DBConcurrencyException> will be thrown.</span></span>  
  
## <a name="example"></a><span data-ttu-id="90eb5-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="90eb5-109">Example</span></span>  

 <span data-ttu-id="90eb5-110">Im Beispiel wird die folgende gespeicherte Prozedur verwendet, um eine neue Kategorie in die Tabelle " **Northwind** **Categories** " einzufügen.</span><span class="sxs-lookup"><span data-stu-id="90eb5-110">The sample uses the following stored procedure to insert a new category into the **Northwind** **Categories** table.</span></span> <span data-ttu-id="90eb5-111">Die gespeicherte Prozedur übernimmt den Wert in der **CategoryName** -Spalte als Eingabeparameter und verwendet die SCOPE_IDENTITY ()-Funktion, um den neuen Wert des Identitäts Felds ( **CategoryID**) abzurufen und in einem Output-Parameter zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="90eb5-111">The stored procedure takes the value in the **CategoryName** column as an input parameter and uses the SCOPE_IDENTITY() function to retrieve the new value of the identity field, **CategoryID**, and return it in an output parameter.</span></span> <span data-ttu-id="90eb5-112">Die Return-Anweisung verwendet die @- @ROWCOUNT Funktion, um die Anzahl der eingefügten Zeilen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="90eb5-112">The RETURN statement uses the @@ROWCOUNT function to return the number of rows inserted.</span></span>  
  
```sql
CREATE PROCEDURE dbo.InsertCategory  
  @CategoryName nvarchar(15),  
  @Identity int OUT  
AS  
INSERT INTO Categories (CategoryName) VALUES(@CategoryName)  
SET @Identity = SCOPE_IDENTITY()  
RETURN @@ROWCOUNT  
```  
  
 <span data-ttu-id="90eb5-113">Im folgenden Codebeispiel wird die oben beschriebene gespeicherte Prozedur `InsertCategory` als Quelle für den <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A> des <xref:System.Data.SqlClient.SqlDataAdapter> verwendet.</span><span class="sxs-lookup"><span data-stu-id="90eb5-113">The following code example uses the `InsertCategory` stored procedure shown above as the source for the <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A> of the <xref:System.Data.SqlClient.SqlDataAdapter>.</span></span> <span data-ttu-id="90eb5-114">Der `@Identity`-Ausgabeparameter erscheint im <xref:System.Data.DataSet>, nachdem der Datensatz in die Datenbank eingefügt und die `Update`-Methode des <xref:System.Data.SqlClient.SqlDataAdapter> aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="90eb5-114">The `@Identity` output parameter will be reflected in the <xref:System.Data.DataSet> after the record has been inserted into the database when the `Update` method of the <xref:System.Data.SqlClient.SqlDataAdapter> is called.</span></span> <span data-ttu-id="90eb5-115">Der Code ruft auch den Rückgabewert ab.</span><span class="sxs-lookup"><span data-stu-id="90eb5-115">The code also retrieves the return value.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="90eb5-116">Wenn Sie verwenden <xref:System.Data.OleDb.OleDbDataAdapter> , müssen Sie Parameter mit einem <xref:System.Data.ParameterDirection> von **ReturnValue** vor den anderen Parametern angeben.</span><span class="sxs-lookup"><span data-stu-id="90eb5-116">When using the <xref:System.Data.OleDb.OleDbDataAdapter>, you must specify parameters with a <xref:System.Data.ParameterDirection> of **ReturnValue** before the other parameters.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.SprocIdentityReturn#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.SprocIdentityReturn/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.SprocIdentityReturn#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.SprocIdentityReturn/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="90eb5-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="90eb5-117">See also</span></span>

- [<span data-ttu-id="90eb5-118">Abrufen und Ändern von Daten in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="90eb5-118">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="90eb5-119">"DataAdapters" und "DataReaders"</span><span class="sxs-lookup"><span data-stu-id="90eb5-119">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="90eb5-120">Ausführen eines Befehls</span><span class="sxs-lookup"><span data-stu-id="90eb5-120">Executing a Command</span></span>](executing-a-command.md)
- [<span data-ttu-id="90eb5-121">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="90eb5-121">ADO.NET Overview</span></span>](ado-net-overview.md)
