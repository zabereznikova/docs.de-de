---
title: Schemaeinschränkungen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
ms.openlocfilehash: d0250e573dc24bfcad97a2f2606cb2e6c8e520da
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782755"
---
# <a name="schema-restrictions"></a><span data-ttu-id="ba29a-102">Schemaeinschränkungen</span><span class="sxs-lookup"><span data-stu-id="ba29a-102">Schema Restrictions</span></span>
<span data-ttu-id="ba29a-103">Der zweite optionale Parameter der **GetSchema** -Methode sind die Einschränkungen, die verwendet werden, um die Menge der zurückgegebenen Schema Informationen einzuschränken, und Sie werden als Zeichen folgen Array an die **GetSchema** -Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="ba29a-103">The second optional parameter of the **GetSchema** method is the restrictions that are used to limit the amount of schema information returned, and it is passed to the **GetSchema** method as an array of strings.</span></span> <span data-ttu-id="ba29a-104">Die Position im Array bestimmt die Werte, die zurückgegeben werden können. Dies entspricht der Anzahl der Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="ba29a-104">The position in the array determines the values that you can pass, and this is equivalent to the restriction number.</span></span>  
  
 <span data-ttu-id="ba29a-105">In der folgenden Tabelle werden beispielsweise die Einschränkungen beschrieben, die von der Schemaauflistung "Tables" mithilfe des .NET Framework-Datenanbieters für SQL Server unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="ba29a-105">For example, the following table describes the restrictions supported by the "Tables" schema collection using the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="ba29a-106">Zusätzliche Einschränkungen für SQL Server-Schemaauflistungen werden am Ende dieses Themas aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="ba29a-106">Additional restrictions for SQL Server schema collections are listed at the end of this topic.</span></span>  
  
|<span data-ttu-id="ba29a-107">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="ba29a-107">Restriction Name</span></span>|<span data-ttu-id="ba29a-108">Parametername</span><span class="sxs-lookup"><span data-stu-id="ba29a-108">Parameter Name</span></span>|<span data-ttu-id="ba29a-109">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="ba29a-109">Restriction Default</span></span>|<span data-ttu-id="ba29a-110">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="ba29a-110">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="ba29a-111">Katalog</span><span class="sxs-lookup"><span data-stu-id="ba29a-111">Catalog</span></span>|@Catalog|<span data-ttu-id="ba29a-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="ba29a-112">TABLE_CATALOG</span></span>|<span data-ttu-id="ba29a-113">1</span><span class="sxs-lookup"><span data-stu-id="ba29a-113">1</span></span>|  
|<span data-ttu-id="ba29a-114">Besitzer</span><span class="sxs-lookup"><span data-stu-id="ba29a-114">Owner</span></span>|@Owner|<span data-ttu-id="ba29a-115">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="ba29a-115">TABLE_SCHEMA</span></span>|<span data-ttu-id="ba29a-116">2</span><span class="sxs-lookup"><span data-stu-id="ba29a-116">2</span></span>|  
|<span data-ttu-id="ba29a-117">Tabelle</span><span class="sxs-lookup"><span data-stu-id="ba29a-117">Table</span></span>|@Name|<span data-ttu-id="ba29a-118">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="ba29a-118">TABLE_NAME</span></span>|<span data-ttu-id="ba29a-119">3</span><span class="sxs-lookup"><span data-stu-id="ba29a-119">3</span></span>|  
|<span data-ttu-id="ba29a-120">TableType</span><span class="sxs-lookup"><span data-stu-id="ba29a-120">TableType</span></span>|@TableType|<span data-ttu-id="ba29a-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="ba29a-121">TABLE_TYPE</span></span>|<span data-ttu-id="ba29a-122">4</span><span class="sxs-lookup"><span data-stu-id="ba29a-122">4</span></span>|  
  
