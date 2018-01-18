---
title: "Schemaeinschränkungen"
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
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: f5b004b70716c61af8ac37fef76f660c488e5a74
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="schema-restrictions"></a><span data-ttu-id="51956-102">Schemaeinschränkungen</span><span class="sxs-lookup"><span data-stu-id="51956-102">Schema Restrictions</span></span>
<span data-ttu-id="51956-103">Den optionalen zweiten Parameter von der **GetSchema** Methode ist die Einschränkungen, die verwendet werden, um die Begrenzung des Umfangs der Schemainformationen zurückgegeben und erfolgt eine Übergabe an die **GetSchema** -Methode ein Array von Zeichenfolgen .</span><span class="sxs-lookup"><span data-stu-id="51956-103">The second optional parameter of the **GetSchema** method is the restrictions that are used to limit the amount of schema information returned, and it is passed to the **GetSchema** method as an array of strings.</span></span> <span data-ttu-id="51956-104">Die Position im Array bestimmt die Werte, die zurückgegeben werden können. Dies entspricht der Anzahl der Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="51956-104">The position in the array determines the values that you can pass, and this is equivalent to the restriction number.</span></span>  
  
 <span data-ttu-id="51956-105">In der folgenden Tabelle werden beispielsweise die Einschränkungen beschrieben, die von der Schemaauflistung "Tables" mithilfe des .NET Framework-Datenanbieters für SQL Server unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="51956-105">For example, the following table describes the restrictions supported by the "Tables" schema collection using the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="51956-106">Zusätzliche Einschränkungen für SQL Server-Schemaauflistungen werden am Ende dieses Themas aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="51956-106">Additional restrictions for SQL Server schema collections are listed at the end of this topic.</span></span>  
  
|<span data-ttu-id="51956-107">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="51956-107">Restriction Name</span></span>|<span data-ttu-id="51956-108">Parametername</span><span class="sxs-lookup"><span data-stu-id="51956-108">Parameter Name</span></span>|<span data-ttu-id="51956-109">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="51956-109">Restriction Default</span></span>|<span data-ttu-id="51956-110">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="51956-110">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="51956-111">Catalog</span><span class="sxs-lookup"><span data-stu-id="51956-111">Catalog</span></span>|@Catalog|<span data-ttu-id="51956-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="51956-112">TABLE_CATALOG</span></span>|<span data-ttu-id="51956-113">1</span><span class="sxs-lookup"><span data-stu-id="51956-113">1</span></span>|  
|<span data-ttu-id="51956-114">Besitzer</span><span class="sxs-lookup"><span data-stu-id="51956-114">Owner</span></span>|@Owner|<span data-ttu-id="51956-115">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="51956-115">TABLE_SCHEMA</span></span>|<span data-ttu-id="51956-116">2</span><span class="sxs-lookup"><span data-stu-id="51956-116">2</span></span>|  
|<span data-ttu-id="51956-117">Tabelle</span><span class="sxs-lookup"><span data-stu-id="51956-117">Table</span></span>|@Name|<span data-ttu-id="51956-118">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="51956-118">TABLE_NAME</span></span>|<span data-ttu-id="51956-119">3</span><span class="sxs-lookup"><span data-stu-id="51956-119">3</span></span>|  
|<span data-ttu-id="51956-120">TableType</span><span class="sxs-lookup"><span data-stu-id="51956-120">TableType</span></span>|@TableType|<span data-ttu-id="51956-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="51956-121">TABLE_TYPE</span></span>|<span data-ttu-id="51956-122">4</span><span class="sxs-lookup"><span data-stu-id="51956-122">4</span></span>|  
  
