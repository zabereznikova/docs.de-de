---
title: Schemaeinschränkungen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
ms.openlocfilehash: 1a2c32d133799ee5338c18d0f51bced49cb3dc4b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963181"
---
# <a name="schema-restrictions"></a><span data-ttu-id="8610c-102">Schemaeinschränkungen</span><span class="sxs-lookup"><span data-stu-id="8610c-102">Schema Restrictions</span></span>
<span data-ttu-id="8610c-103">Der zweite optionale Parameter der **GetSchema** -Methode sind die Einschränkungen, die verwendet werden, um die Menge der zurückgegebenen Schema Informationen einzuschränken, und Sie werden als Zeichen folgen Array an die **GetSchema** -Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="8610c-103">The second optional parameter of the **GetSchema** method is the restrictions that are used to limit the amount of schema information returned, and it is passed to the **GetSchema** method as an array of strings.</span></span> <span data-ttu-id="8610c-104">Die Position im Array bestimmt die Werte, die zurückgegeben werden können. Dies entspricht der Anzahl der Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="8610c-104">The position in the array determines the values that you can pass, and this is equivalent to the restriction number.</span></span>  
  
 <span data-ttu-id="8610c-105">In der folgenden Tabelle werden beispielsweise die Einschränkungen beschrieben, die von der Schemaauflistung "Tables" mithilfe des .NET Framework-Datenanbieters für SQL Server unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="8610c-105">For example, the following table describes the restrictions supported by the "Tables" schema collection using the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="8610c-106">Zusätzliche Einschränkungen für SQL Server-Schemaauflistungen werden am Ende dieses Themas aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="8610c-106">Additional restrictions for SQL Server schema collections are listed at the end of this topic.</span></span>  
  
|<span data-ttu-id="8610c-107">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="8610c-107">Restriction Name</span></span>|<span data-ttu-id="8610c-108">Parametername</span><span class="sxs-lookup"><span data-stu-id="8610c-108">Parameter Name</span></span>|<span data-ttu-id="8610c-109">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="8610c-109">Restriction Default</span></span>|<span data-ttu-id="8610c-110">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="8610c-110">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="8610c-111">Katalog</span><span class="sxs-lookup"><span data-stu-id="8610c-111">Catalog</span></span>|@Catalog|<span data-ttu-id="8610c-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8610c-112">TABLE_CATALOG</span></span>|<span data-ttu-id="8610c-113">1</span><span class="sxs-lookup"><span data-stu-id="8610c-113">1</span></span>|  
|<span data-ttu-id="8610c-114">Besitzer</span><span class="sxs-lookup"><span data-stu-id="8610c-114">Owner</span></span>|@Owner|<span data-ttu-id="8610c-115">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8610c-115">TABLE_SCHEMA</span></span>|<span data-ttu-id="8610c-116">2</span><span class="sxs-lookup"><span data-stu-id="8610c-116">2</span></span>|  
|<span data-ttu-id="8610c-117">Tabelle</span><span class="sxs-lookup"><span data-stu-id="8610c-117">Table</span></span>|@Name|<span data-ttu-id="8610c-118">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8610c-118">TABLE_NAME</span></span>|<span data-ttu-id="8610c-119">3</span><span class="sxs-lookup"><span data-stu-id="8610c-119">3</span></span>|  
|<span data-ttu-id="8610c-120">TableType</span><span class="sxs-lookup"><span data-stu-id="8610c-120">TableType</span></span>|@TableType|<span data-ttu-id="8610c-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="8610c-121">TABLE_TYPE</span></span>|<span data-ttu-id="8610c-122">4</span><span class="sxs-lookup"><span data-stu-id="8610c-122">4</span></span>|  
  
