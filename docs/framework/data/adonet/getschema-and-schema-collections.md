---
title: "\"GetSchema\" und Schemaauflistungen"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab93b89-1221-427c-84ad-04803b3c64b4
ms.openlocfilehash: 11cfad81e40e76691db9f99efd1d60f5528600d2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61667046"
---
# <a name="getschema-and-schema-collections"></a><span data-ttu-id="23299-102">"GetSchema" und Schemaauflistungen</span><span class="sxs-lookup"><span data-stu-id="23299-102">GetSchema and Schema Collections</span></span>
<span data-ttu-id="23299-103">Die **Verbindung** -Klassen in jedem von der .NET Framework verwalteten Anbieter implementieren eine **GetSchema** Methode dient zum Abrufen von Schemainformationen zur Datenbank, die derzeit verbunden ist, und die Schemainformationen zurückgegeben, die von der **GetSchema** Methode kommt in Form von einem <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="23299-103">The **Connection** classes in each of the .NET Framework managed providers implement a **GetSchema** method which is used to retrieve schema information about the database that is currently connected, and the schema information returned from the **GetSchema** method comes in the form of a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="23299-104">Die **GetSchema** Methode ist eine überladene Methode, die optionale Parameter, die zum Angeben der zurückzugebenden schemaauflistung und zum Einschränken der zurückzugebenden Informationsmenge bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="23299-104">The **GetSchema** method is an overloaded method that provides optional parameters for specifying the schema collection to return, and restricting the amount of information returned.</span></span>  
  
## <a name="specifying-the-schema-collections"></a><span data-ttu-id="23299-105">Angeben der Schemaauflistungen</span><span class="sxs-lookup"><span data-stu-id="23299-105">Specifying the Schema Collections</span></span>  
 <span data-ttu-id="23299-106">Dem ersten optionalen Parameter, der die **GetSchema** Methode ist der Name der als Zeichenfolge angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="23299-106">The first optional parameter of the **GetSchema** method is the collection name which is specified as a string.</span></span> <span data-ttu-id="23299-107">Es gibt zwei Arten von Schemaauflistungen: allgemeine Schemaauflistungen, die von allen Anbietern verwendet werden, und besondere Schemaauflistungen, die für jeden Anbieter spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="23299-107">There are two types of schema collections: common schema collections that are common to all providers, and specific schema collections which are specific to each provider.</span></span>  
  
 <span data-ttu-id="23299-108">Sie können einen verwalteten .NET Framework-Datenanbieter, um die Liste der unterstützten schemaauflistungen zu ermitteln, durch Aufrufen von Abfragen die **GetSchema** -Methode ohne Argumente oder mit dem schemaauflistungsnamen "MetaDataCollections".</span><span class="sxs-lookup"><span data-stu-id="23299-108">You can query a .NET Framework managed provider to determine the list of supported schema collections by calling the **GetSchema** method with no arguments, or with the schema collection name "MetaDataCollections".</span></span> <span data-ttu-id="23299-109">Dadurch wird <xref:System.Data.DataTable> mit einer Liste der unterstützten Schemaauflistungen, der Anzahl der von diesen Schemaauflistungen unterstützten Einschränkungen und der Anzahl der von diesen Schemaauflistungen verwendeten Bezeichnerteilen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="23299-109">This will return a <xref:System.Data.DataTable> with a list of the supported schema collections, the number of restrictions that they each support, and the number of identifier parts that they use.</span></span>  
  
### <a name="retrieving-schema-collections-example"></a><span data-ttu-id="23299-110">Beispiel zum Abrufen von Schemaauflistungen</span><span class="sxs-lookup"><span data-stu-id="23299-110">Retrieving Schema Collections Example</span></span>  
 <span data-ttu-id="23299-111">Die folgenden Beispiele veranschaulichen, wie Sie mit der <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> Methode von der .NET Framework-Datenanbieter für SQL Server <xref:System.Data.SqlClient.SqlConnection> -Klasse zum Abrufen von Schemainformationen zu allen enthaltenen Tabellen die **AdventureWorks**-Beispieldatenbank:</span><span class="sxs-lookup"><span data-stu-id="23299-111">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="23299-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="23299-112">See also</span></span>

- [<span data-ttu-id="23299-113">Abrufen von Datenbankschemainformationen</span><span class="sxs-lookup"><span data-stu-id="23299-113">Retrieving Database Schema Information</span></span>](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)
- [<span data-ttu-id="23299-114">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="23299-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