## <a name="specifying-restriction-values"></a><span data-ttu-id="51956-123">Angeben der Einschränkungswerte</span><span class="sxs-lookup"><span data-stu-id="51956-123">Specifying Restriction Values</span></span>  
 <span data-ttu-id="51956-124">Wenn Sie eine der Einschränkungen der Tables-Schemaauflistung verwenden möchten, erstellen Sie ein Zeichenfolgenarray mit vier Elementen und fügen einen Wert in das Element ein, das mit der Einschränkungsnummer übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="51956-124">To use one of the restrictions of the "Tables" schema collection, simply create an array of strings with four elements, then place a value in the element that matches the restriction number.</span></span> <span data-ttu-id="51956-125">Z. B. zum Einschränken der Tabellen zurückgegeben, durch die **GetSchema** Methode, um nur die Tabellen im Schema "Sales" legen Sie das zweite Element des Arrays "Sales" vor der Übergabe an die **GetSchema** Methode.</span><span class="sxs-lookup"><span data-stu-id="51956-125">For example, to restrict the tables returned by the **GetSchema** method to only those tables in the "Sales" schema, set the second element of the array to "Sales" before passing it to the **GetSchema** method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="51956-126">Die Einschränkungsauflistungen für den `SqlClient` und den `OracleClient` verfügen über eine zusätzliche `ParameterName`-Spalte.</span><span class="sxs-lookup"><span data-stu-id="51956-126">The restrictions collections for `SqlClient` and `OracleClient` have an additional `ParameterName` column.</span></span> <span data-ttu-id="51956-127">Die Spalte für den Einschränkungsstandard ist zwar aus Gründen der Abwärtskompatibilität vorhanden, wird aber derzeit ignoriert.</span><span class="sxs-lookup"><span data-stu-id="51956-127">The restriction default column is still there for backwards compatibility, but is currently ignored.</span></span> <span data-ttu-id="51956-128">Verwenden Sie Abfragen mit Parametern statt Zeichenfolgenersetzungen, um das Risiko eines SQL-Injection-Angriffs beim Angeben der Einschränkungswerte zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="51956-128">Parameterized queries rather than string replacement should be used to minimize the risk of an SQL injection attack when specifying restriction values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="51956-129">Die Anzahl der Elementen im Array muss kleiner oder gleich der Anzahl der Einschränkungen sein, die für die angegebene Schemaauflistung unterstützt werden, da sonst eine <xref:System.ArgumentException> ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="51956-129">The number of elements in the array must be less than or equal to the number of restrictions supported for the specified schema collection else an <xref:System.ArgumentException> will be thrown.</span></span> <span data-ttu-id="51956-130">Es können weniger Elemente als die maximale Anzahl der Einschränkungen vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="51956-130">There can be fewer than the maximum number of restrictions.</span></span> <span data-ttu-id="51956-131">Es wird davon ausgegangen, dass die fehlenden Einschränkungen NULL (uneingeschränkt) sind.</span><span class="sxs-lookup"><span data-stu-id="51956-131">The missing restrictions are assumed to be null (unrestricted).</span></span>  
  
 <span data-ttu-id="51956-132">Sie können einen verwalteten .NET Framework-Anbieter, um die Liste der unterstützten Einschränkungen durch Aufrufen von Abfragen die **GetSchema** Methode mit dem Namen der schemaauflistung der Einschränkungen, die "Restrictions" lautet.</span><span class="sxs-lookup"><span data-stu-id="51956-132">You can query a .NET Framework managed provider to determine the list of supported restrictions by calling the **GetSchema** method with the name of the restrictions schema collection, which is "Restrictions".</span></span> <span data-ttu-id="51956-133">Dabei wird eine <xref:System.Data.DataTable> mit einer Liste der Auflistungsnamen, Einschränkungsnamen, Standardeinschränkungswerte und der Anzahl der Einschränkungen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="51956-133">This will return a <xref:System.Data.DataTable> with a list of the collection names, the restriction names, the default restriction values, and the restriction numbers.</span></span>  
  
### <a name="example"></a><span data-ttu-id="51956-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="51956-134">Example</span></span>  
 <span data-ttu-id="51956-135">Die folgenden Beispiele veranschaulichen, wie Sie die <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> Methode von der .NET Framework-Datenanbieter für SQL Server <xref:System.Data.SqlClient.SqlConnection> -Klasse zum Abrufen von Schemainformationen zu allen enthaltenen Tabellen die **AdventureWorks**Beispieldatenbank und zum Einschränken der Informationen, die an die Tabellen im "Sales"-Schema zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="51956-135">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database, and to restrict the information returned to only those tables in the "Sales" schema:</span></span>  
  
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
  
## <a name="sql-server-schema-restrictions"></a><span data-ttu-id="51956-136">SQL Server-Schemabeschränkungen</span><span class="sxs-lookup"><span data-stu-id="51956-136">SQL Server Schema Restrictions</span></span>  
 <span data-ttu-id="51956-137">In den folgenden Tabellen sind die Beschränkungen für SQL Server-Schemaauflistungen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="51956-137">The following tables list the restrictions for SQL Server schema collections.</span></span>  
  
### <a name="users"></a><span data-ttu-id="51956-138">Benutzer</span><span class="sxs-lookup"><span data-stu-id="51956-138">Users</span></span>  
  
