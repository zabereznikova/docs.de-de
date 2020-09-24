---
title: Schemaeinschränkungen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
ms.openlocfilehash: c0a3cafef45341cd95fa0a4f65c818129e120e44
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147823"
---
# <a name="schema-restrictions"></a><span data-ttu-id="794b3-102">Schemaeinschränkungen</span><span class="sxs-lookup"><span data-stu-id="794b3-102">Schema Restrictions</span></span>

<span data-ttu-id="794b3-103">Der zweite optionale Parameter der **GetSchema** -Methode sind die Einschränkungen, die verwendet werden, um die Menge der zurückgegebenen Schema Informationen einzuschränken, und Sie werden als Zeichen folgen Array an die **GetSchema** -Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="794b3-103">The second optional parameter of the **GetSchema** method is the restrictions that are used to limit the amount of schema information returned, and it is passed to the **GetSchema** method as an array of strings.</span></span> <span data-ttu-id="794b3-104">Die Position im Array bestimmt die Werte, die zurückgegeben werden können. Dies entspricht der Anzahl der Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="794b3-104">The position in the array determines the values that you can pass, and this is equivalent to the restriction number.</span></span>  
  
 <span data-ttu-id="794b3-105">In der folgenden Tabelle werden beispielsweise die Einschränkungen beschrieben, die von der Schemaauflistung "Tables" mithilfe des .NET Framework-Datenanbieters für SQL Server unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="794b3-105">For example, the following table describes the restrictions supported by the "Tables" schema collection using the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="794b3-106">Zusätzliche Einschränkungen für SQL Server-Schemaauflistungen werden am Ende dieses Themas aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="794b3-106">Additional restrictions for SQL Server schema collections are listed at the end of this topic.</span></span>  
  
|<span data-ttu-id="794b3-107">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="794b3-107">Restriction Name</span></span>|<span data-ttu-id="794b3-108">Parametername</span><span class="sxs-lookup"><span data-stu-id="794b3-108">Parameter Name</span></span>|<span data-ttu-id="794b3-109">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="794b3-109">Restriction Default</span></span>|<span data-ttu-id="794b3-110">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="794b3-110">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="794b3-111">Katalog</span><span class="sxs-lookup"><span data-stu-id="794b3-111">Catalog</span></span>|@Catalog|<span data-ttu-id="794b3-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="794b3-112">TABLE_CATALOG</span></span>|<span data-ttu-id="794b3-113">1</span><span class="sxs-lookup"><span data-stu-id="794b3-113">1</span></span>|  
|<span data-ttu-id="794b3-114">Besitzer</span><span class="sxs-lookup"><span data-stu-id="794b3-114">Owner</span></span>|@Owner|<span data-ttu-id="794b3-115">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="794b3-115">TABLE_SCHEMA</span></span>|<span data-ttu-id="794b3-116">2</span><span class="sxs-lookup"><span data-stu-id="794b3-116">2</span></span>|  
|<span data-ttu-id="794b3-117">Tabelle</span><span class="sxs-lookup"><span data-stu-id="794b3-117">Table</span></span>|@Name|<span data-ttu-id="794b3-118">table_name</span><span class="sxs-lookup"><span data-stu-id="794b3-118">TABLE_NAME</span></span>|<span data-ttu-id="794b3-119">3</span><span class="sxs-lookup"><span data-stu-id="794b3-119">3</span></span>|  
|<span data-ttu-id="794b3-120">TableType</span><span class="sxs-lookup"><span data-stu-id="794b3-120">TableType</span></span>|@TableType|<span data-ttu-id="794b3-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="794b3-121">TABLE_TYPE</span></span>|<span data-ttu-id="794b3-122">4</span><span class="sxs-lookup"><span data-stu-id="794b3-122">4</span></span>|  
  
