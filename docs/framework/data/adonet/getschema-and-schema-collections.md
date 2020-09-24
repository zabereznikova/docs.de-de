---
title: "\"GetSchema\" und Schemaauflistungen"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab93b89-1221-427c-84ad-04803b3c64b4
ms.openlocfilehash: cea9deb7fe019fea189a87fc08468d010929db9a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177448"
---
# <a name="getschema-and-schema-collections"></a><span data-ttu-id="63fdb-102">"GetSchema" und Schemaauflistungen</span><span class="sxs-lookup"><span data-stu-id="63fdb-102">GetSchema and Schema Collections</span></span>

<span data-ttu-id="63fdb-103">Die **Verbindungs** Klassen in den einzelnen .NET Framework verwalteten Anbietern implementieren eine **GetSchema** -Methode, die zum Abrufen von Schema Informationen über die derzeit verbundene Datenbank verwendet wird, und die Schema Informationen, die von der **GetSchema** -Methode zurückgegeben werden, werden in Form von angezeigt <xref:System.Data.DataTable> .</span><span class="sxs-lookup"><span data-stu-id="63fdb-103">The **Connection** classes in each of the .NET Framework managed providers implement a **GetSchema** method which is used to retrieve schema information about the database that is currently connected, and the schema information returned from the **GetSchema** method comes in the form of a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="63fdb-104">Bei der **GetSchema** -Methode handelt es sich um eine überladene Methode, die optionale Parameter zum Angeben der zurück zugebende Schema Auflistung und zum Einschränken der zurückgegebenen Informationsmenge bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="63fdb-104">The **GetSchema** method is an overloaded method that provides optional parameters for specifying the schema collection to return, and restricting the amount of information returned.</span></span>  
  
## <a name="specifying-the-schema-collections"></a><span data-ttu-id="63fdb-105">Angeben der Schemaauflistungen</span><span class="sxs-lookup"><span data-stu-id="63fdb-105">Specifying the Schema Collections</span></span>  

 <span data-ttu-id="63fdb-106">Der erste optionale Parameter der **GetSchema** -Methode ist der Sammlungs Name, der als Zeichenfolge angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="63fdb-106">The first optional parameter of the **GetSchema** method is the collection name which is specified as a string.</span></span> <span data-ttu-id="63fdb-107">Es gibt zwei Arten von Schemaauflistungen: allgemeine Schemaauflistungen, die von allen Anbietern verwendet werden, und besondere Schemaauflistungen, die für jeden Anbieter spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="63fdb-107">There are two types of schema collections: common schema collections that are common to all providers, and specific schema collections which are specific to each provider.</span></span>  
  
 <span data-ttu-id="63fdb-108">Sie können einen .NET Framework verwalteten Anbieter Abfragen, um die Liste der unterstützten Schema Auflistungen zu ermitteln, indem Sie die **GetSchema** -Methode ohne Argumente oder mit dem Schema Auflistungs Namen "MetaDataCollections" aufrufen.</span><span class="sxs-lookup"><span data-stu-id="63fdb-108">You can query a .NET Framework managed provider to determine the list of supported schema collections by calling the **GetSchema** method with no arguments, or with the schema collection name "MetaDataCollections".</span></span> <span data-ttu-id="63fdb-109">Dadurch wird <xref:System.Data.DataTable> mit einer Liste der unterstützten Schemaauflistungen, der Anzahl der von diesen Schemaauflistungen unterstützten Einschränkungen und der Anzahl der von diesen Schemaauflistungen verwendeten Bezeichnerteilen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="63fdb-109">This will return a <xref:System.Data.DataTable> with a list of the supported schema collections, the number of restrictions that they each support, and the number of identifier parts that they use.</span></span>  
  
### <a name="retrieving-schema-collections-example"></a><span data-ttu-id="63fdb-110">Beispiel zum Abrufen von Schemaauflistungen</span><span class="sxs-lookup"><span data-stu-id="63fdb-110">Retrieving Schema Collections Example</span></span>  

 <span data-ttu-id="63fdb-111">In den folgenden Beispielen wird veranschaulicht, wie die- <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> Methode der .NET Framework Datenanbieter für die SQL Server-Klasse verwendet wird <xref:System.Data.SqlClient.SqlConnection> , um Schema Informationen zu allen Tabellen abzurufen, die in der **AdventureWorks** -Beispieldatenbank enthalten sind:</span><span class="sxs-lookup"><span data-stu-id="63fdb-111">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database:</span></span>  
  
```vb  
Imports System.Data.SqlClient  
  
Module Module1  
   Sub Main()  
      Dim connectionString As String = GetConnectionString()  
      Using connection As New SqlConnection(connectionString)  
         'Connect to the database then retrieve the schema information.  
         connection.Open()  
         Dim table As DataTable = connection.GetSchema("Tables")  
  
         ' Display the contents of the table.  
         DisplayData(table)  
         Console.WriteLine("Press any key to continue.")  
         Console.ReadKey()  
      End Using  
   End Sub  
  
   Private Function GetConnectionString() As String  
      ' To avoid storing the connection string in your code,
      ' you can retrieve it from a configuration file.  
      Return "Data Source=(local);Database=AdventureWorks;" _  
         & "Integrated Security=true;"  
   End Function  
  
   Private Sub DisplayData(ByVal table As DataTable)  
      For Each row As DataRow In table.Rows  
         For Each col As DataColumn In table.Columns  
            Console.WriteLine("{0} = {1}", col.ColumnName, row(col))  
         Next  
         Console.WriteLine("============================")  
      Next  
   End Sub  
End Module  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlClient;  
  
class Program  
{  
  static void Main()  
  {  
  string connectionString = GetConnectionString();  
  using (SqlConnection connection = new SqlConnection(connectionString))  
  {  
   // Connect to the database then retrieve the schema information.  
   connection.Open();  
   DataTable table = connection.GetSchema("Tables");  
  
   // Display the contents of the table.  
   DisplayData(table);  
   Console.WriteLine("Press any key to continue.");  
   Console.ReadKey();  
   }  
 }  
  
  private static string GetConnectionString()  
  {  
   // To avoid storing the connection string in your code,  
   // you can retrieve it from a configuration file.  
   return "Data Source=(local);Database=AdventureWorks;" +  
      "Integrated Security=true;";  
  }  
  
  private static void DisplayData(System.Data.DataTable table)  
  {  
     foreach (System.Data.DataRow row in table.Rows)  
     {  
        foreach (System.Data.DataColumn col in table.Columns)  
        {  
           Console.WriteLine("{0} = {1}", col.ColumnName, row[col]);  
        }  
     Console.WriteLine("============================");  
     }  
  }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="63fdb-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="63fdb-112">See also</span></span>

- [<span data-ttu-id="63fdb-113">Abrufen von Datenbankschemainformationen</span><span class="sxs-lookup"><span data-stu-id="63fdb-113">Retrieving Database Schema Information</span></span>](retrieving-database-schema-information.md)
- [<span data-ttu-id="63fdb-114">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="63fdb-114">ADO.NET Overview</span></span>](ado-net-overview.md)