|<span data-ttu-id="51956-139">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="51956-139">Restriction Name</span></span>|<span data-ttu-id="51956-140">Parametername</span><span class="sxs-lookup"><span data-stu-id="51956-140">Parameter Name</span></span>|<span data-ttu-id="51956-141">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="51956-141">Restriction Default</span></span>|<span data-ttu-id="51956-142">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="51956-142">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="51956-143">User_Name</span><span class="sxs-lookup"><span data-stu-id="51956-143">User_Name</span></span>|@Name|<span data-ttu-id="51956-144">Name</span><span class="sxs-lookup"><span data-stu-id="51956-144">name</span></span>|<span data-ttu-id="51956-145">1</span><span class="sxs-lookup"><span data-stu-id="51956-145">1</span></span>|  
  
### <a name="databases"></a><span data-ttu-id="51956-146">Databases</span><span class="sxs-lookup"><span data-stu-id="51956-146">Databases</span></span>  
  
|<span data-ttu-id="51956-147">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="51956-147">Restriction Name</span></span>|<span data-ttu-id="51956-148">Parametername</span><span class="sxs-lookup"><span data-stu-id="51956-148">Parameter Name</span></span>|<span data-ttu-id="51956-149">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="51956-149">Restriction Default</span></span>|<span data-ttu-id="51956-150">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="51956-150">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="51956-151">name</span><span class="sxs-lookup"><span data-stu-id="51956-151">Name</span></span>|@Name|<span data-ttu-id="51956-152">name</span><span class="sxs-lookup"><span data-stu-id="51956-152">Name</span></span>|<span data-ttu-id="51956-153">1</span><span class="sxs-lookup"><span data-stu-id="51956-153">1</span></span>|  
  
### <a name="tables"></a><span data-ttu-id="51956-154">Tabellen</span><span class="sxs-lookup"><span data-stu-id="51956-154">Tables</span></span>  
  
|<span data-ttu-id="51956-155">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="51956-155">Restriction Name</span></span>|<span data-ttu-id="51956-156">Parametername</span><span class="sxs-lookup"><span data-stu-id="51956-156">Parameter Name</span></span>|<span data-ttu-id="51956-157">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="51956-157">Restriction Default</span></span>|<span data-ttu-id="51956-158">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="51956-158">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="51956-159">Catalog</span><span class="sxs-lookup"><span data-stu-id="51956-159">Catalog</span></span>|@Catalog|<span data-ttu-id="51956-160">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="51956-160">TABLE_CATALOG</span></span>|<span data-ttu-id="51956-161">1</span><span class="sxs-lookup"><span data-stu-id="51956-161">1</span></span>|  
|<span data-ttu-id="51956-162">Besitzer</span><span class="sxs-lookup"><span data-stu-id="51956-162">Owner</span></span>|@Owner|<span data-ttu-id="51956-163">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="51956-163">TABLE_SCHEMA</span></span>|<span data-ttu-id="51956-164">2</span><span class="sxs-lookup"><span data-stu-id="51956-164">2</span></span>|  
|<span data-ttu-id="51956-165">Tabelle</span><span class="sxs-lookup"><span data-stu-id="51956-165">Table</span></span>|@Name|<span data-ttu-id="51956-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="51956-166">TABLE_NAME</span></span>|<span data-ttu-id="51956-167">3</span><span class="sxs-lookup"><span data-stu-id="51956-167">3</span></span>|  
|<span data-ttu-id="51956-168">TableType</span><span class="sxs-lookup"><span data-stu-id="51956-168">TableType</span></span>|@TableType|<span data-ttu-id="51956-169">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="51956-169">TABLE_TYPE</span></span>|<span data-ttu-id="51956-170">4</span><span class="sxs-lookup"><span data-stu-id="51956-170">4</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="51956-171">Columns</span><span class="sxs-lookup"><span data-stu-id="51956-171">Columns</span></span>  
  
|<span data-ttu-id="51956-172">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="51956-172">Restriction Name</span></span>|<span data-ttu-id="51956-173">Parametername</span><span class="sxs-lookup"><span data-stu-id="51956-173">Parameter Name</span></span>|<span data-ttu-id="51956-174">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="51956-174">Restriction Default</span></span>|<span data-ttu-id="51956-175">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="51956-175">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="51956-176">Catalog</span><span class="sxs-lookup"><span data-stu-id="51956-176">Catalog</span></span>|@Catalog|<span data-ttu-id="51956-177">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="51956-177">TABLE_CATALOG</span></span>|<span data-ttu-id="51956-178">1</span><span class="sxs-lookup"><span data-stu-id="51956-178">1</span></span>|  
|<span data-ttu-id="51956-179">Besitzer</span><span class="sxs-lookup"><span data-stu-id="51956-179">Owner</span></span>|@Owner|<span data-ttu-id="51956-180">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="51956-180">TABLE_SCHEMA</span></span>|<span data-ttu-id="51956-181">2</span><span class="sxs-lookup"><span data-stu-id="51956-181">2</span></span>|  
|<span data-ttu-id="51956-182">Tabelle</span><span class="sxs-lookup"><span data-stu-id="51956-182">Table</span></span>|@Table|<span data-ttu-id="51956-183">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="51956-183">TABLE_NAME</span></span>|<span data-ttu-id="51956-184">3</span><span class="sxs-lookup"><span data-stu-id="51956-184">3</span></span>|  
|<span data-ttu-id="51956-185">Spalte</span><span class="sxs-lookup"><span data-stu-id="51956-185">Column</span></span>|@Column|<span data-ttu-id="51956-186">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="51956-186">COLUMN_NAME</span></span>|<span data-ttu-id="51956-187">4</span><span class="sxs-lookup"><span data-stu-id="51956-187">4</span></span>|  
  