## <a name="specifying-restriction-values"></a><span data-ttu-id="794b3-123">Angeben der Einschränkungswerte</span><span class="sxs-lookup"><span data-stu-id="794b3-123">Specifying Restriction Values</span></span>  

 <span data-ttu-id="794b3-124">Wenn Sie eine der Einschränkungen der Tables-Schemaauflistung verwenden möchten, erstellen Sie ein Zeichenfolgenarray mit vier Elementen und fügen einen Wert in das Element ein, das mit der Einschränkungsnummer übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="794b3-124">To use one of the restrictions of the "Tables" schema collection, simply create an array of strings with four elements, then place a value in the element that matches the restriction number.</span></span> <span data-ttu-id="794b3-125">Um beispielsweise die von der **GetSchema** -Methode zurückgegebenen Tabellen nur auf die Tabellen im "Sales"-Schema zu beschränken, legen Sie das zweite Element des Arrays auf "Sales" fest, bevor Sie es an die **GetSchema** -Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="794b3-125">For example, to restrict the tables returned by the **GetSchema** method to only those tables in the "Sales" schema, set the second element of the array to "Sales" before passing it to the **GetSchema** method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="794b3-126">Die Einschränkungsauflistungen für den `SqlClient` und den `OracleClient` verfügen über eine zusätzliche `ParameterName`-Spalte.</span><span class="sxs-lookup"><span data-stu-id="794b3-126">The restrictions collections for `SqlClient` and `OracleClient` have an additional `ParameterName` column.</span></span> <span data-ttu-id="794b3-127">Die Spalte für den Einschränkungsstandard ist zwar aus Gründen der Abwärtskompatibilität vorhanden, wird aber derzeit ignoriert.</span><span class="sxs-lookup"><span data-stu-id="794b3-127">The restriction default column is still there for backwards compatibility, but is currently ignored.</span></span> <span data-ttu-id="794b3-128">Verwenden Sie Abfragen mit Parametern statt Zeichenfolgenersetzungen, um das Risiko eines SQL-Injection-Angriffs beim Angeben der Einschränkungswerte zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="794b3-128">Parameterized queries rather than string replacement should be used to minimize the risk of an SQL injection attack when specifying restriction values.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="794b3-129">Die Anzahl der Elementen im Array muss kleiner oder gleich der Anzahl der Einschränkungen sein, die für die angegebene Schemaauflistung unterstützt werden, da sonst eine <xref:System.ArgumentException> ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="794b3-129">The number of elements in the array must be less than or equal to the number of restrictions supported for the specified schema collection else an <xref:System.ArgumentException> will be thrown.</span></span> <span data-ttu-id="794b3-130">Es können weniger Elemente als die maximale Anzahl der Einschränkungen vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="794b3-130">There can be fewer than the maximum number of restrictions.</span></span> <span data-ttu-id="794b3-131">Es wird davon ausgegangen, dass die fehlenden Einschränkungen NULL (uneingeschränkt) sind.</span><span class="sxs-lookup"><span data-stu-id="794b3-131">The missing restrictions are assumed to be null (unrestricted).</span></span>  
  
 <span data-ttu-id="794b3-132">Sie können einen .NET Framework verwalteten Anbieter Abfragen, um die Liste der unterstützten Einschränkungen zu ermitteln, indem Sie die **GetSchema** -Methode mit dem Namen der Einschränkungs Schema Auflistung aufrufen. Dies ist "Einschränkungen".</span><span class="sxs-lookup"><span data-stu-id="794b3-132">You can query a .NET Framework managed provider to determine the list of supported restrictions by calling the **GetSchema** method with the name of the restrictions schema collection, which is "Restrictions".</span></span> <span data-ttu-id="794b3-133">Dabei wird eine <xref:System.Data.DataTable> mit einer Liste der Auflistungsnamen, Einschränkungsnamen, Standardeinschränkungswerte und der Anzahl der Einschränkungen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="794b3-133">This will return a <xref:System.Data.DataTable> with a list of the collection names, the restriction names, the default restriction values, and the restriction numbers.</span></span>  
  
### <a name="example"></a><span data-ttu-id="794b3-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="794b3-134">Example</span></span>  

 <span data-ttu-id="794b3-135">In den folgenden Beispielen wird veranschaulicht, wie die <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> -Methode der .NET Framework Datenanbieter für die SQL Server- <xref:System.Data.SqlClient.SqlConnection> Klasse zum Abrufen von Schema Informationen zu allen in der **AdventureWorks** -Beispieldatenbank enthaltenen Tabellen und zum Einschränken der zurückgegebenen Informationen auf die Tabellen im "Sales"-Schema verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="794b3-135">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database, and to restrict the information returned to only those tables in the "Sales" schema:</span></span>  
  