## <a name="specifying-restriction-values"></a><span data-ttu-id="8610c-123">Angeben der Einschränkungswerte</span><span class="sxs-lookup"><span data-stu-id="8610c-123">Specifying Restriction Values</span></span>  
 <span data-ttu-id="8610c-124">Wenn Sie eine der Einschränkungen der Tables-Schemaauflistung verwenden möchten, erstellen Sie ein Zeichenfolgenarray mit vier Elementen und fügen einen Wert in das Element ein, das mit der Einschränkungsnummer übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="8610c-124">To use one of the restrictions of the "Tables" schema collection, simply create an array of strings with four elements, then place a value in the element that matches the restriction number.</span></span> <span data-ttu-id="8610c-125">Um beispielsweise die von der **GetSchema** -Methode zurückgegebenen Tabellen nur auf die Tabellen im "Sales"-Schema zu beschränken, legen Sie das zweite Element des Arrays auf "Sales" fest, bevor Sie es an die **GetSchema** -Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="8610c-125">For example, to restrict the tables returned by the **GetSchema** method to only those tables in the "Sales" schema, set the second element of the array to "Sales" before passing it to the **GetSchema** method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8610c-126">Die Einschränkungsauflistungen für den `SqlClient` und den `OracleClient` verfügen über eine zusätzliche `ParameterName`-Spalte.</span><span class="sxs-lookup"><span data-stu-id="8610c-126">The restrictions collections for `SqlClient` and `OracleClient` have an additional `ParameterName` column.</span></span> <span data-ttu-id="8610c-127">Die Spalte für den Einschränkungsstandard ist zwar aus Gründen der Abwärtskompatibilität vorhanden, wird aber derzeit ignoriert.</span><span class="sxs-lookup"><span data-stu-id="8610c-127">The restriction default column is still there for backwards compatibility, but is currently ignored.</span></span> <span data-ttu-id="8610c-128">Verwenden Sie Abfragen mit Parametern statt Zeichenfolgenersetzungen, um das Risiko eines SQL-Injection-Angriffs beim Angeben der Einschränkungswerte zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="8610c-128">Parameterized queries rather than string replacement should be used to minimize the risk of an SQL injection attack when specifying restriction values.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8610c-129">Die Anzahl der Elementen im Array muss kleiner oder gleich der Anzahl der Einschränkungen sein, die für die angegebene Schemaauflistung unterstützt werden, da sonst eine <xref:System.ArgumentException> ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="8610c-129">The number of elements in the array must be less than or equal to the number of restrictions supported for the specified schema collection else an <xref:System.ArgumentException> will be thrown.</span></span> <span data-ttu-id="8610c-130">Es können weniger Elemente als die maximale Anzahl der Einschränkungen vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="8610c-130">There can be fewer than the maximum number of restrictions.</span></span> <span data-ttu-id="8610c-131">Es wird davon ausgegangen, dass die fehlenden Einschränkungen NULL (uneingeschränkt) sind.</span><span class="sxs-lookup"><span data-stu-id="8610c-131">The missing restrictions are assumed to be null (unrestricted).</span></span>  
  
 <span data-ttu-id="8610c-132">Sie können einen .NET Framework verwalteten Anbieter Abfragen, um die Liste der unterstützten Einschränkungen zu ermitteln, indem Sie die **GetSchema** -Methode mit dem Namen der Einschränkungs Schema Auflistung aufrufen. Dies ist "Einschränkungen".</span><span class="sxs-lookup"><span data-stu-id="8610c-132">You can query a .NET Framework managed provider to determine the list of supported restrictions by calling the **GetSchema** method with the name of the restrictions schema collection, which is "Restrictions".</span></span> <span data-ttu-id="8610c-133">Dabei wird eine <xref:System.Data.DataTable> mit einer Liste der Auflistungsnamen, Einschränkungsnamen, Standardeinschränkungswerte und der Anzahl der Einschränkungen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8610c-133">This will return a <xref:System.Data.DataTable> with a list of the collection names, the restriction names, the default restriction values, and the restriction numbers.</span></span>  
  
### <a name="example"></a><span data-ttu-id="8610c-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8610c-134">Example</span></span>  
 <span data-ttu-id="8610c-135">In den folgenden Beispielen wird veranschaulicht, wie <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> die-Methode der .NET Framework Datenanbieter für die <xref:System.Data.SqlClient.SqlConnection> SQL Server-Klasse verwendet wird, um Schema Informationen zu allen Tabellen abzurufen, die in der **AdventureWorks** -Beispieldatenbank enthalten sind. und um die Informationen einzuschränken, die nur auf die Tabellen im "Sales"-Schema zurückgegeben werden:</span><span class="sxs-lookup"><span data-stu-id="8610c-135">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database, and to restrict the information returned to only those tables in the "Sales" schema:</span></span>  
  
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
  
## <a name="sql-server-schema-restrictions"></a><span data-ttu-id="8610c-136">SQL Server-Schemabeschränkungen</span><span class="sxs-lookup"><span data-stu-id="8610c-136">SQL Server Schema Restrictions</span></span>  
 <span data-ttu-id="8610c-137">In den folgenden Tabellen sind die Beschränkungen für SQL Server-Schemaauflistungen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="8610c-137">The following tables list the restrictions for SQL Server schema collections.</span></span>  
  
### <a name="users"></a><span data-ttu-id="8610c-138">Benutzer</span><span class="sxs-lookup"><span data-stu-id="8610c-138">Users</span></span>  
  
|<span data-ttu-id="8610c-139">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="8610c-139">Restriction Name</span></span>|<span data-ttu-id="8610c-140">Parametername</span><span class="sxs-lookup"><span data-stu-id="8610c-140">Parameter Name</span></span>|<span data-ttu-id="8610c-141">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="8610c-141">Restriction Default</span></span>|<span data-ttu-id="8610c-142">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="8610c-142">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="8610c-143">User_Name</span><span class="sxs-lookup"><span data-stu-id="8610c-143">User_Name</span></span>|@Name|<span data-ttu-id="8610c-144">Name</span><span class="sxs-lookup"><span data-stu-id="8610c-144">name</span></span>|<span data-ttu-id="8610c-145">1</span><span class="sxs-lookup"><span data-stu-id="8610c-145">1</span></span>|  
  