### <a name="structuredtypemembers"></a><span data-ttu-id="51956-188">StructuredTypeMembers</span><span class="sxs-lookup"><span data-stu-id="51956-188">StructuredTypeMembers</span></span>  
  
|<span data-ttu-id="51956-189">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="51956-189">Restriction Name</span></span>|<span data-ttu-id="51956-190">Parametername</span><span class="sxs-lookup"><span data-stu-id="51956-190">Parameter Name</span></span>|<span data-ttu-id="51956-191">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="51956-191">Restriction Default</span></span>|<span data-ttu-id="51956-192">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="51956-192">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="51956-193">Catalog</span><span class="sxs-lookup"><span data-stu-id="51956-193">Catalog</span></span>|@Catalog|<span data-ttu-id="51956-194">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="51956-194">TABLE_CATALOG</span></span>|<span data-ttu-id="51956-195">1</span><span class="sxs-lookup"><span data-stu-id="51956-195">1</span></span>|  
|<span data-ttu-id="51956-196">Besitzer</span><span class="sxs-lookup"><span data-stu-id="51956-196">Owner</span></span>|@Owner|<span data-ttu-id="51956-197">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="51956-197">TABLE_SCHEMA</span></span>|<span data-ttu-id="51956-198">2</span><span class="sxs-lookup"><span data-stu-id="51956-198">2</span></span>|  
|<span data-ttu-id="51956-199">Tabelle</span><span class="sxs-lookup"><span data-stu-id="51956-199">Table</span></span>|@Table|<span data-ttu-id="51956-200">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="51956-200">TABLE_NAME</span></span>|<span data-ttu-id="51956-201">3</span><span class="sxs-lookup"><span data-stu-id="51956-201">3</span></span>|  
|<span data-ttu-id="51956-202">Spalte</span><span class="sxs-lookup"><span data-stu-id="51956-202">Column</span></span>|@Column|<span data-ttu-id="51956-203">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="51956-203">COLUMN_NAME</span></span>|<span data-ttu-id="51956-204">4</span><span class="sxs-lookup"><span data-stu-id="51956-204">4</span></span>|  
  
### <a name="views"></a><span data-ttu-id="51956-205">Ansichten</span><span class="sxs-lookup"><span data-stu-id="51956-205">Views</span></span>  
  
|<span data-ttu-id="51956-206">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="51956-206">Restriction Name</span></span>|<span data-ttu-id="51956-207">Parametername</span><span class="sxs-lookup"><span data-stu-id="51956-207">Parameter Name</span></span>|<span data-ttu-id="51956-208">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="51956-208">Restriction Default</span></span>|<span data-ttu-id="51956-209">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="51956-209">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="51956-210">Catalog</span><span class="sxs-lookup"><span data-stu-id="51956-210">Catalog</span></span>|@Catalog|<span data-ttu-id="51956-211">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="51956-211">TABLE_CATALOG</span></span>|<span data-ttu-id="51956-212">1</span><span class="sxs-lookup"><span data-stu-id="51956-212">1</span></span>|  
|<span data-ttu-id="51956-213">Besitzer</span><span class="sxs-lookup"><span data-stu-id="51956-213">Owner</span></span>|@Owner|<span data-ttu-id="51956-214">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="51956-214">TABLE_SCHEMA</span></span>|<span data-ttu-id="51956-215">2</span><span class="sxs-lookup"><span data-stu-id="51956-215">2</span></span>|  
|<span data-ttu-id="51956-216">Tabelle</span><span class="sxs-lookup"><span data-stu-id="51956-216">Table</span></span>|@Table|<span data-ttu-id="51956-217">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="51956-217">TABLE_NAME</span></span>|<span data-ttu-id="51956-218">3</span><span class="sxs-lookup"><span data-stu-id="51956-218">3</span></span>|  
  
### <a name="viewcolumns"></a><span data-ttu-id="51956-219">ViewColumns</span><span class="sxs-lookup"><span data-stu-id="51956-219">ViewColumns</span></span>  
  