## <a name="specifying-restriction-values"></a><span data-ttu-id="ba29a-123">Angeben der Einschränkungswerte</span><span class="sxs-lookup"><span data-stu-id="ba29a-123">Specifying Restriction Values</span></span>  
 <span data-ttu-id="ba29a-124">Wenn Sie eine der Einschränkungen der Tables-Schemaauflistung verwenden möchten, erstellen Sie ein Zeichenfolgenarray mit vier Elementen und fügen einen Wert in das Element ein, das mit der Einschränkungsnummer übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="ba29a-124">To use one of the restrictions of the "Tables" schema collection, simply create an array of strings with four elements, then place a value in the element that matches the restriction number.</span></span> <span data-ttu-id="ba29a-125">Um beispielsweise die von der **GetSchema** -Methode zurückgegebenen Tabellen nur auf die Tabellen im "Sales"-Schema zu beschränken, legen Sie das zweite Element des Arrays auf "Sales" fest, bevor Sie es an die **GetSchema** -Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="ba29a-125">For example, to restrict the tables returned by the **GetSchema** method to only those tables in the "Sales" schema, set the second element of the array to "Sales" before passing it to the **GetSchema** method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ba29a-126">Die Einschränkungsauflistungen für den `SqlClient` und den `OracleClient` verfügen über eine zusätzliche `ParameterName`-Spalte.</span><span class="sxs-lookup"><span data-stu-id="ba29a-126">The restrictions collections for `SqlClient` and `OracleClient` have an additional `ParameterName` column.</span></span> <span data-ttu-id="ba29a-127">Die Spalte für den Einschränkungsstandard ist zwar aus Gründen der Abwärtskompatibilität vorhanden, wird aber derzeit ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ba29a-127">The restriction default column is still there for backwards compatibility, but is currently ignored.</span></span> <span data-ttu-id="ba29a-128">Verwenden Sie Abfragen mit Parametern statt Zeichenfolgenersetzungen, um das Risiko eines SQL-Injection-Angriffs beim Angeben der Einschränkungswerte zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="ba29a-128">Parameterized queries rather than string replacement should be used to minimize the risk of an SQL injection attack when specifying restriction values.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ba29a-129">Die Anzahl der Elementen im Array muss kleiner oder gleich der Anzahl der Einschränkungen sein, die für die angegebene Schemaauflistung unterstützt werden, da sonst eine <xref:System.ArgumentException> ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="ba29a-129">The number of elements in the array must be less than or equal to the number of restrictions supported for the specified schema collection else an <xref:System.ArgumentException> will be thrown.</span></span> <span data-ttu-id="ba29a-130">Es können weniger Elemente als die maximale Anzahl der Einschränkungen vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="ba29a-130">There can be fewer than the maximum number of restrictions.</span></span> <span data-ttu-id="ba29a-131">Es wird davon ausgegangen, dass die fehlenden Einschränkungen NULL (uneingeschränkt) sind.</span><span class="sxs-lookup"><span data-stu-id="ba29a-131">The missing restrictions are assumed to be null (unrestricted).</span></span>  
  
 <span data-ttu-id="ba29a-132">Sie können einen .NET Framework verwalteten Anbieter Abfragen, um die Liste der unterstützten Einschränkungen zu ermitteln, indem Sie die **GetSchema** -Methode mit dem Namen der Einschränkungs Schema Auflistung aufrufen. Dies ist "Einschränkungen".</span><span class="sxs-lookup"><span data-stu-id="ba29a-132">You can query a .NET Framework managed provider to determine the list of supported restrictions by calling the **GetSchema** method with the name of the restrictions schema collection, which is "Restrictions".</span></span> <span data-ttu-id="ba29a-133">Dabei wird eine <xref:System.Data.DataTable> mit einer Liste der Auflistungsnamen, Einschränkungsnamen, Standardeinschränkungswerte und der Anzahl der Einschränkungen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ba29a-133">This will return a <xref:System.Data.DataTable> with a list of the collection names, the restriction names, the default restriction values, and the restriction numbers.</span></span>  
  
### <a name="example"></a><span data-ttu-id="ba29a-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ba29a-134">Example</span></span>  
 <span data-ttu-id="ba29a-135">In den folgenden Beispielen wird veranschaulicht, wie <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> die-Methode der .NET Framework Datenanbieter für die <xref:System.Data.SqlClient.SqlConnection> SQL Server-Klasse verwendet wird, um Schema Informationen zu allen Tabellen abzurufen, die in der **AdventureWorks** -Beispieldatenbank enthalten sind. und um die Informationen einzuschränken, die nur auf die Tabellen im "Sales"-Schema zurückgegeben werden:</span><span class="sxs-lookup"><span data-stu-id="ba29a-135">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database, and to restrict the information returned to only those tables in the "Sales" schema:</span></span>  
  
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
  
## <a name="sql-server-schema-restrictions"></a><span data-ttu-id="ba29a-136">SQL Server-Schemabeschränkungen</span><span class="sxs-lookup"><span data-stu-id="ba29a-136">SQL Server Schema Restrictions</span></span>  
 <span data-ttu-id="ba29a-137">In den folgenden Tabellen sind die Beschränkungen für SQL Server-Schemaauflistungen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="ba29a-137">The following tables list the restrictions for SQL Server schema collections.</span></span>  
  
### <a name="users"></a><span data-ttu-id="ba29a-138">Benutzer</span><span class="sxs-lookup"><span data-stu-id="ba29a-138">Users</span></span>  
  
|<span data-ttu-id="ba29a-139">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="ba29a-139">Restriction Name</span></span>|<span data-ttu-id="ba29a-140">Parametername</span><span class="sxs-lookup"><span data-stu-id="ba29a-140">Parameter Name</span></span>|<span data-ttu-id="ba29a-141">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="ba29a-141">Restriction Default</span></span>|<span data-ttu-id="ba29a-142">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="ba29a-142">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="ba29a-143">User_Name</span><span class="sxs-lookup"><span data-stu-id="ba29a-143">User_Name</span></span>|@Name|<span data-ttu-id="ba29a-144">Name</span><span class="sxs-lookup"><span data-stu-id="ba29a-144">name</span></span>|<span data-ttu-id="ba29a-145">1</span><span class="sxs-lookup"><span data-stu-id="ba29a-145">1</span></span>|  
  