### <a name="databases"></a><span data-ttu-id="8610c-146">Databases</span><span class="sxs-lookup"><span data-stu-id="8610c-146">Databases</span></span>  
  
|<span data-ttu-id="8610c-147">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="8610c-147">Restriction Name</span></span>|<span data-ttu-id="8610c-148">Parametername</span><span class="sxs-lookup"><span data-stu-id="8610c-148">Parameter Name</span></span>|<span data-ttu-id="8610c-149">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="8610c-149">Restriction Default</span></span>|<span data-ttu-id="8610c-150">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="8610c-150">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="8610c-151">Name</span><span class="sxs-lookup"><span data-stu-id="8610c-151">Name</span></span>|@Name|<span data-ttu-id="8610c-152">Name</span><span class="sxs-lookup"><span data-stu-id="8610c-152">Name</span></span>|<span data-ttu-id="8610c-153">1</span><span class="sxs-lookup"><span data-stu-id="8610c-153">1</span></span>|  
  
### <a name="tables"></a><span data-ttu-id="8610c-154">Tabellen</span><span class="sxs-lookup"><span data-stu-id="8610c-154">Tables</span></span>  
  
|<span data-ttu-id="8610c-155">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="8610c-155">Restriction Name</span></span>|<span data-ttu-id="8610c-156">Parametername</span><span class="sxs-lookup"><span data-stu-id="8610c-156">Parameter Name</span></span>|<span data-ttu-id="8610c-157">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="8610c-157">Restriction Default</span></span>|<span data-ttu-id="8610c-158">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="8610c-158">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="8610c-159">Katalog</span><span class="sxs-lookup"><span data-stu-id="8610c-159">Catalog</span></span>|@Catalog|<span data-ttu-id="8610c-160">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8610c-160">TABLE_CATALOG</span></span>|<span data-ttu-id="8610c-161">1</span><span class="sxs-lookup"><span data-stu-id="8610c-161">1</span></span>|  
|<span data-ttu-id="8610c-162">Besitzer</span><span class="sxs-lookup"><span data-stu-id="8610c-162">Owner</span></span>|@Owner|<span data-ttu-id="8610c-163">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8610c-163">TABLE_SCHEMA</span></span>|<span data-ttu-id="8610c-164">2</span><span class="sxs-lookup"><span data-stu-id="8610c-164">2</span></span>|  
|<span data-ttu-id="8610c-165">Tabelle</span><span class="sxs-lookup"><span data-stu-id="8610c-165">Table</span></span>|@Name|<span data-ttu-id="8610c-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8610c-166">TABLE_NAME</span></span>|<span data-ttu-id="8610c-167">3</span><span class="sxs-lookup"><span data-stu-id="8610c-167">3</span></span>|  
|<span data-ttu-id="8610c-168">TableType</span><span class="sxs-lookup"><span data-stu-id="8610c-168">TableType</span></span>|@TableType|<span data-ttu-id="8610c-169">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="8610c-169">TABLE_TYPE</span></span>|<span data-ttu-id="8610c-170">4</span><span class="sxs-lookup"><span data-stu-id="8610c-170">4</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="8610c-171">Spalten</span><span class="sxs-lookup"><span data-stu-id="8610c-171">Columns</span></span>  
  
|<span data-ttu-id="8610c-172">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="8610c-172">Restriction Name</span></span>|<span data-ttu-id="8610c-173">Parametername</span><span class="sxs-lookup"><span data-stu-id="8610c-173">Parameter Name</span></span>|<span data-ttu-id="8610c-174">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="8610c-174">Restriction Default</span></span>|<span data-ttu-id="8610c-175">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="8610c-175">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="8610c-176">Katalog</span><span class="sxs-lookup"><span data-stu-id="8610c-176">Catalog</span></span>|@Catalog|<span data-ttu-id="8610c-177">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8610c-177">TABLE_CATALOG</span></span>|<span data-ttu-id="8610c-178">1</span><span class="sxs-lookup"><span data-stu-id="8610c-178">1</span></span>|  
|<span data-ttu-id="8610c-179">Besitzer</span><span class="sxs-lookup"><span data-stu-id="8610c-179">Owner</span></span>|@Owner|<span data-ttu-id="8610c-180">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8610c-180">TABLE_SCHEMA</span></span>|<span data-ttu-id="8610c-181">2</span><span class="sxs-lookup"><span data-stu-id="8610c-181">2</span></span>|  
|<span data-ttu-id="8610c-182">Tabelle</span><span class="sxs-lookup"><span data-stu-id="8610c-182">Table</span></span>|@Table|<span data-ttu-id="8610c-183">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8610c-183">TABLE_NAME</span></span>|<span data-ttu-id="8610c-184">3</span><span class="sxs-lookup"><span data-stu-id="8610c-184">3</span></span>|  
|<span data-ttu-id="8610c-185">Spalte</span><span class="sxs-lookup"><span data-stu-id="8610c-185">Column</span></span>|@Column|<span data-ttu-id="8610c-186">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="8610c-186">COLUMN_NAME</span></span>|<span data-ttu-id="8610c-187">4</span><span class="sxs-lookup"><span data-stu-id="8610c-187">4</span></span>|  
  