|<span data-ttu-id="51956-220">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="51956-220">Restriction Name</span></span>|<span data-ttu-id="51956-221">Parametername</span><span class="sxs-lookup"><span data-stu-id="51956-221">Parameter Name</span></span>|<span data-ttu-id="51956-222">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="51956-222">Restriction Default</span></span>|<span data-ttu-id="51956-223">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="51956-223">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="51956-224">Catalog</span><span class="sxs-lookup"><span data-stu-id="51956-224">Catalog</span></span>|@Catalog|<span data-ttu-id="51956-225">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="51956-225">VIEW_CATALOG</span></span>|<span data-ttu-id="51956-226">1</span><span class="sxs-lookup"><span data-stu-id="51956-226">1</span></span>|  
|<span data-ttu-id="51956-227">Besitzer</span><span class="sxs-lookup"><span data-stu-id="51956-227">Owner</span></span>|@Owner|<span data-ttu-id="51956-228">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="51956-228">VIEW_SCHEMA</span></span>|<span data-ttu-id="51956-229">2</span><span class="sxs-lookup"><span data-stu-id="51956-229">2</span></span>|  
|<span data-ttu-id="51956-230">Tabelle</span><span class="sxs-lookup"><span data-stu-id="51956-230">Table</span></span>|@Table|<span data-ttu-id="51956-231">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="51956-231">VIEW_NAME</span></span>|<span data-ttu-id="51956-232">3</span><span class="sxs-lookup"><span data-stu-id="51956-232">3</span></span>|  
|<span data-ttu-id="51956-233">Spalte</span><span class="sxs-lookup"><span data-stu-id="51956-233">Column</span></span>|@Column|<span data-ttu-id="51956-234">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="51956-234">COLUMN_NAME</span></span>|<span data-ttu-id="51956-235">4</span><span class="sxs-lookup"><span data-stu-id="51956-235">4</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="51956-236">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="51956-236">ProcedureParameters</span></span>  
  
|<span data-ttu-id="51956-237">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="51956-237">Restriction Name</span></span>|<span data-ttu-id="51956-238">Parametername</span><span class="sxs-lookup"><span data-stu-id="51956-238">Parameter Name</span></span>|<span data-ttu-id="51956-239">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="51956-239">Restriction Default</span></span>|<span data-ttu-id="51956-240">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="51956-240">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="51956-241">Catalog</span><span class="sxs-lookup"><span data-stu-id="51956-241">Catalog</span></span>|@Catalog|<span data-ttu-id="51956-242">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="51956-242">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="51956-243">1</span><span class="sxs-lookup"><span data-stu-id="51956-243">1</span></span>|  
|<span data-ttu-id="51956-244">Besitzer</span><span class="sxs-lookup"><span data-stu-id="51956-244">Owner</span></span>|@Owner|<span data-ttu-id="51956-245">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="51956-245">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="51956-246">2</span><span class="sxs-lookup"><span data-stu-id="51956-246">2</span></span>|  
|<span data-ttu-id="51956-247">name</span><span class="sxs-lookup"><span data-stu-id="51956-247">Name</span></span>|@Name|<span data-ttu-id="51956-248">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="51956-248">SPECIFIC_NAME</span></span>|<span data-ttu-id="51956-249">3</span><span class="sxs-lookup"><span data-stu-id="51956-249">3</span></span>|  
|<span data-ttu-id="51956-250">Parameter</span><span class="sxs-lookup"><span data-stu-id="51956-250">Parameter</span></span>|@Parameter|<span data-ttu-id="51956-251">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="51956-251">PARAMETER_NAME</span></span>|<span data-ttu-id="51956-252">4</span><span class="sxs-lookup"><span data-stu-id="51956-252">4</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="51956-253">Verfahren</span><span class="sxs-lookup"><span data-stu-id="51956-253">Procedures</span></span>  
  