### <a name="databases"></a><span data-ttu-id="ba29a-146">Databases</span><span class="sxs-lookup"><span data-stu-id="ba29a-146">Databases</span></span>  
  
|<span data-ttu-id="ba29a-147">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="ba29a-147">Restriction Name</span></span>|<span data-ttu-id="ba29a-148">Parametername</span><span class="sxs-lookup"><span data-stu-id="ba29a-148">Parameter Name</span></span>|<span data-ttu-id="ba29a-149">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="ba29a-149">Restriction Default</span></span>|<span data-ttu-id="ba29a-150">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="ba29a-150">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="ba29a-151">Name</span><span class="sxs-lookup"><span data-stu-id="ba29a-151">Name</span></span>|@Name|<span data-ttu-id="ba29a-152">Name</span><span class="sxs-lookup"><span data-stu-id="ba29a-152">Name</span></span>|<span data-ttu-id="ba29a-153">1</span><span class="sxs-lookup"><span data-stu-id="ba29a-153">1</span></span>|  
  
### <a name="tables"></a><span data-ttu-id="ba29a-154">Tabellen</span><span class="sxs-lookup"><span data-stu-id="ba29a-154">Tables</span></span>  
  
|<span data-ttu-id="ba29a-155">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="ba29a-155">Restriction Name</span></span>|<span data-ttu-id="ba29a-156">Parametername</span><span class="sxs-lookup"><span data-stu-id="ba29a-156">Parameter Name</span></span>|<span data-ttu-id="ba29a-157">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="ba29a-157">Restriction Default</span></span>|<span data-ttu-id="ba29a-158">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="ba29a-158">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="ba29a-159">Katalog</span><span class="sxs-lookup"><span data-stu-id="ba29a-159">Catalog</span></span>|@Catalog|<span data-ttu-id="ba29a-160">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="ba29a-160">TABLE_CATALOG</span></span>|<span data-ttu-id="ba29a-161">1</span><span class="sxs-lookup"><span data-stu-id="ba29a-161">1</span></span>|  
|<span data-ttu-id="ba29a-162">Besitzer</span><span class="sxs-lookup"><span data-stu-id="ba29a-162">Owner</span></span>|@Owner|<span data-ttu-id="ba29a-163">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="ba29a-163">TABLE_SCHEMA</span></span>|<span data-ttu-id="ba29a-164">2</span><span class="sxs-lookup"><span data-stu-id="ba29a-164">2</span></span>|  
|<span data-ttu-id="ba29a-165">Tabelle</span><span class="sxs-lookup"><span data-stu-id="ba29a-165">Table</span></span>|@Name|<span data-ttu-id="ba29a-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="ba29a-166">TABLE_NAME</span></span>|<span data-ttu-id="ba29a-167">3</span><span class="sxs-lookup"><span data-stu-id="ba29a-167">3</span></span>|  
|<span data-ttu-id="ba29a-168">TableType</span><span class="sxs-lookup"><span data-stu-id="ba29a-168">TableType</span></span>|@TableType|<span data-ttu-id="ba29a-169">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="ba29a-169">TABLE_TYPE</span></span>|<span data-ttu-id="ba29a-170">4</span><span class="sxs-lookup"><span data-stu-id="ba29a-170">4</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="ba29a-171">Spalten</span><span class="sxs-lookup"><span data-stu-id="ba29a-171">Columns</span></span>  
  
|<span data-ttu-id="ba29a-172">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="ba29a-172">Restriction Name</span></span>|<span data-ttu-id="ba29a-173">Parametername</span><span class="sxs-lookup"><span data-stu-id="ba29a-173">Parameter Name</span></span>|<span data-ttu-id="ba29a-174">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="ba29a-174">Restriction Default</span></span>|<span data-ttu-id="ba29a-175">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="ba29a-175">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="ba29a-176">Katalog</span><span class="sxs-lookup"><span data-stu-id="ba29a-176">Catalog</span></span>|@Catalog|<span data-ttu-id="ba29a-177">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="ba29a-177">TABLE_CATALOG</span></span>|<span data-ttu-id="ba29a-178">1</span><span class="sxs-lookup"><span data-stu-id="ba29a-178">1</span></span>|  
|<span data-ttu-id="ba29a-179">Besitzer</span><span class="sxs-lookup"><span data-stu-id="ba29a-179">Owner</span></span>|@Owner|<span data-ttu-id="ba29a-180">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="ba29a-180">TABLE_SCHEMA</span></span>|<span data-ttu-id="ba29a-181">2</span><span class="sxs-lookup"><span data-stu-id="ba29a-181">2</span></span>|  
|<span data-ttu-id="ba29a-182">Tabelle</span><span class="sxs-lookup"><span data-stu-id="ba29a-182">Table</span></span>|@Table|<span data-ttu-id="ba29a-183">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="ba29a-183">TABLE_NAME</span></span>|<span data-ttu-id="ba29a-184">3</span><span class="sxs-lookup"><span data-stu-id="ba29a-184">3</span></span>|  
|<span data-ttu-id="ba29a-185">Spalte</span><span class="sxs-lookup"><span data-stu-id="ba29a-185">Column</span></span>|@Column|<span data-ttu-id="ba29a-186">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="ba29a-186">COLUMN_NAME</span></span>|<span data-ttu-id="ba29a-187">4</span><span class="sxs-lookup"><span data-stu-id="ba29a-187">4</span></span>|  
  