### <a name="structuredtypemembers"></a><span data-ttu-id="8610c-188">StructuredTypeMembers</span><span class="sxs-lookup"><span data-stu-id="8610c-188">StructuredTypeMembers</span></span>  
  
|<span data-ttu-id="8610c-189">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="8610c-189">Restriction Name</span></span>|<span data-ttu-id="8610c-190">Parametername</span><span class="sxs-lookup"><span data-stu-id="8610c-190">Parameter Name</span></span>|<span data-ttu-id="8610c-191">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="8610c-191">Restriction Default</span></span>|<span data-ttu-id="8610c-192">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="8610c-192">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="8610c-193">Katalog</span><span class="sxs-lookup"><span data-stu-id="8610c-193">Catalog</span></span>|@Catalog|<span data-ttu-id="8610c-194">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8610c-194">TABLE_CATALOG</span></span>|<span data-ttu-id="8610c-195">1</span><span class="sxs-lookup"><span data-stu-id="8610c-195">1</span></span>|  
|<span data-ttu-id="8610c-196">Besitzer</span><span class="sxs-lookup"><span data-stu-id="8610c-196">Owner</span></span>|@Owner|<span data-ttu-id="8610c-197">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8610c-197">TABLE_SCHEMA</span></span>|<span data-ttu-id="8610c-198">2</span><span class="sxs-lookup"><span data-stu-id="8610c-198">2</span></span>|  
|<span data-ttu-id="8610c-199">Tabelle</span><span class="sxs-lookup"><span data-stu-id="8610c-199">Table</span></span>|@Table|<span data-ttu-id="8610c-200">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8610c-200">TABLE_NAME</span></span>|<span data-ttu-id="8610c-201">3</span><span class="sxs-lookup"><span data-stu-id="8610c-201">3</span></span>|  
|<span data-ttu-id="8610c-202">Spalte</span><span class="sxs-lookup"><span data-stu-id="8610c-202">Column</span></span>|@Column|<span data-ttu-id="8610c-203">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="8610c-203">COLUMN_NAME</span></span>|<span data-ttu-id="8610c-204">4</span><span class="sxs-lookup"><span data-stu-id="8610c-204">4</span></span>|  
  
### <a name="views"></a><span data-ttu-id="8610c-205">Ansichten</span><span class="sxs-lookup"><span data-stu-id="8610c-205">Views</span></span>  
  
|<span data-ttu-id="8610c-206">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="8610c-206">Restriction Name</span></span>|<span data-ttu-id="8610c-207">Parametername</span><span class="sxs-lookup"><span data-stu-id="8610c-207">Parameter Name</span></span>|<span data-ttu-id="8610c-208">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="8610c-208">Restriction Default</span></span>|<span data-ttu-id="8610c-209">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="8610c-209">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="8610c-210">Katalog</span><span class="sxs-lookup"><span data-stu-id="8610c-210">Catalog</span></span>|@Catalog|<span data-ttu-id="8610c-211">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8610c-211">TABLE_CATALOG</span></span>|<span data-ttu-id="8610c-212">1</span><span class="sxs-lookup"><span data-stu-id="8610c-212">1</span></span>|  
|<span data-ttu-id="8610c-213">Besitzer</span><span class="sxs-lookup"><span data-stu-id="8610c-213">Owner</span></span>|@Owner|<span data-ttu-id="8610c-214">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8610c-214">TABLE_SCHEMA</span></span>|<span data-ttu-id="8610c-215">2</span><span class="sxs-lookup"><span data-stu-id="8610c-215">2</span></span>|  
|<span data-ttu-id="8610c-216">Tabelle</span><span class="sxs-lookup"><span data-stu-id="8610c-216">Table</span></span>|@Table|<span data-ttu-id="8610c-217">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8610c-217">TABLE_NAME</span></span>|<span data-ttu-id="8610c-218">3</span><span class="sxs-lookup"><span data-stu-id="8610c-218">3</span></span>|  
  
### <a name="viewcolumns"></a><span data-ttu-id="8610c-219">ViewColumns</span><span class="sxs-lookup"><span data-stu-id="8610c-219">ViewColumns</span></span>  
  