|<span data-ttu-id="51956-254">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="51956-254">Restriction Name</span></span>|<span data-ttu-id="51956-255">Parametername</span><span class="sxs-lookup"><span data-stu-id="51956-255">Parameter Name</span></span>|<span data-ttu-id="51956-256">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="51956-256">Restriction Default</span></span>|<span data-ttu-id="51956-257">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="51956-257">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="51956-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="51956-258">Catalog</span></span>|@Catalog|<span data-ttu-id="51956-259">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="51956-259">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="51956-260">1</span><span class="sxs-lookup"><span data-stu-id="51956-260">1</span></span>|  
|<span data-ttu-id="51956-261">Besitzer</span><span class="sxs-lookup"><span data-stu-id="51956-261">Owner</span></span>|@Owner|<span data-ttu-id="51956-262">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="51956-262">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="51956-263">2</span><span class="sxs-lookup"><span data-stu-id="51956-263">2</span></span>|  
|<span data-ttu-id="51956-264">name</span><span class="sxs-lookup"><span data-stu-id="51956-264">Name</span></span>|@Name|<span data-ttu-id="51956-265">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="51956-265">SPECIFIC_NAME</span></span>|<span data-ttu-id="51956-266">3</span><span class="sxs-lookup"><span data-stu-id="51956-266">3</span></span>|  
|<span data-ttu-id="51956-267">Typ</span><span class="sxs-lookup"><span data-stu-id="51956-267">Type</span></span>|@Type|<span data-ttu-id="51956-268">ROUTINE_TYPE</span><span class="sxs-lookup"><span data-stu-id="51956-268">ROUTINE_TYPE</span></span>|<span data-ttu-id="51956-269">4</span><span class="sxs-lookup"><span data-stu-id="51956-269">4</span></span>|  
  
### <a name="indexcolumns"></a><span data-ttu-id="51956-270">IndexColumns</span><span class="sxs-lookup"><span data-stu-id="51956-270">IndexColumns</span></span>  
  
|<span data-ttu-id="51956-271">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="51956-271">Restriction Name</span></span>|<span data-ttu-id="51956-272">Parametername</span><span class="sxs-lookup"><span data-stu-id="51956-272">Parameter Name</span></span>|<span data-ttu-id="51956-273">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="51956-273">Restriction Default</span></span>|<span data-ttu-id="51956-274">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="51956-274">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="51956-275">Catalog</span><span class="sxs-lookup"><span data-stu-id="51956-275">Catalog</span></span>|@Catalog|<span data-ttu-id="51956-276">db_name()</span><span class="sxs-lookup"><span data-stu-id="51956-276">db_name()</span></span>|<span data-ttu-id="51956-277">1</span><span class="sxs-lookup"><span data-stu-id="51956-277">1</span></span>|  
|<span data-ttu-id="51956-278">Besitzer</span><span class="sxs-lookup"><span data-stu-id="51956-278">Owner</span></span>|@Owner|<span data-ttu-id="51956-279">user_name()</span><span class="sxs-lookup"><span data-stu-id="51956-279">user_name()</span></span>|<span data-ttu-id="51956-280">2</span><span class="sxs-lookup"><span data-stu-id="51956-280">2</span></span>|  
|<span data-ttu-id="51956-281">Tabelle</span><span class="sxs-lookup"><span data-stu-id="51956-281">Table</span></span>|@Table|<span data-ttu-id="51956-282">o.name</span><span class="sxs-lookup"><span data-stu-id="51956-282">o.name</span></span>|<span data-ttu-id="51956-283">3</span><span class="sxs-lookup"><span data-stu-id="51956-283">3</span></span>|  
|<span data-ttu-id="51956-284">ConstraintName</span><span class="sxs-lookup"><span data-stu-id="51956-284">ConstraintName</span></span>|@ConstraintName|<span data-ttu-id="51956-285">x.name</span><span class="sxs-lookup"><span data-stu-id="51956-285">x.name</span></span>|<span data-ttu-id="51956-286">4</span><span class="sxs-lookup"><span data-stu-id="51956-286">4</span></span>|  
|<span data-ttu-id="51956-287">Spalte</span><span class="sxs-lookup"><span data-stu-id="51956-287">Column</span></span>|@Column|<span data-ttu-id="51956-288">c.name</span><span class="sxs-lookup"><span data-stu-id="51956-288">c.name</span></span>|<span data-ttu-id="51956-289">5</span><span class="sxs-lookup"><span data-stu-id="51956-289">5</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="51956-290">Indexes</span><span class="sxs-lookup"><span data-stu-id="51956-290">Indexes</span></span>  
  