### <a name="structuredtypemembers"></a><span data-ttu-id="ba29a-188">StructuredTypeMembers</span><span class="sxs-lookup"><span data-stu-id="ba29a-188">StructuredTypeMembers</span></span>  
  
|<span data-ttu-id="ba29a-189">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="ba29a-189">Restriction Name</span></span>|<span data-ttu-id="ba29a-190">Parametername</span><span class="sxs-lookup"><span data-stu-id="ba29a-190">Parameter Name</span></span>|<span data-ttu-id="ba29a-191">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="ba29a-191">Restriction Default</span></span>|<span data-ttu-id="ba29a-192">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="ba29a-192">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="ba29a-193">Katalog</span><span class="sxs-lookup"><span data-stu-id="ba29a-193">Catalog</span></span>|@Catalog|<span data-ttu-id="ba29a-194">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="ba29a-194">TABLE_CATALOG</span></span>|<span data-ttu-id="ba29a-195">1</span><span class="sxs-lookup"><span data-stu-id="ba29a-195">1</span></span>|  
|<span data-ttu-id="ba29a-196">Besitzer</span><span class="sxs-lookup"><span data-stu-id="ba29a-196">Owner</span></span>|@Owner|<span data-ttu-id="ba29a-197">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="ba29a-197">TABLE_SCHEMA</span></span>|<span data-ttu-id="ba29a-198">2</span><span class="sxs-lookup"><span data-stu-id="ba29a-198">2</span></span>|  
|<span data-ttu-id="ba29a-199">Tabelle</span><span class="sxs-lookup"><span data-stu-id="ba29a-199">Table</span></span>|@Table|<span data-ttu-id="ba29a-200">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="ba29a-200">TABLE_NAME</span></span>|<span data-ttu-id="ba29a-201">3</span><span class="sxs-lookup"><span data-stu-id="ba29a-201">3</span></span>|  
|<span data-ttu-id="ba29a-202">Spalte</span><span class="sxs-lookup"><span data-stu-id="ba29a-202">Column</span></span>|@Column|<span data-ttu-id="ba29a-203">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="ba29a-203">COLUMN_NAME</span></span>|<span data-ttu-id="ba29a-204">4</span><span class="sxs-lookup"><span data-stu-id="ba29a-204">4</span></span>|  
  
### <a name="views"></a><span data-ttu-id="ba29a-205">Ansichten</span><span class="sxs-lookup"><span data-stu-id="ba29a-205">Views</span></span>  
  
|<span data-ttu-id="ba29a-206">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="ba29a-206">Restriction Name</span></span>|<span data-ttu-id="ba29a-207">Parametername</span><span class="sxs-lookup"><span data-stu-id="ba29a-207">Parameter Name</span></span>|<span data-ttu-id="ba29a-208">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="ba29a-208">Restriction Default</span></span>|<span data-ttu-id="ba29a-209">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="ba29a-209">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="ba29a-210">Katalog</span><span class="sxs-lookup"><span data-stu-id="ba29a-210">Catalog</span></span>|@Catalog|<span data-ttu-id="ba29a-211">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="ba29a-211">TABLE_CATALOG</span></span>|<span data-ttu-id="ba29a-212">1</span><span class="sxs-lookup"><span data-stu-id="ba29a-212">1</span></span>|  
|<span data-ttu-id="ba29a-213">Besitzer</span><span class="sxs-lookup"><span data-stu-id="ba29a-213">Owner</span></span>|@Owner|<span data-ttu-id="ba29a-214">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="ba29a-214">TABLE_SCHEMA</span></span>|<span data-ttu-id="ba29a-215">2</span><span class="sxs-lookup"><span data-stu-id="ba29a-215">2</span></span>|  
|<span data-ttu-id="ba29a-216">Tabelle</span><span class="sxs-lookup"><span data-stu-id="ba29a-216">Table</span></span>|@Table|<span data-ttu-id="ba29a-217">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="ba29a-217">TABLE_NAME</span></span>|<span data-ttu-id="ba29a-218">3</span><span class="sxs-lookup"><span data-stu-id="ba29a-218">3</span></span>|  
  
### <a name="viewcolumns"></a><span data-ttu-id="ba29a-219">ViewColumns</span><span class="sxs-lookup"><span data-stu-id="ba29a-219">ViewColumns</span></span>  
  