|<span data-ttu-id="8610c-220">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="8610c-220">Restriction Name</span></span>|<span data-ttu-id="8610c-221">Parametername</span><span class="sxs-lookup"><span data-stu-id="8610c-221">Parameter Name</span></span>|<span data-ttu-id="8610c-222">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="8610c-222">Restriction Default</span></span>|<span data-ttu-id="8610c-223">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="8610c-223">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="8610c-224">Katalog</span><span class="sxs-lookup"><span data-stu-id="8610c-224">Catalog</span></span>|@Catalog|<span data-ttu-id="8610c-225">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8610c-225">VIEW_CATALOG</span></span>|<span data-ttu-id="8610c-226">1</span><span class="sxs-lookup"><span data-stu-id="8610c-226">1</span></span>|  
|<span data-ttu-id="8610c-227">Besitzer</span><span class="sxs-lookup"><span data-stu-id="8610c-227">Owner</span></span>|@Owner|<span data-ttu-id="8610c-228">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8610c-228">VIEW_SCHEMA</span></span>|<span data-ttu-id="8610c-229">2</span><span class="sxs-lookup"><span data-stu-id="8610c-229">2</span></span>|  
|<span data-ttu-id="8610c-230">Tabelle</span><span class="sxs-lookup"><span data-stu-id="8610c-230">Table</span></span>|@Table|<span data-ttu-id="8610c-231">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="8610c-231">VIEW_NAME</span></span>|<span data-ttu-id="8610c-232">3</span><span class="sxs-lookup"><span data-stu-id="8610c-232">3</span></span>|  
|<span data-ttu-id="8610c-233">Spalte</span><span class="sxs-lookup"><span data-stu-id="8610c-233">Column</span></span>|@Column|<span data-ttu-id="8610c-234">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="8610c-234">COLUMN_NAME</span></span>|<span data-ttu-id="8610c-235">4</span><span class="sxs-lookup"><span data-stu-id="8610c-235">4</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="8610c-236">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="8610c-236">ProcedureParameters</span></span>  
  
|<span data-ttu-id="8610c-237">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="8610c-237">Restriction Name</span></span>|<span data-ttu-id="8610c-238">Parametername</span><span class="sxs-lookup"><span data-stu-id="8610c-238">Parameter Name</span></span>|<span data-ttu-id="8610c-239">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="8610c-239">Restriction Default</span></span>|<span data-ttu-id="8610c-240">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="8610c-240">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="8610c-241">Katalog</span><span class="sxs-lookup"><span data-stu-id="8610c-241">Catalog</span></span>|@Catalog|<span data-ttu-id="8610c-242">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8610c-242">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="8610c-243">1</span><span class="sxs-lookup"><span data-stu-id="8610c-243">1</span></span>|  
|<span data-ttu-id="8610c-244">Besitzer</span><span class="sxs-lookup"><span data-stu-id="8610c-244">Owner</span></span>|@Owner|<span data-ttu-id="8610c-245">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8610c-245">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="8610c-246">2</span><span class="sxs-lookup"><span data-stu-id="8610c-246">2</span></span>|  
|<span data-ttu-id="8610c-247">Name</span><span class="sxs-lookup"><span data-stu-id="8610c-247">Name</span></span>|@Name|<span data-ttu-id="8610c-248">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="8610c-248">SPECIFIC_NAME</span></span>|<span data-ttu-id="8610c-249">3</span><span class="sxs-lookup"><span data-stu-id="8610c-249">3</span></span>|  
|<span data-ttu-id="8610c-250">Parameter</span><span class="sxs-lookup"><span data-stu-id="8610c-250">Parameter</span></span>|@Parameter|<span data-ttu-id="8610c-251">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="8610c-251">PARAMETER_NAME</span></span>|<span data-ttu-id="8610c-252">4</span><span class="sxs-lookup"><span data-stu-id="8610c-252">4</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="8610c-253">Verfahren</span><span class="sxs-lookup"><span data-stu-id="8610c-253">Procedures</span></span>  
  