```vb  
Imports System.Data.SqlClient  
  
Module Module1  
Sub Main()  
  Dim connectionString As String = _  
    "Data Source=(local);Database=AdventureWorks;" & _  
       "Integrated Security=true;";  
  
  Dim restrictions(3) As String  
  Using connection As New SqlConnection(connectionString)  
    connection.Open()  
  
    'Specify the restrictions.  
    restrictions(1) = "Sales"  
    Dim table As DataTable = connection.GetSchema("Tables", _  
       restrictions)  
  
    ' Display the contents of the table.  
      For Each row As DataRow In table.Rows  
         For Each col As DataColumn In table.Columns  
            Console.WriteLine("{0} = {1}", col.ColumnName, row(col))  
         Next  
         Console.WriteLine("============================")  
      Next  
    Console.WriteLine("Press any key to continue.")  
    Console.ReadKey()  
  End Using  
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
    string connectionString =
       "Data Source=(local);Database=AdventureWorks;" +  
       "Integrated Security=true;";  
    using (SqlConnection connection =  
       new SqlConnection(connectionString))  
    {  
        connection.Open();  
  
        // Specify the restrictions.  
        string[] restrictions = new string[4];  
        restrictions[1] = "Sales";  
        System.Data.DataTable table = connection.GetSchema(  
          "Tables", restrictions);  
  
        // Display the contents of the table.  
        foreach (System.Data.DataRow row in table.Rows)  
        {  
            foreach (System.Data.DataColumn col in table.Columns)  
            {  
                Console.WriteLine("{0} = {1}",
                  col.ColumnName, row[col]);  
            }  
            Console.WriteLine("============================");  
        }  
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
  
## <a name="sql-server-schema-restrictions"></a><span data-ttu-id="794b3-136">SQL Server-Schemabeschränkungen</span><span class="sxs-lookup"><span data-stu-id="794b3-136">SQL Server Schema Restrictions</span></span>  

 <span data-ttu-id="794b3-137">In den folgenden Tabellen sind die Beschränkungen für SQL Server-Schemaauflistungen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="794b3-137">The following tables list the restrictions for SQL Server schema collections.</span></span>  
  
### <a name="users"></a><span data-ttu-id="794b3-138">Benutzer</span><span class="sxs-lookup"><span data-stu-id="794b3-138">Users</span></span>  
  
|<span data-ttu-id="794b3-139">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="794b3-139">Restriction Name</span></span>|<span data-ttu-id="794b3-140">Parametername</span><span class="sxs-lookup"><span data-stu-id="794b3-140">Parameter Name</span></span>|<span data-ttu-id="794b3-141">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="794b3-141">Restriction Default</span></span>|<span data-ttu-id="794b3-142">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="794b3-142">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="794b3-143">User_Name</span><span class="sxs-lookup"><span data-stu-id="794b3-143">User_Name</span></span>|@Name|<span data-ttu-id="794b3-144">name</span><span class="sxs-lookup"><span data-stu-id="794b3-144">name</span></span>|<span data-ttu-id="794b3-145">1</span><span class="sxs-lookup"><span data-stu-id="794b3-145">1</span></span>|  
  
### <a name="databases"></a><span data-ttu-id="794b3-146">Datenbanken</span><span class="sxs-lookup"><span data-stu-id="794b3-146">Databases</span></span>  
  
|<span data-ttu-id="794b3-147">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="794b3-147">Restriction Name</span></span>|<span data-ttu-id="794b3-148">Parametername</span><span class="sxs-lookup"><span data-stu-id="794b3-148">Parameter Name</span></span>|<span data-ttu-id="794b3-149">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="794b3-149">Restriction Default</span></span>|<span data-ttu-id="794b3-150">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="794b3-150">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="794b3-151">Name</span><span class="sxs-lookup"><span data-stu-id="794b3-151">Name</span></span>|@Name|<span data-ttu-id="794b3-152">Name</span><span class="sxs-lookup"><span data-stu-id="794b3-152">Name</span></span>|<span data-ttu-id="794b3-153">1</span><span class="sxs-lookup"><span data-stu-id="794b3-153">1</span></span>|  
  
### <a name="tables"></a><span data-ttu-id="794b3-154">Tabellen</span><span class="sxs-lookup"><span data-stu-id="794b3-154">Tables</span></span>  
  
|<span data-ttu-id="794b3-155">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="794b3-155">Restriction Name</span></span>|<span data-ttu-id="794b3-156">Parametername</span><span class="sxs-lookup"><span data-stu-id="794b3-156">Parameter Name</span></span>|<span data-ttu-id="794b3-157">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="794b3-157">Restriction Default</span></span>|<span data-ttu-id="794b3-158">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="794b3-158">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="794b3-159">Katalog</span><span class="sxs-lookup"><span data-stu-id="794b3-159">Catalog</span></span>|@Catalog|<span data-ttu-id="794b3-160">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="794b3-160">TABLE_CATALOG</span></span>|<span data-ttu-id="794b3-161">1</span><span class="sxs-lookup"><span data-stu-id="794b3-161">1</span></span>|  
|<span data-ttu-id="794b3-162">Besitzer</span><span class="sxs-lookup"><span data-stu-id="794b3-162">Owner</span></span>|@Owner|<span data-ttu-id="794b3-163">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="794b3-163">TABLE_SCHEMA</span></span>|<span data-ttu-id="794b3-164">2</span><span class="sxs-lookup"><span data-stu-id="794b3-164">2</span></span>|  
|<span data-ttu-id="794b3-165">Tabelle</span><span class="sxs-lookup"><span data-stu-id="794b3-165">Table</span></span>|@Name|<span data-ttu-id="794b3-166">table_name</span><span class="sxs-lookup"><span data-stu-id="794b3-166">TABLE_NAME</span></span>|<span data-ttu-id="794b3-167">3</span><span class="sxs-lookup"><span data-stu-id="794b3-167">3</span></span>|  
|<span data-ttu-id="794b3-168">TableType</span><span class="sxs-lookup"><span data-stu-id="794b3-168">TableType</span></span>|@TableType|<span data-ttu-id="794b3-169">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="794b3-169">TABLE_TYPE</span></span>|<span data-ttu-id="794b3-170">4</span><span class="sxs-lookup"><span data-stu-id="794b3-170">4</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="794b3-171">Spalten</span><span class="sxs-lookup"><span data-stu-id="794b3-171">Columns</span></span>  
  
|<span data-ttu-id="794b3-172">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="794b3-172">Restriction Name</span></span>|<span data-ttu-id="794b3-173">Parametername</span><span class="sxs-lookup"><span data-stu-id="794b3-173">Parameter Name</span></span>|<span data-ttu-id="794b3-174">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="794b3-174">Restriction Default</span></span>|<span data-ttu-id="794b3-175">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="794b3-175">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="794b3-176">Katalog</span><span class="sxs-lookup"><span data-stu-id="794b3-176">Catalog</span></span>|@Catalog|<span data-ttu-id="794b3-177">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="794b3-177">TABLE_CATALOG</span></span>|<span data-ttu-id="794b3-178">1</span><span class="sxs-lookup"><span data-stu-id="794b3-178">1</span></span>|  
|<span data-ttu-id="794b3-179">Besitzer</span><span class="sxs-lookup"><span data-stu-id="794b3-179">Owner</span></span>|@Owner|<span data-ttu-id="794b3-180">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="794b3-180">TABLE_SCHEMA</span></span>|<span data-ttu-id="794b3-181">2</span><span class="sxs-lookup"><span data-stu-id="794b3-181">2</span></span>|  
|<span data-ttu-id="794b3-182">Tabelle</span><span class="sxs-lookup"><span data-stu-id="794b3-182">Table</span></span>|@Table|<span data-ttu-id="794b3-183">table_name</span><span class="sxs-lookup"><span data-stu-id="794b3-183">TABLE_NAME</span></span>|<span data-ttu-id="794b3-184">3</span><span class="sxs-lookup"><span data-stu-id="794b3-184">3</span></span>|  
|<span data-ttu-id="794b3-185">Column</span><span class="sxs-lookup"><span data-stu-id="794b3-185">Column</span></span>|@Column|<span data-ttu-id="794b3-186">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="794b3-186">COLUMN_NAME</span></span>|<span data-ttu-id="794b3-187">4</span><span class="sxs-lookup"><span data-stu-id="794b3-187">4</span></span>|  
  
### <a name="structuredtypemembers"></a><span data-ttu-id="794b3-188">StructuredTypeMembers</span><span class="sxs-lookup"><span data-stu-id="794b3-188">StructuredTypeMembers</span></span>  
  
|<span data-ttu-id="794b3-189">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="794b3-189">Restriction Name</span></span>|<span data-ttu-id="794b3-190">Parametername</span><span class="sxs-lookup"><span data-stu-id="794b3-190">Parameter Name</span></span>|<span data-ttu-id="794b3-191">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="794b3-191">Restriction Default</span></span>|<span data-ttu-id="794b3-192">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="794b3-192">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="794b3-193">Katalog</span><span class="sxs-lookup"><span data-stu-id="794b3-193">Catalog</span></span>|@Catalog|<span data-ttu-id="794b3-194">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="794b3-194">TABLE_CATALOG</span></span>|<span data-ttu-id="794b3-195">1</span><span class="sxs-lookup"><span data-stu-id="794b3-195">1</span></span>|  
|<span data-ttu-id="794b3-196">Besitzer</span><span class="sxs-lookup"><span data-stu-id="794b3-196">Owner</span></span>|@Owner|<span data-ttu-id="794b3-197">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="794b3-197">TABLE_SCHEMA</span></span>|<span data-ttu-id="794b3-198">2</span><span class="sxs-lookup"><span data-stu-id="794b3-198">2</span></span>|  
|<span data-ttu-id="794b3-199">Tabelle</span><span class="sxs-lookup"><span data-stu-id="794b3-199">Table</span></span>|@Table|<span data-ttu-id="794b3-200">table_name</span><span class="sxs-lookup"><span data-stu-id="794b3-200">TABLE_NAME</span></span>|<span data-ttu-id="794b3-201">3</span><span class="sxs-lookup"><span data-stu-id="794b3-201">3</span></span>|  
|<span data-ttu-id="794b3-202">Column</span><span class="sxs-lookup"><span data-stu-id="794b3-202">Column</span></span>|@Column|<span data-ttu-id="794b3-203">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="794b3-203">COLUMN_NAME</span></span>|<span data-ttu-id="794b3-204">4</span><span class="sxs-lookup"><span data-stu-id="794b3-204">4</span></span>|  
  
### <a name="views"></a><span data-ttu-id="794b3-205">Sichten</span><span class="sxs-lookup"><span data-stu-id="794b3-205">Views</span></span>  
  
|<span data-ttu-id="794b3-206">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="794b3-206">Restriction Name</span></span>|<span data-ttu-id="794b3-207">Parametername</span><span class="sxs-lookup"><span data-stu-id="794b3-207">Parameter Name</span></span>|<span data-ttu-id="794b3-208">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="794b3-208">Restriction Default</span></span>|<span data-ttu-id="794b3-209">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="794b3-209">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="794b3-210">Katalog</span><span class="sxs-lookup"><span data-stu-id="794b3-210">Catalog</span></span>|@Catalog|<span data-ttu-id="794b3-211">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="794b3-211">TABLE_CATALOG</span></span>|<span data-ttu-id="794b3-212">1</span><span class="sxs-lookup"><span data-stu-id="794b3-212">1</span></span>|  
|<span data-ttu-id="794b3-213">Besitzer</span><span class="sxs-lookup"><span data-stu-id="794b3-213">Owner</span></span>|@Owner|<span data-ttu-id="794b3-214">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="794b3-214">TABLE_SCHEMA</span></span>|<span data-ttu-id="794b3-215">2</span><span class="sxs-lookup"><span data-stu-id="794b3-215">2</span></span>|  
|<span data-ttu-id="794b3-216">Tabelle</span><span class="sxs-lookup"><span data-stu-id="794b3-216">Table</span></span>|@Table|<span data-ttu-id="794b3-217">table_name</span><span class="sxs-lookup"><span data-stu-id="794b3-217">TABLE_NAME</span></span>|<span data-ttu-id="794b3-218">3</span><span class="sxs-lookup"><span data-stu-id="794b3-218">3</span></span>|  
  
### <a name="viewcolumns"></a><span data-ttu-id="794b3-219">ViewColumns</span><span class="sxs-lookup"><span data-stu-id="794b3-219">ViewColumns</span></span>  
  
|<span data-ttu-id="794b3-220">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="794b3-220">Restriction Name</span></span>|<span data-ttu-id="794b3-221">Parametername</span><span class="sxs-lookup"><span data-stu-id="794b3-221">Parameter Name</span></span>|<span data-ttu-id="794b3-222">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="794b3-222">Restriction Default</span></span>|<span data-ttu-id="794b3-223">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="794b3-223">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="794b3-224">Katalog</span><span class="sxs-lookup"><span data-stu-id="794b3-224">Catalog</span></span>|@Catalog|<span data-ttu-id="794b3-225">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="794b3-225">VIEW_CATALOG</span></span>|<span data-ttu-id="794b3-226">1</span><span class="sxs-lookup"><span data-stu-id="794b3-226">1</span></span>|  
|<span data-ttu-id="794b3-227">Besitzer</span><span class="sxs-lookup"><span data-stu-id="794b3-227">Owner</span></span>|@Owner|<span data-ttu-id="794b3-228">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="794b3-228">VIEW_SCHEMA</span></span>|<span data-ttu-id="794b3-229">2</span><span class="sxs-lookup"><span data-stu-id="794b3-229">2</span></span>|  
|<span data-ttu-id="794b3-230">Tabelle</span><span class="sxs-lookup"><span data-stu-id="794b3-230">Table</span></span>|@Table|<span data-ttu-id="794b3-231">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="794b3-231">VIEW_NAME</span></span>|<span data-ttu-id="794b3-232">3</span><span class="sxs-lookup"><span data-stu-id="794b3-232">3</span></span>|  
|<span data-ttu-id="794b3-233">Column</span><span class="sxs-lookup"><span data-stu-id="794b3-233">Column</span></span>|@Column|<span data-ttu-id="794b3-234">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="794b3-234">COLUMN_NAME</span></span>|<span data-ttu-id="794b3-235">4</span><span class="sxs-lookup"><span data-stu-id="794b3-235">4</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="794b3-236">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="794b3-236">ProcedureParameters</span></span>  
  
|<span data-ttu-id="794b3-237">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="794b3-237">Restriction Name</span></span>|<span data-ttu-id="794b3-238">Parametername</span><span class="sxs-lookup"><span data-stu-id="794b3-238">Parameter Name</span></span>|<span data-ttu-id="794b3-239">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="794b3-239">Restriction Default</span></span>|<span data-ttu-id="794b3-240">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="794b3-240">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="794b3-241">Katalog</span><span class="sxs-lookup"><span data-stu-id="794b3-241">Catalog</span></span>|@Catalog|<span data-ttu-id="794b3-242">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="794b3-242">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="794b3-243">1</span><span class="sxs-lookup"><span data-stu-id="794b3-243">1</span></span>|  
|<span data-ttu-id="794b3-244">Besitzer</span><span class="sxs-lookup"><span data-stu-id="794b3-244">Owner</span></span>|@Owner|<span data-ttu-id="794b3-245">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="794b3-245">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="794b3-246">2</span><span class="sxs-lookup"><span data-stu-id="794b3-246">2</span></span>|  
|<span data-ttu-id="794b3-247">Name</span><span class="sxs-lookup"><span data-stu-id="794b3-247">Name</span></span>|@Name|<span data-ttu-id="794b3-248">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="794b3-248">SPECIFIC_NAME</span></span>|<span data-ttu-id="794b3-249">3</span><span class="sxs-lookup"><span data-stu-id="794b3-249">3</span></span>|  
|<span data-ttu-id="794b3-250">Parameter</span><span class="sxs-lookup"><span data-stu-id="794b3-250">Parameter</span></span>|@Parameter|<span data-ttu-id="794b3-251">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="794b3-251">PARAMETER_NAME</span></span>|<span data-ttu-id="794b3-252">4</span><span class="sxs-lookup"><span data-stu-id="794b3-252">4</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="794b3-253">Prozeduren</span><span class="sxs-lookup"><span data-stu-id="794b3-253">Procedures</span></span>  
  
|<span data-ttu-id="794b3-254">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="794b3-254">Restriction Name</span></span>|<span data-ttu-id="794b3-255">Parametername</span><span class="sxs-lookup"><span data-stu-id="794b3-255">Parameter Name</span></span>|<span data-ttu-id="794b3-256">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="794b3-256">Restriction Default</span></span>|<span data-ttu-id="794b3-257">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="794b3-257">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="794b3-258">Katalog</span><span class="sxs-lookup"><span data-stu-id="794b3-258">Catalog</span></span>|@Catalog|<span data-ttu-id="794b3-259">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="794b3-259">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="794b3-260">1</span><span class="sxs-lookup"><span data-stu-id="794b3-260">1</span></span>|  
|<span data-ttu-id="794b3-261">Besitzer</span><span class="sxs-lookup"><span data-stu-id="794b3-261">Owner</span></span>|@Owner|<span data-ttu-id="794b3-262">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="794b3-262">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="794b3-263">2</span><span class="sxs-lookup"><span data-stu-id="794b3-263">2</span></span>|  
|<span data-ttu-id="794b3-264">Name</span><span class="sxs-lookup"><span data-stu-id="794b3-264">Name</span></span>|@Name|<span data-ttu-id="794b3-265">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="794b3-265">SPECIFIC_NAME</span></span>|<span data-ttu-id="794b3-266">3</span><span class="sxs-lookup"><span data-stu-id="794b3-266">3</span></span>|  
|<span data-ttu-id="794b3-267">Typ</span><span class="sxs-lookup"><span data-stu-id="794b3-267">Type</span></span>|@Type|<span data-ttu-id="794b3-268">ROUTINE_TYPE</span><span class="sxs-lookup"><span data-stu-id="794b3-268">ROUTINE_TYPE</span></span>|<span data-ttu-id="794b3-269">4</span><span class="sxs-lookup"><span data-stu-id="794b3-269">4</span></span>|  
  
### <a name="indexcolumns"></a><span data-ttu-id="794b3-270">IndexColumns</span><span class="sxs-lookup"><span data-stu-id="794b3-270">IndexColumns</span></span>  
  
|<span data-ttu-id="794b3-271">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="794b3-271">Restriction Name</span></span>|<span data-ttu-id="794b3-272">Parametername</span><span class="sxs-lookup"><span data-stu-id="794b3-272">Parameter Name</span></span>|<span data-ttu-id="794b3-273">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="794b3-273">Restriction Default</span></span>|<span data-ttu-id="794b3-274">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="794b3-274">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="794b3-275">Katalog</span><span class="sxs-lookup"><span data-stu-id="794b3-275">Catalog</span></span>|@Catalog|<span data-ttu-id="794b3-276">db_name()</span><span class="sxs-lookup"><span data-stu-id="794b3-276">db_name()</span></span>|<span data-ttu-id="794b3-277">1</span><span class="sxs-lookup"><span data-stu-id="794b3-277">1</span></span>|  
|<span data-ttu-id="794b3-278">Besitzer</span><span class="sxs-lookup"><span data-stu-id="794b3-278">Owner</span></span>|@Owner|<span data-ttu-id="794b3-279">user_name()</span><span class="sxs-lookup"><span data-stu-id="794b3-279">user_name()</span></span>|<span data-ttu-id="794b3-280">2</span><span class="sxs-lookup"><span data-stu-id="794b3-280">2</span></span>|  
|<span data-ttu-id="794b3-281">Tabelle</span><span class="sxs-lookup"><span data-stu-id="794b3-281">Table</span></span>|@Table|<span data-ttu-id="794b3-282">o.name</span><span class="sxs-lookup"><span data-stu-id="794b3-282">o.name</span></span>|<span data-ttu-id="794b3-283">3</span><span class="sxs-lookup"><span data-stu-id="794b3-283">3</span></span>|  
|<span data-ttu-id="794b3-284">ConstraintName</span><span class="sxs-lookup"><span data-stu-id="794b3-284">ConstraintName</span></span>|@ConstraintName|<span data-ttu-id="794b3-285">x.name</span><span class="sxs-lookup"><span data-stu-id="794b3-285">x.name</span></span>|<span data-ttu-id="794b3-286">4</span><span class="sxs-lookup"><span data-stu-id="794b3-286">4</span></span>|  
|<span data-ttu-id="794b3-287">Column</span><span class="sxs-lookup"><span data-stu-id="794b3-287">Column</span></span>|@Column|<span data-ttu-id="794b3-288">c.name</span><span class="sxs-lookup"><span data-stu-id="794b3-288">c.name</span></span>|<span data-ttu-id="794b3-289">5</span><span class="sxs-lookup"><span data-stu-id="794b3-289">5</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="794b3-290">Indizes</span><span class="sxs-lookup"><span data-stu-id="794b3-290">Indexes</span></span>  
  
|<span data-ttu-id="794b3-291">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="794b3-291">Restriction Name</span></span>|<span data-ttu-id="794b3-292">Parametername</span><span class="sxs-lookup"><span data-stu-id="794b3-292">Parameter Name</span></span>|<span data-ttu-id="794b3-293">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="794b3-293">Restriction Default</span></span>|<span data-ttu-id="794b3-294">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="794b3-294">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="794b3-295">Katalog</span><span class="sxs-lookup"><span data-stu-id="794b3-295">Catalog</span></span>|@Catalog|<span data-ttu-id="794b3-296">db_name()</span><span class="sxs-lookup"><span data-stu-id="794b3-296">db_name()</span></span>|<span data-ttu-id="794b3-297">1</span><span class="sxs-lookup"><span data-stu-id="794b3-297">1</span></span>|  
|<span data-ttu-id="794b3-298">Besitzer</span><span class="sxs-lookup"><span data-stu-id="794b3-298">Owner</span></span>|@Owner|<span data-ttu-id="794b3-299">user_name()</span><span class="sxs-lookup"><span data-stu-id="794b3-299">user_name()</span></span>|<span data-ttu-id="794b3-300">2</span><span class="sxs-lookup"><span data-stu-id="794b3-300">2</span></span>|  
|<span data-ttu-id="794b3-301">Tabelle</span><span class="sxs-lookup"><span data-stu-id="794b3-301">Table</span></span>|@Table|<span data-ttu-id="794b3-302">o.name</span><span class="sxs-lookup"><span data-stu-id="794b3-302">o.name</span></span>|<span data-ttu-id="794b3-303">3</span><span class="sxs-lookup"><span data-stu-id="794b3-303">3</span></span>|  
  
### <a name="userdefinedtypes"></a><span data-ttu-id="794b3-304">UserDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="794b3-304">UserDefinedTypes</span></span>  
  
|<span data-ttu-id="794b3-305">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="794b3-305">Restriction Name</span></span>|<span data-ttu-id="794b3-306">Parametername</span><span class="sxs-lookup"><span data-stu-id="794b3-306">Parameter Name</span></span>|<span data-ttu-id="794b3-307">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="794b3-307">Restriction Default</span></span>|<span data-ttu-id="794b3-308">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="794b3-308">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="794b3-309">assembly_name</span><span class="sxs-lookup"><span data-stu-id="794b3-309">assembly_name</span></span>|@AssemblyName|<span data-ttu-id="794b3-310">assemblies.name</span><span class="sxs-lookup"><span data-stu-id="794b3-310">assemblies.name</span></span>|<span data-ttu-id="794b3-311">1</span><span class="sxs-lookup"><span data-stu-id="794b3-311">1</span></span>|  
|<span data-ttu-id="794b3-312">udt_name</span><span class="sxs-lookup"><span data-stu-id="794b3-312">udt_name</span></span>|@UDTName|<span data-ttu-id="794b3-313">types.assembly_class</span><span class="sxs-lookup"><span data-stu-id="794b3-313">types.assembly_class</span></span>|<span data-ttu-id="794b3-314">2</span><span class="sxs-lookup"><span data-stu-id="794b3-314">2</span></span>|  
  
### <a name="foreignkeys"></a><span data-ttu-id="794b3-315">ForeignKeys</span><span class="sxs-lookup"><span data-stu-id="794b3-315">ForeignKeys</span></span>  
  
|<span data-ttu-id="794b3-316">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="794b3-316">Restriction Name</span></span>|<span data-ttu-id="794b3-317">Parametername</span><span class="sxs-lookup"><span data-stu-id="794b3-317">Parameter Name</span></span>|<span data-ttu-id="794b3-318">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="794b3-318">Restriction Default</span></span>|<span data-ttu-id="794b3-319">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="794b3-319">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="794b3-320">Katalog</span><span class="sxs-lookup"><span data-stu-id="794b3-320">Catalog</span></span>|@Catalog|<span data-ttu-id="794b3-321">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="794b3-321">CONSTRAINT_CATALOG</span></span>|<span data-ttu-id="794b3-322">1</span><span class="sxs-lookup"><span data-stu-id="794b3-322">1</span></span>|  
|<span data-ttu-id="794b3-323">Besitzer</span><span class="sxs-lookup"><span data-stu-id="794b3-323">Owner</span></span>|@Owner|<span data-ttu-id="794b3-324">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="794b3-324">CONSTRAINT_SCHEMA</span></span>|<span data-ttu-id="794b3-325">2</span><span class="sxs-lookup"><span data-stu-id="794b3-325">2</span></span>|  
|<span data-ttu-id="794b3-326">Tabelle</span><span class="sxs-lookup"><span data-stu-id="794b3-326">Table</span></span>|@Table|<span data-ttu-id="794b3-327">table_name</span><span class="sxs-lookup"><span data-stu-id="794b3-327">TABLE_NAME</span></span>|<span data-ttu-id="794b3-328">3</span><span class="sxs-lookup"><span data-stu-id="794b3-328">3</span></span>|  
|<span data-ttu-id="794b3-329">Name</span><span class="sxs-lookup"><span data-stu-id="794b3-329">Name</span></span>|@Name|<span data-ttu-id="794b3-330">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="794b3-330">CONSTRAINT_NAME</span></span>|<span data-ttu-id="794b3-331">4</span><span class="sxs-lookup"><span data-stu-id="794b3-331">4</span></span>|  
  
## <a name="sql-server-2008-schema-restrictions"></a><span data-ttu-id="794b3-332">SQL Server 2008-Schemabeschränkungen</span><span class="sxs-lookup"><span data-stu-id="794b3-332">SQL Server 2008 Schema Restrictions</span></span>  

 <span data-ttu-id="794b3-333">In den folgenden Tabellen sind die Beschränkungen für SQL Server 2008-Schemaauflistungen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="794b3-333">The following tables list the restrictions for SQL Server 2008 schema collections.</span></span> <span data-ttu-id="794b3-334">Diese Beschränkungen gelten ab Version 3.5 SP1 von .NET Framework und SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="794b3-334">These restrictions are valid beginning with version 3.5 SP1 of the .NET Framework and SQL Server 2008.</span></span> <span data-ttu-id="794b3-335">Sie werden in früheren Versionen von .NET Framework und SQL Server nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="794b3-335">They are not supported in earlier versions of the .NET Framework and SQL Server.</span></span>  
  
### <a name="columnsetcolumns"></a><span data-ttu-id="794b3-336">ColumnSetColumns</span><span class="sxs-lookup"><span data-stu-id="794b3-336">ColumnSetColumns</span></span>  
  
|<span data-ttu-id="794b3-337">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="794b3-337">Restriction Name</span></span>|<span data-ttu-id="794b3-338">Parametername</span><span class="sxs-lookup"><span data-stu-id="794b3-338">Parameter Name</span></span>|<span data-ttu-id="794b3-339">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="794b3-339">Restriction Default</span></span>|<span data-ttu-id="794b3-340">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="794b3-340">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="794b3-341">Katalog</span><span class="sxs-lookup"><span data-stu-id="794b3-341">Catalog</span></span>|@Catalog|<span data-ttu-id="794b3-342">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="794b3-342">TABLE_CATALOG</span></span>|<span data-ttu-id="794b3-343">1</span><span class="sxs-lookup"><span data-stu-id="794b3-343">1</span></span>|  
|<span data-ttu-id="794b3-344">Besitzer</span><span class="sxs-lookup"><span data-stu-id="794b3-344">Owner</span></span>|@Owner|<span data-ttu-id="794b3-345">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="794b3-345">TABLE_SCHEMA</span></span>|<span data-ttu-id="794b3-346">2</span><span class="sxs-lookup"><span data-stu-id="794b3-346">2</span></span>|  
|<span data-ttu-id="794b3-347">Tabelle</span><span class="sxs-lookup"><span data-stu-id="794b3-347">Table</span></span>|@Table|<span data-ttu-id="794b3-348">table_name</span><span class="sxs-lookup"><span data-stu-id="794b3-348">TABLE_NAME</span></span>|<span data-ttu-id="794b3-349">3</span><span class="sxs-lookup"><span data-stu-id="794b3-349">3</span></span>|  
  
### <a name="allcolumns"></a><span data-ttu-id="794b3-350">AllColumns</span><span class="sxs-lookup"><span data-stu-id="794b3-350">AllColumns</span></span>  
  
|<span data-ttu-id="794b3-351">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="794b3-351">Restriction Name</span></span>|<span data-ttu-id="794b3-352">Parametername</span><span class="sxs-lookup"><span data-stu-id="794b3-352">Parameter Name</span></span>|<span data-ttu-id="794b3-353">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="794b3-353">Restriction Default</span></span>|<span data-ttu-id="794b3-354">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="794b3-354">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="794b3-355">Katalog</span><span class="sxs-lookup"><span data-stu-id="794b3-355">Catalog</span></span>|@Catalog|<span data-ttu-id="794b3-356">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="794b3-356">TABLE_CATALOG</span></span>|<span data-ttu-id="794b3-357">1</span><span class="sxs-lookup"><span data-stu-id="794b3-357">1</span></span>|  
|<span data-ttu-id="794b3-358">Besitzer</span><span class="sxs-lookup"><span data-stu-id="794b3-358">Owner</span></span>|@Owner|<span data-ttu-id="794b3-359">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="794b3-359">TABLE_SCHEMA</span></span>|<span data-ttu-id="794b3-360">2</span><span class="sxs-lookup"><span data-stu-id="794b3-360">2</span></span>|  
|<span data-ttu-id="794b3-361">Tabelle</span><span class="sxs-lookup"><span data-stu-id="794b3-361">Table</span></span>|@Table|<span data-ttu-id="794b3-362">table_name</span><span class="sxs-lookup"><span data-stu-id="794b3-362">TABLE_NAME</span></span>|<span data-ttu-id="794b3-363">3</span><span class="sxs-lookup"><span data-stu-id="794b3-363">3</span></span>|  
|<span data-ttu-id="794b3-364">Column</span><span class="sxs-lookup"><span data-stu-id="794b3-364">Column</span></span>|@Column|<span data-ttu-id="794b3-365">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="794b3-365">COLUMN_NAME</span></span>|<span data-ttu-id="794b3-366">4</span><span class="sxs-lookup"><span data-stu-id="794b3-366">4</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="794b3-367">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="794b3-367">See also</span></span>

- [<span data-ttu-id="794b3-368">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="794b3-368">ADO.NET Overview</span></span>](ado-net-overview.md)