|<span data-ttu-id="ba29a-220">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="ba29a-220">Restriction Name</span></span>|<span data-ttu-id="ba29a-221">Parametername</span><span class="sxs-lookup"><span data-stu-id="ba29a-221">Parameter Name</span></span>|<span data-ttu-id="ba29a-222">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="ba29a-222">Restriction Default</span></span>|<span data-ttu-id="ba29a-223">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="ba29a-223">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="ba29a-224">Katalog</span><span class="sxs-lookup"><span data-stu-id="ba29a-224">Catalog</span></span>|@Catalog|<span data-ttu-id="ba29a-225">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="ba29a-225">VIEW_CATALOG</span></span>|<span data-ttu-id="ba29a-226">1</span><span class="sxs-lookup"><span data-stu-id="ba29a-226">1</span></span>|  
|<span data-ttu-id="ba29a-227">Besitzer</span><span class="sxs-lookup"><span data-stu-id="ba29a-227">Owner</span></span>|@Owner|<span data-ttu-id="ba29a-228">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="ba29a-228">VIEW_SCHEMA</span></span>|<span data-ttu-id="ba29a-229">2</span><span class="sxs-lookup"><span data-stu-id="ba29a-229">2</span></span>|  
|<span data-ttu-id="ba29a-230">Tabelle</span><span class="sxs-lookup"><span data-stu-id="ba29a-230">Table</span></span>|@Table|<span data-ttu-id="ba29a-231">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="ba29a-231">VIEW_NAME</span></span>|<span data-ttu-id="ba29a-232">3</span><span class="sxs-lookup"><span data-stu-id="ba29a-232">3</span></span>|  
|<span data-ttu-id="ba29a-233">Spalte</span><span class="sxs-lookup"><span data-stu-id="ba29a-233">Column</span></span>|@Column|<span data-ttu-id="ba29a-234">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="ba29a-234">COLUMN_NAME</span></span>|<span data-ttu-id="ba29a-235">4</span><span class="sxs-lookup"><span data-stu-id="ba29a-235">4</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="ba29a-236">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="ba29a-236">ProcedureParameters</span></span>  
  
|<span data-ttu-id="ba29a-237">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="ba29a-237">Restriction Name</span></span>|<span data-ttu-id="ba29a-238">Parametername</span><span class="sxs-lookup"><span data-stu-id="ba29a-238">Parameter Name</span></span>|<span data-ttu-id="ba29a-239">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="ba29a-239">Restriction Default</span></span>|<span data-ttu-id="ba29a-240">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="ba29a-240">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="ba29a-241">Katalog</span><span class="sxs-lookup"><span data-stu-id="ba29a-241">Catalog</span></span>|@Catalog|<span data-ttu-id="ba29a-242">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="ba29a-242">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="ba29a-243">1</span><span class="sxs-lookup"><span data-stu-id="ba29a-243">1</span></span>|  
|<span data-ttu-id="ba29a-244">Besitzer</span><span class="sxs-lookup"><span data-stu-id="ba29a-244">Owner</span></span>|@Owner|<span data-ttu-id="ba29a-245">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="ba29a-245">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="ba29a-246">2</span><span class="sxs-lookup"><span data-stu-id="ba29a-246">2</span></span>|  
|<span data-ttu-id="ba29a-247">Name</span><span class="sxs-lookup"><span data-stu-id="ba29a-247">Name</span></span>|@Name|<span data-ttu-id="ba29a-248">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="ba29a-248">SPECIFIC_NAME</span></span>|<span data-ttu-id="ba29a-249">3</span><span class="sxs-lookup"><span data-stu-id="ba29a-249">3</span></span>|  
|<span data-ttu-id="ba29a-250">Parameter</span><span class="sxs-lookup"><span data-stu-id="ba29a-250">Parameter</span></span>|@Parameter|<span data-ttu-id="ba29a-251">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="ba29a-251">PARAMETER_NAME</span></span>|<span data-ttu-id="ba29a-252">4</span><span class="sxs-lookup"><span data-stu-id="ba29a-252">4</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="ba29a-253">Verfahren</span><span class="sxs-lookup"><span data-stu-id="ba29a-253">Procedures</span></span>  
  