|<span data-ttu-id="51956-291">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="51956-291">Restriction Name</span></span>|<span data-ttu-id="51956-292">Parametername</span><span class="sxs-lookup"><span data-stu-id="51956-292">Parameter Name</span></span>|<span data-ttu-id="51956-293">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="51956-293">Restriction Default</span></span>|<span data-ttu-id="51956-294">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="51956-294">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="51956-295">Catalog</span><span class="sxs-lookup"><span data-stu-id="51956-295">Catalog</span></span>|@Catalog|<span data-ttu-id="51956-296">db_name()</span><span class="sxs-lookup"><span data-stu-id="51956-296">db_name()</span></span>|<span data-ttu-id="51956-297">1</span><span class="sxs-lookup"><span data-stu-id="51956-297">1</span></span>|  
|<span data-ttu-id="51956-298">Besitzer</span><span class="sxs-lookup"><span data-stu-id="51956-298">Owner</span></span>|@Owner|<span data-ttu-id="51956-299">user_name()</span><span class="sxs-lookup"><span data-stu-id="51956-299">user_name()</span></span>|<span data-ttu-id="51956-300">2</span><span class="sxs-lookup"><span data-stu-id="51956-300">2</span></span>|  
|<span data-ttu-id="51956-301">Tabelle</span><span class="sxs-lookup"><span data-stu-id="51956-301">Table</span></span>|@Table|<span data-ttu-id="51956-302">o.name</span><span class="sxs-lookup"><span data-stu-id="51956-302">o.name</span></span>|<span data-ttu-id="51956-303">3</span><span class="sxs-lookup"><span data-stu-id="51956-303">3</span></span>|  
  
### <a name="userdefinedtypes"></a><span data-ttu-id="51956-304">UserDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="51956-304">UserDefinedTypes</span></span>  
  
|<span data-ttu-id="51956-305">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="51956-305">Restriction Name</span></span>|<span data-ttu-id="51956-306">Parametername</span><span class="sxs-lookup"><span data-stu-id="51956-306">Parameter Name</span></span>|<span data-ttu-id="51956-307">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="51956-307">Restriction Default</span></span>|<span data-ttu-id="51956-308">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="51956-308">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="51956-309">assembly_name</span><span class="sxs-lookup"><span data-stu-id="51956-309">assembly_name</span></span>|@AssemblyName|<span data-ttu-id="51956-310">assemblies.name</span><span class="sxs-lookup"><span data-stu-id="51956-310">assemblies.name</span></span>|<span data-ttu-id="51956-311">1</span><span class="sxs-lookup"><span data-stu-id="51956-311">1</span></span>|  
|<span data-ttu-id="51956-312">udt_name</span><span class="sxs-lookup"><span data-stu-id="51956-312">udt_name</span></span>|@UDTName|<span data-ttu-id="51956-313">types.assembly_class</span><span class="sxs-lookup"><span data-stu-id="51956-313">types.assembly_class</span></span>|<span data-ttu-id="51956-314">2</span><span class="sxs-lookup"><span data-stu-id="51956-314">2</span></span>|  
  
### <a name="foreignkeys"></a><span data-ttu-id="51956-315">ForeignKeys</span><span class="sxs-lookup"><span data-stu-id="51956-315">ForeignKeys</span></span>  
  
|<span data-ttu-id="51956-316">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="51956-316">Restriction Name</span></span>|<span data-ttu-id="51956-317">Parametername</span><span class="sxs-lookup"><span data-stu-id="51956-317">Parameter Name</span></span>|<span data-ttu-id="51956-318">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="51956-318">Restriction Default</span></span>|<span data-ttu-id="51956-319">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="51956-319">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="51956-320">Catalog</span><span class="sxs-lookup"><span data-stu-id="51956-320">Catalog</span></span>|@Catalog|<span data-ttu-id="51956-321">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="51956-321">CONSTRAINT_CATALOG</span></span>|<span data-ttu-id="51956-322">1</span><span class="sxs-lookup"><span data-stu-id="51956-322">1</span></span>|  
|<span data-ttu-id="51956-323">Besitzer</span><span class="sxs-lookup"><span data-stu-id="51956-323">Owner</span></span>|@Owner|<span data-ttu-id="51956-324">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="51956-324">CONSTRAINT_SCHEMA</span></span>|<span data-ttu-id="51956-325">2</span><span class="sxs-lookup"><span data-stu-id="51956-325">2</span></span>|  
|<span data-ttu-id="51956-326">Tabelle</span><span class="sxs-lookup"><span data-stu-id="51956-326">Table</span></span>|@Table|<span data-ttu-id="51956-327">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="51956-327">TABLE_NAME</span></span>|<span data-ttu-id="51956-328">3</span><span class="sxs-lookup"><span data-stu-id="51956-328">3</span></span>|  
|<span data-ttu-id="51956-329">name</span><span class="sxs-lookup"><span data-stu-id="51956-329">Name</span></span>|@Name|<span data-ttu-id="51956-330">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="51956-330">CONSTRAINT_NAME</span></span>|<span data-ttu-id="51956-331">4</span><span class="sxs-lookup"><span data-stu-id="51956-331">4</span></span>|  
  