|<span data-ttu-id="8610c-254">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="8610c-254">Restriction Name</span></span>|<span data-ttu-id="8610c-255">Parametername</span><span class="sxs-lookup"><span data-stu-id="8610c-255">Parameter Name</span></span>|<span data-ttu-id="8610c-256">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="8610c-256">Restriction Default</span></span>|<span data-ttu-id="8610c-257">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="8610c-257">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="8610c-258">Katalog</span><span class="sxs-lookup"><span data-stu-id="8610c-258">Catalog</span></span>|@Catalog|<span data-ttu-id="8610c-259">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8610c-259">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="8610c-260">1</span><span class="sxs-lookup"><span data-stu-id="8610c-260">1</span></span>|  
|<span data-ttu-id="8610c-261">Besitzer</span><span class="sxs-lookup"><span data-stu-id="8610c-261">Owner</span></span>|@Owner|<span data-ttu-id="8610c-262">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8610c-262">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="8610c-263">2</span><span class="sxs-lookup"><span data-stu-id="8610c-263">2</span></span>|  
|<span data-ttu-id="8610c-264">Name</span><span class="sxs-lookup"><span data-stu-id="8610c-264">Name</span></span>|@Name|<span data-ttu-id="8610c-265">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="8610c-265">SPECIFIC_NAME</span></span>|<span data-ttu-id="8610c-266">3</span><span class="sxs-lookup"><span data-stu-id="8610c-266">3</span></span>|  
|<span data-ttu-id="8610c-267">Typ</span><span class="sxs-lookup"><span data-stu-id="8610c-267">Type</span></span>|@Type|<span data-ttu-id="8610c-268">ROUTINE_TYPE</span><span class="sxs-lookup"><span data-stu-id="8610c-268">ROUTINE_TYPE</span></span>|<span data-ttu-id="8610c-269">4</span><span class="sxs-lookup"><span data-stu-id="8610c-269">4</span></span>|  
  
### <a name="indexcolumns"></a><span data-ttu-id="8610c-270">IndexColumns</span><span class="sxs-lookup"><span data-stu-id="8610c-270">IndexColumns</span></span>  
  
|<span data-ttu-id="8610c-271">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="8610c-271">Restriction Name</span></span>|<span data-ttu-id="8610c-272">Parametername</span><span class="sxs-lookup"><span data-stu-id="8610c-272">Parameter Name</span></span>|<span data-ttu-id="8610c-273">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="8610c-273">Restriction Default</span></span>|<span data-ttu-id="8610c-274">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="8610c-274">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="8610c-275">Katalog</span><span class="sxs-lookup"><span data-stu-id="8610c-275">Catalog</span></span>|@Catalog|<span data-ttu-id="8610c-276">db_name()</span><span class="sxs-lookup"><span data-stu-id="8610c-276">db_name()</span></span>|<span data-ttu-id="8610c-277">1</span><span class="sxs-lookup"><span data-stu-id="8610c-277">1</span></span>|  
|<span data-ttu-id="8610c-278">Besitzer</span><span class="sxs-lookup"><span data-stu-id="8610c-278">Owner</span></span>|@Owner|<span data-ttu-id="8610c-279">user_name()</span><span class="sxs-lookup"><span data-stu-id="8610c-279">user_name()</span></span>|<span data-ttu-id="8610c-280">2</span><span class="sxs-lookup"><span data-stu-id="8610c-280">2</span></span>|  
|<span data-ttu-id="8610c-281">Tabelle</span><span class="sxs-lookup"><span data-stu-id="8610c-281">Table</span></span>|@Table|<span data-ttu-id="8610c-282">o.name</span><span class="sxs-lookup"><span data-stu-id="8610c-282">o.name</span></span>|<span data-ttu-id="8610c-283">3</span><span class="sxs-lookup"><span data-stu-id="8610c-283">3</span></span>|  
|<span data-ttu-id="8610c-284">ConstraintName</span><span class="sxs-lookup"><span data-stu-id="8610c-284">ConstraintName</span></span>|@ConstraintName|<span data-ttu-id="8610c-285">x.name</span><span class="sxs-lookup"><span data-stu-id="8610c-285">x.name</span></span>|<span data-ttu-id="8610c-286">4</span><span class="sxs-lookup"><span data-stu-id="8610c-286">4</span></span>|  
|<span data-ttu-id="8610c-287">Spalte</span><span class="sxs-lookup"><span data-stu-id="8610c-287">Column</span></span>|@Column|<span data-ttu-id="8610c-288">c.name</span><span class="sxs-lookup"><span data-stu-id="8610c-288">c.name</span></span>|<span data-ttu-id="8610c-289">5</span><span class="sxs-lookup"><span data-stu-id="8610c-289">5</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="8610c-290">Indizes</span><span class="sxs-lookup"><span data-stu-id="8610c-290">Indexes</span></span>  
  