|<span data-ttu-id="ba29a-254">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="ba29a-254">Restriction Name</span></span>|<span data-ttu-id="ba29a-255">Parametername</span><span class="sxs-lookup"><span data-stu-id="ba29a-255">Parameter Name</span></span>|<span data-ttu-id="ba29a-256">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="ba29a-256">Restriction Default</span></span>|<span data-ttu-id="ba29a-257">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="ba29a-257">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="ba29a-258">Katalog</span><span class="sxs-lookup"><span data-stu-id="ba29a-258">Catalog</span></span>|@Catalog|<span data-ttu-id="ba29a-259">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="ba29a-259">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="ba29a-260">1</span><span class="sxs-lookup"><span data-stu-id="ba29a-260">1</span></span>|  
|<span data-ttu-id="ba29a-261">Besitzer</span><span class="sxs-lookup"><span data-stu-id="ba29a-261">Owner</span></span>|@Owner|<span data-ttu-id="ba29a-262">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="ba29a-262">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="ba29a-263">2</span><span class="sxs-lookup"><span data-stu-id="ba29a-263">2</span></span>|  
|<span data-ttu-id="ba29a-264">Name</span><span class="sxs-lookup"><span data-stu-id="ba29a-264">Name</span></span>|@Name|<span data-ttu-id="ba29a-265">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="ba29a-265">SPECIFIC_NAME</span></span>|<span data-ttu-id="ba29a-266">3</span><span class="sxs-lookup"><span data-stu-id="ba29a-266">3</span></span>|  
|<span data-ttu-id="ba29a-267">Typ</span><span class="sxs-lookup"><span data-stu-id="ba29a-267">Type</span></span>|@Type|<span data-ttu-id="ba29a-268">ROUTINE_TYPE</span><span class="sxs-lookup"><span data-stu-id="ba29a-268">ROUTINE_TYPE</span></span>|<span data-ttu-id="ba29a-269">4</span><span class="sxs-lookup"><span data-stu-id="ba29a-269">4</span></span>|  
  
### <a name="indexcolumns"></a><span data-ttu-id="ba29a-270">IndexColumns</span><span class="sxs-lookup"><span data-stu-id="ba29a-270">IndexColumns</span></span>  
  
|<span data-ttu-id="ba29a-271">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="ba29a-271">Restriction Name</span></span>|<span data-ttu-id="ba29a-272">Parametername</span><span class="sxs-lookup"><span data-stu-id="ba29a-272">Parameter Name</span></span>|<span data-ttu-id="ba29a-273">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="ba29a-273">Restriction Default</span></span>|<span data-ttu-id="ba29a-274">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="ba29a-274">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="ba29a-275">Katalog</span><span class="sxs-lookup"><span data-stu-id="ba29a-275">Catalog</span></span>|@Catalog|<span data-ttu-id="ba29a-276">db_name()</span><span class="sxs-lookup"><span data-stu-id="ba29a-276">db_name()</span></span>|<span data-ttu-id="ba29a-277">1</span><span class="sxs-lookup"><span data-stu-id="ba29a-277">1</span></span>|  
|<span data-ttu-id="ba29a-278">Besitzer</span><span class="sxs-lookup"><span data-stu-id="ba29a-278">Owner</span></span>|@Owner|<span data-ttu-id="ba29a-279">user_name()</span><span class="sxs-lookup"><span data-stu-id="ba29a-279">user_name()</span></span>|<span data-ttu-id="ba29a-280">2</span><span class="sxs-lookup"><span data-stu-id="ba29a-280">2</span></span>|  
|<span data-ttu-id="ba29a-281">Tabelle</span><span class="sxs-lookup"><span data-stu-id="ba29a-281">Table</span></span>|@Table|<span data-ttu-id="ba29a-282">o.name</span><span class="sxs-lookup"><span data-stu-id="ba29a-282">o.name</span></span>|<span data-ttu-id="ba29a-283">3</span><span class="sxs-lookup"><span data-stu-id="ba29a-283">3</span></span>|  
|<span data-ttu-id="ba29a-284">ConstraintName</span><span class="sxs-lookup"><span data-stu-id="ba29a-284">ConstraintName</span></span>|@ConstraintName|<span data-ttu-id="ba29a-285">x.name</span><span class="sxs-lookup"><span data-stu-id="ba29a-285">x.name</span></span>|<span data-ttu-id="ba29a-286">4</span><span class="sxs-lookup"><span data-stu-id="ba29a-286">4</span></span>|  
|<span data-ttu-id="ba29a-287">Spalte</span><span class="sxs-lookup"><span data-stu-id="ba29a-287">Column</span></span>|@Column|<span data-ttu-id="ba29a-288">c.name</span><span class="sxs-lookup"><span data-stu-id="ba29a-288">c.name</span></span>|<span data-ttu-id="ba29a-289">5</span><span class="sxs-lookup"><span data-stu-id="ba29a-289">5</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="ba29a-290">Indizes</span><span class="sxs-lookup"><span data-stu-id="ba29a-290">Indexes</span></span>  
  
|<span data-ttu-id="ba29a-291">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="ba29a-291">Restriction Name</span></span>|<span data-ttu-id="ba29a-292">Parametername</span><span class="sxs-lookup"><span data-stu-id="ba29a-292">Parameter Name</span></span>|<span data-ttu-id="ba29a-293">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="ba29a-293">Restriction Default</span></span>|<span data-ttu-id="ba29a-294">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="ba29a-294">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="ba29a-295">Katalog</span><span class="sxs-lookup"><span data-stu-id="ba29a-295">Catalog</span></span>|@Catalog|<span data-ttu-id="ba29a-296">db_name()</span><span class="sxs-lookup"><span data-stu-id="ba29a-296">db_name()</span></span>|<span data-ttu-id="ba29a-297">1</span><span class="sxs-lookup"><span data-stu-id="ba29a-297">1</span></span>|  
|<span data-ttu-id="ba29a-298">Besitzer</span><span class="sxs-lookup"><span data-stu-id="ba29a-298">Owner</span></span>|@Owner|<span data-ttu-id="ba29a-299">user_name()</span><span class="sxs-lookup"><span data-stu-id="ba29a-299">user_name()</span></span>|<span data-ttu-id="ba29a-300">2</span><span class="sxs-lookup"><span data-stu-id="ba29a-300">2</span></span>|  
|<span data-ttu-id="ba29a-301">Tabelle</span><span class="sxs-lookup"><span data-stu-id="ba29a-301">Table</span></span>|@Table|<span data-ttu-id="ba29a-302">o.name</span><span class="sxs-lookup"><span data-stu-id="ba29a-302">o.name</span></span>|<span data-ttu-id="ba29a-303">3</span><span class="sxs-lookup"><span data-stu-id="ba29a-303">3</span></span>|  
  