## <a name="sql-server-2008-schema-restrictions"></a><span data-ttu-id="51956-332">SQL Server 2008-Schemabeschränkungen</span><span class="sxs-lookup"><span data-stu-id="51956-332">SQL Server 2008 Schema Restrictions</span></span>  
 <span data-ttu-id="51956-333">In den folgenden Tabellen sind die Beschränkungen für SQL Server 2008-Schemaauflistungen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="51956-333">The following tables list the restrictions for SQL Server 2008 schema collections.</span></span> <span data-ttu-id="51956-334">Diese Beschränkungen gelten ab Version 3.5 SP1 von .NET Framework und SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="51956-334">These restrictions are valid beginning with version 3.5 SP1 of the .NET Framework and SQL Server 2008.</span></span> <span data-ttu-id="51956-335">Sie werden in früheren Versionen von .NET Framework und SQL Server nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="51956-335">They are not supported in earlier versions of the .NET Framework and SQL Server.</span></span>  
  
### <a name="columnsetcolumns"></a><span data-ttu-id="51956-336">ColumnSetColumns</span><span class="sxs-lookup"><span data-stu-id="51956-336">ColumnSetColumns</span></span>  
  
|<span data-ttu-id="51956-337">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="51956-337">Restriction Name</span></span>|<span data-ttu-id="51956-338">Parametername</span><span class="sxs-lookup"><span data-stu-id="51956-338">Parameter Name</span></span>|<span data-ttu-id="51956-339">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="51956-339">Restriction Default</span></span>|<span data-ttu-id="51956-340">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="51956-340">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="51956-341">Catalog</span><span class="sxs-lookup"><span data-stu-id="51956-341">Catalog</span></span>|@Catalog|<span data-ttu-id="51956-342">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="51956-342">TABLE_CATALOG</span></span>|<span data-ttu-id="51956-343">1</span><span class="sxs-lookup"><span data-stu-id="51956-343">1</span></span>|  
|<span data-ttu-id="51956-344">Besitzer</span><span class="sxs-lookup"><span data-stu-id="51956-344">Owner</span></span>|@Owner|<span data-ttu-id="51956-345">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="51956-345">TABLE_SCHEMA</span></span>|<span data-ttu-id="51956-346">2</span><span class="sxs-lookup"><span data-stu-id="51956-346">2</span></span>|  
|<span data-ttu-id="51956-347">Tabelle</span><span class="sxs-lookup"><span data-stu-id="51956-347">Table</span></span>|@Table|<span data-ttu-id="51956-348">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="51956-348">TABLE_NAME</span></span>|<span data-ttu-id="51956-349">3</span><span class="sxs-lookup"><span data-stu-id="51956-349">3</span></span>|  
  
### <a name="allcolumns"></a><span data-ttu-id="51956-350">AllColumns</span><span class="sxs-lookup"><span data-stu-id="51956-350">AllColumns</span></span>  
  
|<span data-ttu-id="51956-351">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="51956-351">Restriction Name</span></span>|<span data-ttu-id="51956-352">Parametername</span><span class="sxs-lookup"><span data-stu-id="51956-352">Parameter Name</span></span>|<span data-ttu-id="51956-353">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="51956-353">Restriction Default</span></span>|<span data-ttu-id="51956-354">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="51956-354">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="51956-355">Catalog</span><span class="sxs-lookup"><span data-stu-id="51956-355">Catalog</span></span>|@Catalog|<span data-ttu-id="51956-356">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="51956-356">TABLE_CATALOG</span></span>|<span data-ttu-id="51956-357">1</span><span class="sxs-lookup"><span data-stu-id="51956-357">1</span></span>|  
|<span data-ttu-id="51956-358">Besitzer</span><span class="sxs-lookup"><span data-stu-id="51956-358">Owner</span></span>|@Owner|<span data-ttu-id="51956-359">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="51956-359">TABLE_SCHEMA</span></span>|<span data-ttu-id="51956-360">2</span><span class="sxs-lookup"><span data-stu-id="51956-360">2</span></span>|  
|<span data-ttu-id="51956-361">Tabelle</span><span class="sxs-lookup"><span data-stu-id="51956-361">Table</span></span>|@Table|<span data-ttu-id="51956-362">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="51956-362">TABLE_NAME</span></span>|<span data-ttu-id="51956-363">3</span><span class="sxs-lookup"><span data-stu-id="51956-363">3</span></span>|  
|<span data-ttu-id="51956-364">Spalte</span><span class="sxs-lookup"><span data-stu-id="51956-364">Column</span></span>|@Column|<span data-ttu-id="51956-365">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="51956-365">COLUMN_NAME</span></span>|<span data-ttu-id="51956-366">4</span><span class="sxs-lookup"><span data-stu-id="51956-366">4</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="51956-367">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51956-367">See Also</span></span>  
 [<span data-ttu-id="51956-368">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="51956-368">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