|<span data-ttu-id="8610c-291">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="8610c-291">Restriction Name</span></span>|<span data-ttu-id="8610c-292">Parametername</span><span class="sxs-lookup"><span data-stu-id="8610c-292">Parameter Name</span></span>|<span data-ttu-id="8610c-293">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="8610c-293">Restriction Default</span></span>|<span data-ttu-id="8610c-294">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="8610c-294">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="8610c-295">Katalog</span><span class="sxs-lookup"><span data-stu-id="8610c-295">Catalog</span></span>|@Catalog|<span data-ttu-id="8610c-296">db_name()</span><span class="sxs-lookup"><span data-stu-id="8610c-296">db_name()</span></span>|<span data-ttu-id="8610c-297">1</span><span class="sxs-lookup"><span data-stu-id="8610c-297">1</span></span>|  
|<span data-ttu-id="8610c-298">Besitzer</span><span class="sxs-lookup"><span data-stu-id="8610c-298">Owner</span></span>|@Owner|<span data-ttu-id="8610c-299">user_name()</span><span class="sxs-lookup"><span data-stu-id="8610c-299">user_name()</span></span>|<span data-ttu-id="8610c-300">2</span><span class="sxs-lookup"><span data-stu-id="8610c-300">2</span></span>|  
|<span data-ttu-id="8610c-301">Tabelle</span><span class="sxs-lookup"><span data-stu-id="8610c-301">Table</span></span>|@Table|<span data-ttu-id="8610c-302">o.name</span><span class="sxs-lookup"><span data-stu-id="8610c-302">o.name</span></span>|<span data-ttu-id="8610c-303">3</span><span class="sxs-lookup"><span data-stu-id="8610c-303">3</span></span>|  
  
### <a name="userdefinedtypes"></a><span data-ttu-id="8610c-304">UserDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="8610c-304">UserDefinedTypes</span></span>  
  
|<span data-ttu-id="8610c-305">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="8610c-305">Restriction Name</span></span>|<span data-ttu-id="8610c-306">Parametername</span><span class="sxs-lookup"><span data-stu-id="8610c-306">Parameter Name</span></span>|<span data-ttu-id="8610c-307">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="8610c-307">Restriction Default</span></span>|<span data-ttu-id="8610c-308">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="8610c-308">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="8610c-309">assembly_name</span><span class="sxs-lookup"><span data-stu-id="8610c-309">assembly_name</span></span>|@AssemblyName|<span data-ttu-id="8610c-310">assemblies.name</span><span class="sxs-lookup"><span data-stu-id="8610c-310">assemblies.name</span></span>|<span data-ttu-id="8610c-311">1</span><span class="sxs-lookup"><span data-stu-id="8610c-311">1</span></span>|  
|<span data-ttu-id="8610c-312">udt_name</span><span class="sxs-lookup"><span data-stu-id="8610c-312">udt_name</span></span>|@UDTName|<span data-ttu-id="8610c-313">types.assembly_class</span><span class="sxs-lookup"><span data-stu-id="8610c-313">types.assembly_class</span></span>|<span data-ttu-id="8610c-314">2</span><span class="sxs-lookup"><span data-stu-id="8610c-314">2</span></span>|  
  
### <a name="foreignkeys"></a><span data-ttu-id="8610c-315">ForeignKeys</span><span class="sxs-lookup"><span data-stu-id="8610c-315">ForeignKeys</span></span>  
  
|<span data-ttu-id="8610c-316">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="8610c-316">Restriction Name</span></span>|<span data-ttu-id="8610c-317">Parametername</span><span class="sxs-lookup"><span data-stu-id="8610c-317">Parameter Name</span></span>|<span data-ttu-id="8610c-318">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="8610c-318">Restriction Default</span></span>|<span data-ttu-id="8610c-319">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="8610c-319">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="8610c-320">Katalog</span><span class="sxs-lookup"><span data-stu-id="8610c-320">Catalog</span></span>|@Catalog|<span data-ttu-id="8610c-321">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8610c-321">CONSTRAINT_CATALOG</span></span>|<span data-ttu-id="8610c-322">1</span><span class="sxs-lookup"><span data-stu-id="8610c-322">1</span></span>|  
|<span data-ttu-id="8610c-323">Besitzer</span><span class="sxs-lookup"><span data-stu-id="8610c-323">Owner</span></span>|@Owner|<span data-ttu-id="8610c-324">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8610c-324">CONSTRAINT_SCHEMA</span></span>|<span data-ttu-id="8610c-325">2</span><span class="sxs-lookup"><span data-stu-id="8610c-325">2</span></span>|  
|<span data-ttu-id="8610c-326">Tabelle</span><span class="sxs-lookup"><span data-stu-id="8610c-326">Table</span></span>|@Table|<span data-ttu-id="8610c-327">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8610c-327">TABLE_NAME</span></span>|<span data-ttu-id="8610c-328">3</span><span class="sxs-lookup"><span data-stu-id="8610c-328">3</span></span>|  
|<span data-ttu-id="8610c-329">Name</span><span class="sxs-lookup"><span data-stu-id="8610c-329">Name</span></span>|@Name|<span data-ttu-id="8610c-330">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="8610c-330">CONSTRAINT_NAME</span></span>|<span data-ttu-id="8610c-331">4</span><span class="sxs-lookup"><span data-stu-id="8610c-331">4</span></span>|  
  