### <a name="userdefinedtypes"></a><span data-ttu-id="ba29a-304">UserDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="ba29a-304">UserDefinedTypes</span></span>  
  
|<span data-ttu-id="ba29a-305">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="ba29a-305">Restriction Name</span></span>|<span data-ttu-id="ba29a-306">Parametername</span><span class="sxs-lookup"><span data-stu-id="ba29a-306">Parameter Name</span></span>|<span data-ttu-id="ba29a-307">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="ba29a-307">Restriction Default</span></span>|<span data-ttu-id="ba29a-308">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="ba29a-308">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="ba29a-309">assembly_name</span><span class="sxs-lookup"><span data-stu-id="ba29a-309">assembly_name</span></span>|@AssemblyName|<span data-ttu-id="ba29a-310">assemblies.name</span><span class="sxs-lookup"><span data-stu-id="ba29a-310">assemblies.name</span></span>|<span data-ttu-id="ba29a-311">1</span><span class="sxs-lookup"><span data-stu-id="ba29a-311">1</span></span>|  
|<span data-ttu-id="ba29a-312">udt_name</span><span class="sxs-lookup"><span data-stu-id="ba29a-312">udt_name</span></span>|@UDTName|<span data-ttu-id="ba29a-313">types.assembly_class</span><span class="sxs-lookup"><span data-stu-id="ba29a-313">types.assembly_class</span></span>|<span data-ttu-id="ba29a-314">2</span><span class="sxs-lookup"><span data-stu-id="ba29a-314">2</span></span>|  
  
### <a name="foreignkeys"></a><span data-ttu-id="ba29a-315">ForeignKeys</span><span class="sxs-lookup"><span data-stu-id="ba29a-315">ForeignKeys</span></span>  
  
|<span data-ttu-id="ba29a-316">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="ba29a-316">Restriction Name</span></span>|<span data-ttu-id="ba29a-317">Parametername</span><span class="sxs-lookup"><span data-stu-id="ba29a-317">Parameter Name</span></span>|<span data-ttu-id="ba29a-318">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="ba29a-318">Restriction Default</span></span>|<span data-ttu-id="ba29a-319">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="ba29a-319">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="ba29a-320">Katalog</span><span class="sxs-lookup"><span data-stu-id="ba29a-320">Catalog</span></span>|@Catalog|<span data-ttu-id="ba29a-321">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="ba29a-321">CONSTRAINT_CATALOG</span></span>|<span data-ttu-id="ba29a-322">1</span><span class="sxs-lookup"><span data-stu-id="ba29a-322">1</span></span>|  
|<span data-ttu-id="ba29a-323">Besitzer</span><span class="sxs-lookup"><span data-stu-id="ba29a-323">Owner</span></span>|@Owner|<span data-ttu-id="ba29a-324">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="ba29a-324">CONSTRAINT_SCHEMA</span></span>|<span data-ttu-id="ba29a-325">2</span><span class="sxs-lookup"><span data-stu-id="ba29a-325">2</span></span>|  
|<span data-ttu-id="ba29a-326">Tabelle</span><span class="sxs-lookup"><span data-stu-id="ba29a-326">Table</span></span>|@Table|<span data-ttu-id="ba29a-327">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="ba29a-327">TABLE_NAME</span></span>|<span data-ttu-id="ba29a-328">3</span><span class="sxs-lookup"><span data-stu-id="ba29a-328">3</span></span>|  
|<span data-ttu-id="ba29a-329">Name</span><span class="sxs-lookup"><span data-stu-id="ba29a-329">Name</span></span>|@Name|<span data-ttu-id="ba29a-330">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="ba29a-330">CONSTRAINT_NAME</span></span>|<span data-ttu-id="ba29a-331">4</span><span class="sxs-lookup"><span data-stu-id="ba29a-331">4</span></span>|  
  