## <a name="sql-server-2008-schema-restrictions"></a><span data-ttu-id="8610c-332">SQL Server 2008-Schemabeschränkungen</span><span class="sxs-lookup"><span data-stu-id="8610c-332">SQL Server 2008 Schema Restrictions</span></span>  
 <span data-ttu-id="8610c-333">In den folgenden Tabellen sind die Beschränkungen für SQL Server 2008-Schemaauflistungen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="8610c-333">The following tables list the restrictions for SQL Server 2008 schema collections.</span></span> <span data-ttu-id="8610c-334">Diese Beschränkungen gelten ab Version 3.5 SP1 von .NET Framework und SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="8610c-334">These restrictions are valid beginning with version 3.5 SP1 of the .NET Framework and SQL Server 2008.</span></span> <span data-ttu-id="8610c-335">Sie werden in früheren Versionen von .NET Framework und SQL Server nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8610c-335">They are not supported in earlier versions of the .NET Framework and SQL Server.</span></span>  
  
### <a name="columnsetcolumns"></a><span data-ttu-id="8610c-336">ColumnSetColumns</span><span class="sxs-lookup"><span data-stu-id="8610c-336">ColumnSetColumns</span></span>  
  
|<span data-ttu-id="8610c-337">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="8610c-337">Restriction Name</span></span>|<span data-ttu-id="8610c-338">Parametername</span><span class="sxs-lookup"><span data-stu-id="8610c-338">Parameter Name</span></span>|<span data-ttu-id="8610c-339">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="8610c-339">Restriction Default</span></span>|<span data-ttu-id="8610c-340">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="8610c-340">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="8610c-341">Katalog</span><span class="sxs-lookup"><span data-stu-id="8610c-341">Catalog</span></span>|@Catalog|<span data-ttu-id="8610c-342">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8610c-342">TABLE_CATALOG</span></span>|<span data-ttu-id="8610c-343">1</span><span class="sxs-lookup"><span data-stu-id="8610c-343">1</span></span>|  
|<span data-ttu-id="8610c-344">Besitzer</span><span class="sxs-lookup"><span data-stu-id="8610c-344">Owner</span></span>|@Owner|<span data-ttu-id="8610c-345">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8610c-345">TABLE_SCHEMA</span></span>|<span data-ttu-id="8610c-346">2</span><span class="sxs-lookup"><span data-stu-id="8610c-346">2</span></span>|  
|<span data-ttu-id="8610c-347">Tabelle</span><span class="sxs-lookup"><span data-stu-id="8610c-347">Table</span></span>|@Table|<span data-ttu-id="8610c-348">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8610c-348">TABLE_NAME</span></span>|<span data-ttu-id="8610c-349">3</span><span class="sxs-lookup"><span data-stu-id="8610c-349">3</span></span>|  
  
### <a name="allcolumns"></a><span data-ttu-id="8610c-350">AllColumns</span><span class="sxs-lookup"><span data-stu-id="8610c-350">AllColumns</span></span>  
  
|<span data-ttu-id="8610c-351">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="8610c-351">Restriction Name</span></span>|<span data-ttu-id="8610c-352">Parametername</span><span class="sxs-lookup"><span data-stu-id="8610c-352">Parameter Name</span></span>|<span data-ttu-id="8610c-353">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="8610c-353">Restriction Default</span></span>|<span data-ttu-id="8610c-354">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="8610c-354">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="8610c-355">Katalog</span><span class="sxs-lookup"><span data-stu-id="8610c-355">Catalog</span></span>|@Catalog|<span data-ttu-id="8610c-356">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8610c-356">TABLE_CATALOG</span></span>|<span data-ttu-id="8610c-357">1</span><span class="sxs-lookup"><span data-stu-id="8610c-357">1</span></span>|  
|<span data-ttu-id="8610c-358">Besitzer</span><span class="sxs-lookup"><span data-stu-id="8610c-358">Owner</span></span>|@Owner|<span data-ttu-id="8610c-359">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8610c-359">TABLE_SCHEMA</span></span>|<span data-ttu-id="8610c-360">2</span><span class="sxs-lookup"><span data-stu-id="8610c-360">2</span></span>|  
|<span data-ttu-id="8610c-361">Tabelle</span><span class="sxs-lookup"><span data-stu-id="8610c-361">Table</span></span>|@Table|<span data-ttu-id="8610c-362">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8610c-362">TABLE_NAME</span></span>|<span data-ttu-id="8610c-363">3</span><span class="sxs-lookup"><span data-stu-id="8610c-363">3</span></span>|  
|<span data-ttu-id="8610c-364">Spalte</span><span class="sxs-lookup"><span data-stu-id="8610c-364">Column</span></span>|@Column|<span data-ttu-id="8610c-365">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="8610c-365">COLUMN_NAME</span></span>|<span data-ttu-id="8610c-366">4</span><span class="sxs-lookup"><span data-stu-id="8610c-366">4</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8610c-367">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8610c-367">See also</span></span>

- [<span data-ttu-id="8610c-368">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="8610c-368">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