## <a name="sql-server-2008-schema-restrictions"></a><span data-ttu-id="ba29a-332">SQL Server 2008-Schemabeschränkungen</span><span class="sxs-lookup"><span data-stu-id="ba29a-332">SQL Server 2008 Schema Restrictions</span></span>  
 <span data-ttu-id="ba29a-333">In den folgenden Tabellen sind die Beschränkungen für SQL Server 2008-Schemaauflistungen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="ba29a-333">The following tables list the restrictions for SQL Server 2008 schema collections.</span></span> <span data-ttu-id="ba29a-334">Diese Beschränkungen gelten ab Version 3.5 SP1 von .NET Framework und SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="ba29a-334">These restrictions are valid beginning with version 3.5 SP1 of the .NET Framework and SQL Server 2008.</span></span> <span data-ttu-id="ba29a-335">Sie werden in früheren Versionen von .NET Framework und SQL Server nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ba29a-335">They are not supported in earlier versions of the .NET Framework and SQL Server.</span></span>  
  
### <a name="columnsetcolumns"></a><span data-ttu-id="ba29a-336">ColumnSetColumns</span><span class="sxs-lookup"><span data-stu-id="ba29a-336">ColumnSetColumns</span></span>  
  
|<span data-ttu-id="ba29a-337">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="ba29a-337">Restriction Name</span></span>|<span data-ttu-id="ba29a-338">Parametername</span><span class="sxs-lookup"><span data-stu-id="ba29a-338">Parameter Name</span></span>|<span data-ttu-id="ba29a-339">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="ba29a-339">Restriction Default</span></span>|<span data-ttu-id="ba29a-340">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="ba29a-340">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="ba29a-341">Katalog</span><span class="sxs-lookup"><span data-stu-id="ba29a-341">Catalog</span></span>|@Catalog|<span data-ttu-id="ba29a-342">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="ba29a-342">TABLE_CATALOG</span></span>|<span data-ttu-id="ba29a-343">1</span><span class="sxs-lookup"><span data-stu-id="ba29a-343">1</span></span>|  
|<span data-ttu-id="ba29a-344">Besitzer</span><span class="sxs-lookup"><span data-stu-id="ba29a-344">Owner</span></span>|@Owner|<span data-ttu-id="ba29a-345">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="ba29a-345">TABLE_SCHEMA</span></span>|<span data-ttu-id="ba29a-346">2</span><span class="sxs-lookup"><span data-stu-id="ba29a-346">2</span></span>|  
|<span data-ttu-id="ba29a-347">Tabelle</span><span class="sxs-lookup"><span data-stu-id="ba29a-347">Table</span></span>|@Table|<span data-ttu-id="ba29a-348">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="ba29a-348">TABLE_NAME</span></span>|<span data-ttu-id="ba29a-349">3</span><span class="sxs-lookup"><span data-stu-id="ba29a-349">3</span></span>|  
  
### <a name="allcolumns"></a><span data-ttu-id="ba29a-350">AllColumns</span><span class="sxs-lookup"><span data-stu-id="ba29a-350">AllColumns</span></span>  
  
|<span data-ttu-id="ba29a-351">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="ba29a-351">Restriction Name</span></span>|<span data-ttu-id="ba29a-352">Parametername</span><span class="sxs-lookup"><span data-stu-id="ba29a-352">Parameter Name</span></span>|<span data-ttu-id="ba29a-353">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="ba29a-353">Restriction Default</span></span>|<span data-ttu-id="ba29a-354">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="ba29a-354">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="ba29a-355">Katalog</span><span class="sxs-lookup"><span data-stu-id="ba29a-355">Catalog</span></span>|@Catalog|<span data-ttu-id="ba29a-356">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="ba29a-356">TABLE_CATALOG</span></span>|<span data-ttu-id="ba29a-357">1</span><span class="sxs-lookup"><span data-stu-id="ba29a-357">1</span></span>|  
|<span data-ttu-id="ba29a-358">Besitzer</span><span class="sxs-lookup"><span data-stu-id="ba29a-358">Owner</span></span>|@Owner|<span data-ttu-id="ba29a-359">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="ba29a-359">TABLE_SCHEMA</span></span>|<span data-ttu-id="ba29a-360">2</span><span class="sxs-lookup"><span data-stu-id="ba29a-360">2</span></span>|  
|<span data-ttu-id="ba29a-361">Tabelle</span><span class="sxs-lookup"><span data-stu-id="ba29a-361">Table</span></span>|@Table|<span data-ttu-id="ba29a-362">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="ba29a-362">TABLE_NAME</span></span>|<span data-ttu-id="ba29a-363">3</span><span class="sxs-lookup"><span data-stu-id="ba29a-363">3</span></span>|  
|<span data-ttu-id="ba29a-364">Spalte</span><span class="sxs-lookup"><span data-stu-id="ba29a-364">Column</span></span>|@Column|<span data-ttu-id="ba29a-365">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="ba29a-365">COLUMN_NAME</span></span>|<span data-ttu-id="ba29a-366">4</span><span class="sxs-lookup"><span data-stu-id="ba29a-366">4</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ba29a-367">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba29a-367">See also</span></span>

- [<span data-ttu-id="ba29a-368">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ba29a-368">ADO.NET Overview</span></span>](ado-net-overview.md)
