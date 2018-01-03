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
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 4a3cc1f0c27af1ad41e14374b4c155e6b8620f28
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="schema-restrictions"></a><span data-ttu-id="8a603-102">Schemaeinschränkungen</span><span class="sxs-lookup"><span data-stu-id="8a603-102">Schema Restrictions</span></span>
<span data-ttu-id="8a603-103">Den optionalen zweiten Parameter von der **GetSchema** Methode ist die Einschränkungen, die verwendet werden, um die Begrenzung des Umfangs der Schemainformationen zurückgegeben und erfolgt eine Übergabe an die **GetSchema** -Methode ein Array von Zeichenfolgen .</span><span class="sxs-lookup"><span data-stu-id="8a603-103">The second optional parameter of the **GetSchema** method is the restrictions that are used to limit the amount of schema information returned, and it is passed to the **GetSchema** method as an array of strings.</span></span> <span data-ttu-id="8a603-104">Die Position im Array bestimmt die Werte, die zurückgegeben werden können. Dies entspricht der Anzahl der Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="8a603-104">The position in the array determines the values that you can pass, and this is equivalent to the restriction number.</span></span>  
  
 <span data-ttu-id="8a603-105">In der folgenden Tabelle werden beispielsweise die Einschränkungen beschrieben, die von der Schemaauflistung "Tables" mithilfe des .NET Framework-Datenanbieters für SQL Server unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="8a603-105">For example, the following table describes the restrictions supported by the "Tables" schema collection using the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="8a603-106">Zusätzliche Einschränkungen für SQL Server-Schemaauflistungen werden am Ende dieses Themas aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="8a603-106">Additional restrictions for SQL Server schema collections are listed at the end of this topic.</span></span>  
  
|<span data-ttu-id="8a603-107">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="8a603-107">Restriction Name</span></span>|<span data-ttu-id="8a603-108">Parametername</span><span class="sxs-lookup"><span data-stu-id="8a603-108">Parameter Name</span></span>|<span data-ttu-id="8a603-109">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="8a603-109">Restriction Default</span></span>|<span data-ttu-id="8a603-110">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="8a603-110">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="8a603-111">Catalog</span><span class="sxs-lookup"><span data-stu-id="8a603-111">Catalog</span></span>|@Catalog|<span data-ttu-id="8a603-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8a603-112">TABLE_CATALOG</span></span>|<span data-ttu-id="8a603-113">1</span><span class="sxs-lookup"><span data-stu-id="8a603-113">1</span></span>|  
|<span data-ttu-id="8a603-114">Besitzer</span><span class="sxs-lookup"><span data-stu-id="8a603-114">Owner</span></span>|@Owner|<span data-ttu-id="8a603-115">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8a603-115">TABLE_SCHEMA</span></span>|<span data-ttu-id="8a603-116">2</span><span class="sxs-lookup"><span data-stu-id="8a603-116">2</span></span>|  
|<span data-ttu-id="8a603-117">Tabelle</span><span class="sxs-lookup"><span data-stu-id="8a603-117">Table</span></span>|@Name|<span data-ttu-id="8a603-118">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8a603-118">TABLE_NAME</span></span>|<span data-ttu-id="8a603-119">3</span><span class="sxs-lookup"><span data-stu-id="8a603-119">3</span></span>|  
|<span data-ttu-id="8a603-120">TableType</span><span class="sxs-lookup"><span data-stu-id="8a603-120">TableType</span></span>|@TableType|<span data-ttu-id="8a603-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="8a603-121">TABLE_TYPE</span></span>|<span data-ttu-id="8a603-122">4</span><span class="sxs-lookup"><span data-stu-id="8a603-122">4</span></span>|  
  
## <a name="specifying-restriction-values"></a><span data-ttu-id="8a603-123">Angeben der Einschränkungswerte</span><span class="sxs-lookup"><span data-stu-id="8a603-123">Specifying Restriction Values</span></span>  
 <span data-ttu-id="8a603-124">Wenn Sie eine der Einschränkungen der Tables-Schemaauflistung verwenden möchten, erstellen Sie ein Zeichenfolgenarray mit vier Elementen und fügen einen Wert in das Element ein, das mit der Einschränkungsnummer übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="8a603-124">To use one of the restrictions of the "Tables" schema collection, simply create an array of strings with four elements, then place a value in the element that matches the restriction number.</span></span> <span data-ttu-id="8a603-125">Z. B. zum Einschränken der Tabellen zurückgegeben, durch die **GetSchema** Methode, um nur die Tabellen im Schema "Sales" legen Sie das zweite Element des Arrays "Sales" vor der Übergabe an die **GetSchema** Methode.</span><span class="sxs-lookup"><span data-stu-id="8a603-125">For example, to restrict the tables returned by the **GetSchema** method to only those tables in the "Sales" schema, set the second element of the array to "Sales" before passing it to the **GetSchema** method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8a603-126">Die Einschränkungsauflistungen für den `SqlClient` und den `OracleClient` verfügen über eine zusätzliche `ParameterName`-Spalte.</span><span class="sxs-lookup"><span data-stu-id="8a603-126">The restrictions collections for `SqlClient` and `OracleClient` have an additional `ParameterName` column.</span></span> <span data-ttu-id="8a603-127">Die Spalte für den Einschränkungsstandard ist zwar aus Gründen der Abwärtskompatibilität vorhanden, wird aber derzeit ignoriert.</span><span class="sxs-lookup"><span data-stu-id="8a603-127">The restriction default column is still there for backwards compatibility, but is currently ignored.</span></span> <span data-ttu-id="8a603-128">Verwenden Sie Abfragen mit Parametern statt Zeichenfolgenersetzungen, um das Risiko eines SQL-Injection-Angriffs beim Angeben der Einschränkungswerte zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="8a603-128">Parameterized queries rather than string replacement should be used to minimize the risk of an SQL injection attack when specifying restriction values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8a603-129">Die Anzahl der Elementen im Array muss kleiner oder gleich der Anzahl der Einschränkungen sein, die für die angegebene Schemaauflistung unterstützt werden, da sonst eine <xref:System.ArgumentException> ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="8a603-129">The number of elements in the array must be less than or equal to the number of restrictions supported for the specified schema collection else an <xref:System.ArgumentException> will be thrown.</span></span> <span data-ttu-id="8a603-130">Es können weniger Elemente als die maximale Anzahl der Einschränkungen vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="8a603-130">There can be fewer than the maximum number of restrictions.</span></span> <span data-ttu-id="8a603-131">Es wird davon ausgegangen, dass die fehlenden Einschränkungen NULL (uneingeschränkt) sind.</span><span class="sxs-lookup"><span data-stu-id="8a603-131">The missing restrictions are assumed to be null (unrestricted).</span></span>  
  
 <span data-ttu-id="8a603-132">Sie können einen verwalteten .NET Framework-Anbieter, um die Liste der unterstützten Einschränkungen durch Aufrufen von Abfragen die **GetSchema** Methode mit dem Namen der schemaauflistung der Einschränkungen, die "Restrictions" lautet.</span><span class="sxs-lookup"><span data-stu-id="8a603-132">You can query a .NET Framework managed provider to determine the list of supported restrictions by calling the **GetSchema** method with the name of the restrictions schema collection, which is "Restrictions".</span></span> <span data-ttu-id="8a603-133">Dabei wird eine <xref:System.Data.DataTable> mit einer Liste der Auflistungsnamen, Einschränkungsnamen, Standardeinschränkungswerte und der Anzahl der Einschränkungen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8a603-133">This will return a <xref:System.Data.DataTable> with a list of the collection names, the restriction names, the default restriction values, and the restriction numbers.</span></span>  
  
### <a name="example"></a><span data-ttu-id="8a603-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8a603-134">Example</span></span>  
 <span data-ttu-id="8a603-135">Die folgenden Beispiele veranschaulichen, wie Sie die <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> Methode von der .NET Framework-Datenanbieter für SQL Server <xref:System.Data.SqlClient.SqlConnection> -Klasse zum Abrufen von Schemainformationen zu allen enthaltenen Tabellen die **AdventureWorks**Beispieldatenbank und zum Einschränken der Informationen, die an die Tabellen im "Sales"-Schema zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="8a603-135">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database, and to restrict the information returned to only those tables in the "Sales" schema:</span></span>  
  
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
  
## <a name="sql-server-schema-restrictions"></a><span data-ttu-id="8a603-136">SQL Server-Schemabeschränkungen</span><span class="sxs-lookup"><span data-stu-id="8a603-136">SQL Server Schema Restrictions</span></span>  
 <span data-ttu-id="8a603-137">In den folgenden Tabellen sind die Beschränkungen für SQL Server-Schemaauflistungen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="8a603-137">The following tables list the restrictions for SQL Server schema collections.</span></span>  
  
### <a name="users"></a><span data-ttu-id="8a603-138">Benutzer</span><span class="sxs-lookup"><span data-stu-id="8a603-138">Users</span></span>  
  
|<span data-ttu-id="8a603-139">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="8a603-139">Restriction Name</span></span>|<span data-ttu-id="8a603-140">Parametername</span><span class="sxs-lookup"><span data-stu-id="8a603-140">Parameter Name</span></span>|<span data-ttu-id="8a603-141">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="8a603-141">Restriction Default</span></span>|<span data-ttu-id="8a603-142">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="8a603-142">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="8a603-143">User_Name</span><span class="sxs-lookup"><span data-stu-id="8a603-143">User_Name</span></span>|@Name|<span data-ttu-id="8a603-144">Name</span><span class="sxs-lookup"><span data-stu-id="8a603-144">name</span></span>|<span data-ttu-id="8a603-145">1</span><span class="sxs-lookup"><span data-stu-id="8a603-145">1</span></span>|  
  
### <a name="databases"></a><span data-ttu-id="8a603-146">Databases</span><span class="sxs-lookup"><span data-stu-id="8a603-146">Databases</span></span>  
  
|<span data-ttu-id="8a603-147">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="8a603-147">Restriction Name</span></span>|<span data-ttu-id="8a603-148">Parametername</span><span class="sxs-lookup"><span data-stu-id="8a603-148">Parameter Name</span></span>|<span data-ttu-id="8a603-149">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="8a603-149">Restriction Default</span></span>|<span data-ttu-id="8a603-150">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="8a603-150">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="8a603-151">name</span><span class="sxs-lookup"><span data-stu-id="8a603-151">Name</span></span>|@Name|<span data-ttu-id="8a603-152">name</span><span class="sxs-lookup"><span data-stu-id="8a603-152">Name</span></span>|<span data-ttu-id="8a603-153">1</span><span class="sxs-lookup"><span data-stu-id="8a603-153">1</span></span>|  
  
### <a name="tables"></a><span data-ttu-id="8a603-154">Tabellen</span><span class="sxs-lookup"><span data-stu-id="8a603-154">Tables</span></span>  
  
|<span data-ttu-id="8a603-155">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="8a603-155">Restriction Name</span></span>|<span data-ttu-id="8a603-156">Parametername</span><span class="sxs-lookup"><span data-stu-id="8a603-156">Parameter Name</span></span>|<span data-ttu-id="8a603-157">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="8a603-157">Restriction Default</span></span>|<span data-ttu-id="8a603-158">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="8a603-158">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="8a603-159">Catalog</span><span class="sxs-lookup"><span data-stu-id="8a603-159">Catalog</span></span>|@Catalog|<span data-ttu-id="8a603-160">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8a603-160">TABLE_CATALOG</span></span>|<span data-ttu-id="8a603-161">1</span><span class="sxs-lookup"><span data-stu-id="8a603-161">1</span></span>|  
|<span data-ttu-id="8a603-162">Besitzer</span><span class="sxs-lookup"><span data-stu-id="8a603-162">Owner</span></span>|@Owner|<span data-ttu-id="8a603-163">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8a603-163">TABLE_SCHEMA</span></span>|<span data-ttu-id="8a603-164">2</span><span class="sxs-lookup"><span data-stu-id="8a603-164">2</span></span>|  
|<span data-ttu-id="8a603-165">Tabelle</span><span class="sxs-lookup"><span data-stu-id="8a603-165">Table</span></span>|@Name|<span data-ttu-id="8a603-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8a603-166">TABLE_NAME</span></span>|<span data-ttu-id="8a603-167">3</span><span class="sxs-lookup"><span data-stu-id="8a603-167">3</span></span>|  
|<span data-ttu-id="8a603-168">TableType</span><span class="sxs-lookup"><span data-stu-id="8a603-168">TableType</span></span>|@TableType|<span data-ttu-id="8a603-169">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="8a603-169">TABLE_TYPE</span></span>|<span data-ttu-id="8a603-170">4</span><span class="sxs-lookup"><span data-stu-id="8a603-170">4</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="8a603-171">Columns</span><span class="sxs-lookup"><span data-stu-id="8a603-171">Columns</span></span>  
  
|<span data-ttu-id="8a603-172">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="8a603-172">Restriction Name</span></span>|<span data-ttu-id="8a603-173">Parametername</span><span class="sxs-lookup"><span data-stu-id="8a603-173">Parameter Name</span></span>|<span data-ttu-id="8a603-174">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="8a603-174">Restriction Default</span></span>|<span data-ttu-id="8a603-175">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="8a603-175">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="8a603-176">Catalog</span><span class="sxs-lookup"><span data-stu-id="8a603-176">Catalog</span></span>|@Catalog|<span data-ttu-id="8a603-177">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8a603-177">TABLE_CATALOG</span></span>|<span data-ttu-id="8a603-178">1</span><span class="sxs-lookup"><span data-stu-id="8a603-178">1</span></span>|  
|<span data-ttu-id="8a603-179">Besitzer</span><span class="sxs-lookup"><span data-stu-id="8a603-179">Owner</span></span>|@Owner|<span data-ttu-id="8a603-180">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8a603-180">TABLE_SCHEMA</span></span>|<span data-ttu-id="8a603-181">2</span><span class="sxs-lookup"><span data-stu-id="8a603-181">2</span></span>|  
|<span data-ttu-id="8a603-182">Tabelle</span><span class="sxs-lookup"><span data-stu-id="8a603-182">Table</span></span>|@Table|<span data-ttu-id="8a603-183">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8a603-183">TABLE_NAME</span></span>|<span data-ttu-id="8a603-184">3</span><span class="sxs-lookup"><span data-stu-id="8a603-184">3</span></span>|  
|<span data-ttu-id="8a603-185">Spalte</span><span class="sxs-lookup"><span data-stu-id="8a603-185">Column</span></span>|@Column|<span data-ttu-id="8a603-186">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="8a603-186">COLUMN_NAME</span></span>|<span data-ttu-id="8a603-187">4</span><span class="sxs-lookup"><span data-stu-id="8a603-187">4</span></span>|  
  
### <a name="structuredtypemembers"></a><span data-ttu-id="8a603-188">StructuredTypeMembers</span><span class="sxs-lookup"><span data-stu-id="8a603-188">StructuredTypeMembers</span></span>  
  
|<span data-ttu-id="8a603-189">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="8a603-189">Restriction Name</span></span>|<span data-ttu-id="8a603-190">Parametername</span><span class="sxs-lookup"><span data-stu-id="8a603-190">Parameter Name</span></span>|<span data-ttu-id="8a603-191">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="8a603-191">Restriction Default</span></span>|<span data-ttu-id="8a603-192">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="8a603-192">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="8a603-193">Catalog</span><span class="sxs-lookup"><span data-stu-id="8a603-193">Catalog</span></span>|@Catalog|<span data-ttu-id="8a603-194">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8a603-194">TABLE_CATALOG</span></span>|<span data-ttu-id="8a603-195">1</span><span class="sxs-lookup"><span data-stu-id="8a603-195">1</span></span>|  
|<span data-ttu-id="8a603-196">Besitzer</span><span class="sxs-lookup"><span data-stu-id="8a603-196">Owner</span></span>|@Owner|<span data-ttu-id="8a603-197">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8a603-197">TABLE_SCHEMA</span></span>|<span data-ttu-id="8a603-198">2</span><span class="sxs-lookup"><span data-stu-id="8a603-198">2</span></span>|  
|<span data-ttu-id="8a603-199">Tabelle</span><span class="sxs-lookup"><span data-stu-id="8a603-199">Table</span></span>|@Table|<span data-ttu-id="8a603-200">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8a603-200">TABLE_NAME</span></span>|<span data-ttu-id="8a603-201">3</span><span class="sxs-lookup"><span data-stu-id="8a603-201">3</span></span>|  
|<span data-ttu-id="8a603-202">Spalte</span><span class="sxs-lookup"><span data-stu-id="8a603-202">Column</span></span>|@Column|<span data-ttu-id="8a603-203">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="8a603-203">COLUMN_NAME</span></span>|<span data-ttu-id="8a603-204">4</span><span class="sxs-lookup"><span data-stu-id="8a603-204">4</span></span>|  
  
### <a name="views"></a><span data-ttu-id="8a603-205">Ansichten</span><span class="sxs-lookup"><span data-stu-id="8a603-205">Views</span></span>  
  
|<span data-ttu-id="8a603-206">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="8a603-206">Restriction Name</span></span>|<span data-ttu-id="8a603-207">Parametername</span><span class="sxs-lookup"><span data-stu-id="8a603-207">Parameter Name</span></span>|<span data-ttu-id="8a603-208">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="8a603-208">Restriction Default</span></span>|<span data-ttu-id="8a603-209">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="8a603-209">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="8a603-210">Catalog</span><span class="sxs-lookup"><span data-stu-id="8a603-210">Catalog</span></span>|@Catalog|<span data-ttu-id="8a603-211">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8a603-211">TABLE_CATALOG</span></span>|<span data-ttu-id="8a603-212">1</span><span class="sxs-lookup"><span data-stu-id="8a603-212">1</span></span>|  
|<span data-ttu-id="8a603-213">Besitzer</span><span class="sxs-lookup"><span data-stu-id="8a603-213">Owner</span></span>|@Owner|<span data-ttu-id="8a603-214">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8a603-214">TABLE_SCHEMA</span></span>|<span data-ttu-id="8a603-215">2</span><span class="sxs-lookup"><span data-stu-id="8a603-215">2</span></span>|  
|<span data-ttu-id="8a603-216">Tabelle</span><span class="sxs-lookup"><span data-stu-id="8a603-216">Table</span></span>|@Table|<span data-ttu-id="8a603-217">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8a603-217">TABLE_NAME</span></span>|<span data-ttu-id="8a603-218">3</span><span class="sxs-lookup"><span data-stu-id="8a603-218">3</span></span>|  
  
### <a name="viewcolumns"></a><span data-ttu-id="8a603-219">ViewColumns</span><span class="sxs-lookup"><span data-stu-id="8a603-219">ViewColumns</span></span>  
  
|<span data-ttu-id="8a603-220">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="8a603-220">Restriction Name</span></span>|<span data-ttu-id="8a603-221">Parametername</span><span class="sxs-lookup"><span data-stu-id="8a603-221">Parameter Name</span></span>|<span data-ttu-id="8a603-222">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="8a603-222">Restriction Default</span></span>|<span data-ttu-id="8a603-223">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="8a603-223">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="8a603-224">Catalog</span><span class="sxs-lookup"><span data-stu-id="8a603-224">Catalog</span></span>|@Catalog|<span data-ttu-id="8a603-225">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8a603-225">VIEW_CATALOG</span></span>|<span data-ttu-id="8a603-226">1</span><span class="sxs-lookup"><span data-stu-id="8a603-226">1</span></span>|  
|<span data-ttu-id="8a603-227">Besitzer</span><span class="sxs-lookup"><span data-stu-id="8a603-227">Owner</span></span>|@Owner|<span data-ttu-id="8a603-228">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8a603-228">VIEW_SCHEMA</span></span>|<span data-ttu-id="8a603-229">2</span><span class="sxs-lookup"><span data-stu-id="8a603-229">2</span></span>|  
|<span data-ttu-id="8a603-230">Tabelle</span><span class="sxs-lookup"><span data-stu-id="8a603-230">Table</span></span>|@Table|<span data-ttu-id="8a603-231">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="8a603-231">VIEW_NAME</span></span>|<span data-ttu-id="8a603-232">3</span><span class="sxs-lookup"><span data-stu-id="8a603-232">3</span></span>|  
|<span data-ttu-id="8a603-233">Spalte</span><span class="sxs-lookup"><span data-stu-id="8a603-233">Column</span></span>|@Column|<span data-ttu-id="8a603-234">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="8a603-234">COLUMN_NAME</span></span>|<span data-ttu-id="8a603-235">4</span><span class="sxs-lookup"><span data-stu-id="8a603-235">4</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="8a603-236">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="8a603-236">ProcedureParameters</span></span>  
  
|<span data-ttu-id="8a603-237">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="8a603-237">Restriction Name</span></span>|<span data-ttu-id="8a603-238">Parametername</span><span class="sxs-lookup"><span data-stu-id="8a603-238">Parameter Name</span></span>|<span data-ttu-id="8a603-239">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="8a603-239">Restriction Default</span></span>|<span data-ttu-id="8a603-240">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="8a603-240">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="8a603-241">Catalog</span><span class="sxs-lookup"><span data-stu-id="8a603-241">Catalog</span></span>|@Catalog|<span data-ttu-id="8a603-242">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8a603-242">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="8a603-243">1</span><span class="sxs-lookup"><span data-stu-id="8a603-243">1</span></span>|  
|<span data-ttu-id="8a603-244">Besitzer</span><span class="sxs-lookup"><span data-stu-id="8a603-244">Owner</span></span>|@Owner|<span data-ttu-id="8a603-245">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8a603-245">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="8a603-246">2</span><span class="sxs-lookup"><span data-stu-id="8a603-246">2</span></span>|  
|<span data-ttu-id="8a603-247">name</span><span class="sxs-lookup"><span data-stu-id="8a603-247">Name</span></span>|@Name|<span data-ttu-id="8a603-248">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="8a603-248">SPECIFIC_NAME</span></span>|<span data-ttu-id="8a603-249">3</span><span class="sxs-lookup"><span data-stu-id="8a603-249">3</span></span>|  
|<span data-ttu-id="8a603-250">Parameter</span><span class="sxs-lookup"><span data-stu-id="8a603-250">Parameter</span></span>|@Parameter|<span data-ttu-id="8a603-251">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="8a603-251">PARAMETER_NAME</span></span>|<span data-ttu-id="8a603-252">4</span><span class="sxs-lookup"><span data-stu-id="8a603-252">4</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="8a603-253">Verfahren</span><span class="sxs-lookup"><span data-stu-id="8a603-253">Procedures</span></span>  
  
|<span data-ttu-id="8a603-254">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="8a603-254">Restriction Name</span></span>|<span data-ttu-id="8a603-255">Parametername</span><span class="sxs-lookup"><span data-stu-id="8a603-255">Parameter Name</span></span>|<span data-ttu-id="8a603-256">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="8a603-256">Restriction Default</span></span>|<span data-ttu-id="8a603-257">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="8a603-257">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="8a603-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="8a603-258">Catalog</span></span>|@Catalog|<span data-ttu-id="8a603-259">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8a603-259">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="8a603-260">1</span><span class="sxs-lookup"><span data-stu-id="8a603-260">1</span></span>|  
|<span data-ttu-id="8a603-261">Besitzer</span><span class="sxs-lookup"><span data-stu-id="8a603-261">Owner</span></span>|@Owner|<span data-ttu-id="8a603-262">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8a603-262">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="8a603-263">2</span><span class="sxs-lookup"><span data-stu-id="8a603-263">2</span></span>|  
|<span data-ttu-id="8a603-264">name</span><span class="sxs-lookup"><span data-stu-id="8a603-264">Name</span></span>|@Name|<span data-ttu-id="8a603-265">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="8a603-265">SPECIFIC_NAME</span></span>|<span data-ttu-id="8a603-266">3</span><span class="sxs-lookup"><span data-stu-id="8a603-266">3</span></span>|  
|<span data-ttu-id="8a603-267">Typ</span><span class="sxs-lookup"><span data-stu-id="8a603-267">Type</span></span>|@Type|<span data-ttu-id="8a603-268">ROUTINE_TYPE</span><span class="sxs-lookup"><span data-stu-id="8a603-268">ROUTINE_TYPE</span></span>|<span data-ttu-id="8a603-269">4</span><span class="sxs-lookup"><span data-stu-id="8a603-269">4</span></span>|  
  
### <a name="indexcolumns"></a><span data-ttu-id="8a603-270">IndexColumns</span><span class="sxs-lookup"><span data-stu-id="8a603-270">IndexColumns</span></span>  
  
|<span data-ttu-id="8a603-271">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="8a603-271">Restriction Name</span></span>|<span data-ttu-id="8a603-272">Parametername</span><span class="sxs-lookup"><span data-stu-id="8a603-272">Parameter Name</span></span>|<span data-ttu-id="8a603-273">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="8a603-273">Restriction Default</span></span>|<span data-ttu-id="8a603-274">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="8a603-274">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="8a603-275">Catalog</span><span class="sxs-lookup"><span data-stu-id="8a603-275">Catalog</span></span>|@Catalog|<span data-ttu-id="8a603-276">db_name()</span><span class="sxs-lookup"><span data-stu-id="8a603-276">db_name()</span></span>|<span data-ttu-id="8a603-277">1</span><span class="sxs-lookup"><span data-stu-id="8a603-277">1</span></span>|  
|<span data-ttu-id="8a603-278">Besitzer</span><span class="sxs-lookup"><span data-stu-id="8a603-278">Owner</span></span>|@Owner|<span data-ttu-id="8a603-279">user_name()</span><span class="sxs-lookup"><span data-stu-id="8a603-279">user_name()</span></span>|<span data-ttu-id="8a603-280">2</span><span class="sxs-lookup"><span data-stu-id="8a603-280">2</span></span>|  
|<span data-ttu-id="8a603-281">Tabelle</span><span class="sxs-lookup"><span data-stu-id="8a603-281">Table</span></span>|@Table|<span data-ttu-id="8a603-282">o.name</span><span class="sxs-lookup"><span data-stu-id="8a603-282">o.name</span></span>|<span data-ttu-id="8a603-283">3</span><span class="sxs-lookup"><span data-stu-id="8a603-283">3</span></span>|  
|<span data-ttu-id="8a603-284">ConstraintName</span><span class="sxs-lookup"><span data-stu-id="8a603-284">ConstraintName</span></span>|@ConstraintName|<span data-ttu-id="8a603-285">x.name</span><span class="sxs-lookup"><span data-stu-id="8a603-285">x.name</span></span>|<span data-ttu-id="8a603-286">4</span><span class="sxs-lookup"><span data-stu-id="8a603-286">4</span></span>|  
|<span data-ttu-id="8a603-287">Spalte</span><span class="sxs-lookup"><span data-stu-id="8a603-287">Column</span></span>|@Column|<span data-ttu-id="8a603-288">c.name</span><span class="sxs-lookup"><span data-stu-id="8a603-288">c.name</span></span>|<span data-ttu-id="8a603-289">5</span><span class="sxs-lookup"><span data-stu-id="8a603-289">5</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="8a603-290">Indexes</span><span class="sxs-lookup"><span data-stu-id="8a603-290">Indexes</span></span>  
  
|<span data-ttu-id="8a603-291">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="8a603-291">Restriction Name</span></span>|<span data-ttu-id="8a603-292">Parametername</span><span class="sxs-lookup"><span data-stu-id="8a603-292">Parameter Name</span></span>|<span data-ttu-id="8a603-293">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="8a603-293">Restriction Default</span></span>|<span data-ttu-id="8a603-294">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="8a603-294">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="8a603-295">Catalog</span><span class="sxs-lookup"><span data-stu-id="8a603-295">Catalog</span></span>|@Catalog|<span data-ttu-id="8a603-296">db_name()</span><span class="sxs-lookup"><span data-stu-id="8a603-296">db_name()</span></span>|<span data-ttu-id="8a603-297">1</span><span class="sxs-lookup"><span data-stu-id="8a603-297">1</span></span>|  
|<span data-ttu-id="8a603-298">Besitzer</span><span class="sxs-lookup"><span data-stu-id="8a603-298">Owner</span></span>|@Owner|<span data-ttu-id="8a603-299">user_name()</span><span class="sxs-lookup"><span data-stu-id="8a603-299">user_name()</span></span>|<span data-ttu-id="8a603-300">2</span><span class="sxs-lookup"><span data-stu-id="8a603-300">2</span></span>|  
|<span data-ttu-id="8a603-301">Tabelle</span><span class="sxs-lookup"><span data-stu-id="8a603-301">Table</span></span>|@Table|<span data-ttu-id="8a603-302">o.name</span><span class="sxs-lookup"><span data-stu-id="8a603-302">o.name</span></span>|<span data-ttu-id="8a603-303">3</span><span class="sxs-lookup"><span data-stu-id="8a603-303">3</span></span>|  
  
### <a name="userdefinedtypes"></a><span data-ttu-id="8a603-304">UserDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="8a603-304">UserDefinedTypes</span></span>  
  
|<span data-ttu-id="8a603-305">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="8a603-305">Restriction Name</span></span>|<span data-ttu-id="8a603-306">Parametername</span><span class="sxs-lookup"><span data-stu-id="8a603-306">Parameter Name</span></span>|<span data-ttu-id="8a603-307">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="8a603-307">Restriction Default</span></span>|<span data-ttu-id="8a603-308">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="8a603-308">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="8a603-309">assembly_name</span><span class="sxs-lookup"><span data-stu-id="8a603-309">assembly_name</span></span>|@AssemblyName|<span data-ttu-id="8a603-310">assemblies.name</span><span class="sxs-lookup"><span data-stu-id="8a603-310">assemblies.name</span></span>|<span data-ttu-id="8a603-311">1</span><span class="sxs-lookup"><span data-stu-id="8a603-311">1</span></span>|  
|<span data-ttu-id="8a603-312">udt_name</span><span class="sxs-lookup"><span data-stu-id="8a603-312">udt_name</span></span>|@UDTName|<span data-ttu-id="8a603-313">types.assembly_class</span><span class="sxs-lookup"><span data-stu-id="8a603-313">types.assembly_class</span></span>|<span data-ttu-id="8a603-314">2</span><span class="sxs-lookup"><span data-stu-id="8a603-314">2</span></span>|  
  
### <a name="foreignkeys"></a><span data-ttu-id="8a603-315">ForeignKeys</span><span class="sxs-lookup"><span data-stu-id="8a603-315">ForeignKeys</span></span>  
  
|<span data-ttu-id="8a603-316">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="8a603-316">Restriction Name</span></span>|<span data-ttu-id="8a603-317">Parametername</span><span class="sxs-lookup"><span data-stu-id="8a603-317">Parameter Name</span></span>|<span data-ttu-id="8a603-318">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="8a603-318">Restriction Default</span></span>|<span data-ttu-id="8a603-319">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="8a603-319">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="8a603-320">Catalog</span><span class="sxs-lookup"><span data-stu-id="8a603-320">Catalog</span></span>|@Catalog|<span data-ttu-id="8a603-321">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8a603-321">CONSTRAINT_CATALOG</span></span>|<span data-ttu-id="8a603-322">1</span><span class="sxs-lookup"><span data-stu-id="8a603-322">1</span></span>|  
|<span data-ttu-id="8a603-323">Besitzer</span><span class="sxs-lookup"><span data-stu-id="8a603-323">Owner</span></span>|@Owner|<span data-ttu-id="8a603-324">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8a603-324">CONSTRAINT_SCHEMA</span></span>|<span data-ttu-id="8a603-325">2</span><span class="sxs-lookup"><span data-stu-id="8a603-325">2</span></span>|  
|<span data-ttu-id="8a603-326">Tabelle</span><span class="sxs-lookup"><span data-stu-id="8a603-326">Table</span></span>|@Table|<span data-ttu-id="8a603-327">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8a603-327">TABLE_NAME</span></span>|<span data-ttu-id="8a603-328">3</span><span class="sxs-lookup"><span data-stu-id="8a603-328">3</span></span>|  
|<span data-ttu-id="8a603-329">name</span><span class="sxs-lookup"><span data-stu-id="8a603-329">Name</span></span>|@Name|<span data-ttu-id="8a603-330">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="8a603-330">CONSTRAINT_NAME</span></span>|<span data-ttu-id="8a603-331">4</span><span class="sxs-lookup"><span data-stu-id="8a603-331">4</span></span>|  
  
## <a name="sql-server-2008-schema-restrictions"></a><span data-ttu-id="8a603-332">SQL Server 2008-Schemabeschränkungen</span><span class="sxs-lookup"><span data-stu-id="8a603-332">SQL Server 2008 Schema Restrictions</span></span>  
 <span data-ttu-id="8a603-333">In den folgenden Tabellen sind die Beschränkungen für SQL Server 2008-Schemaauflistungen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="8a603-333">The following tables list the restrictions for SQL Server 2008 schema collections.</span></span> <span data-ttu-id="8a603-334">Diese Beschränkungen gelten ab Version 3.5 SP1 von .NET Framework und SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="8a603-334">These restrictions are valid beginning with version 3.5 SP1 of the .NET Framework and SQL Server 2008.</span></span> <span data-ttu-id="8a603-335">Sie werden in früheren Versionen von .NET Framework und SQL Server nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8a603-335">They are not supported in earlier versions of the .NET Framework and SQL Server.</span></span>  
  
### <a name="columnsetcolumns"></a><span data-ttu-id="8a603-336">ColumnSetColumns</span><span class="sxs-lookup"><span data-stu-id="8a603-336">ColumnSetColumns</span></span>  
  
|<span data-ttu-id="8a603-337">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="8a603-337">Restriction Name</span></span>|<span data-ttu-id="8a603-338">Parametername</span><span class="sxs-lookup"><span data-stu-id="8a603-338">Parameter Name</span></span>|<span data-ttu-id="8a603-339">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="8a603-339">Restriction Default</span></span>|<span data-ttu-id="8a603-340">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="8a603-340">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="8a603-341">Catalog</span><span class="sxs-lookup"><span data-stu-id="8a603-341">Catalog</span></span>|@Catalog|<span data-ttu-id="8a603-342">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8a603-342">TABLE_CATALOG</span></span>|<span data-ttu-id="8a603-343">1</span><span class="sxs-lookup"><span data-stu-id="8a603-343">1</span></span>|  
|<span data-ttu-id="8a603-344">Besitzer</span><span class="sxs-lookup"><span data-stu-id="8a603-344">Owner</span></span>|@Owner|<span data-ttu-id="8a603-345">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8a603-345">TABLE_SCHEMA</span></span>|<span data-ttu-id="8a603-346">2</span><span class="sxs-lookup"><span data-stu-id="8a603-346">2</span></span>|  
|<span data-ttu-id="8a603-347">Tabelle</span><span class="sxs-lookup"><span data-stu-id="8a603-347">Table</span></span>|@Table|<span data-ttu-id="8a603-348">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8a603-348">TABLE_NAME</span></span>|<span data-ttu-id="8a603-349">3</span><span class="sxs-lookup"><span data-stu-id="8a603-349">3</span></span>|  
  
### <a name="allcolumns"></a><span data-ttu-id="8a603-350">AllColumns</span><span class="sxs-lookup"><span data-stu-id="8a603-350">AllColumns</span></span>  
  
|<span data-ttu-id="8a603-351">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="8a603-351">Restriction Name</span></span>|<span data-ttu-id="8a603-352">Parametername</span><span class="sxs-lookup"><span data-stu-id="8a603-352">Parameter Name</span></span>|<span data-ttu-id="8a603-353">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="8a603-353">Restriction Default</span></span>|<span data-ttu-id="8a603-354">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="8a603-354">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="8a603-355">Catalog</span><span class="sxs-lookup"><span data-stu-id="8a603-355">Catalog</span></span>|@Catalog|<span data-ttu-id="8a603-356">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8a603-356">TABLE_CATALOG</span></span>|<span data-ttu-id="8a603-357">1</span><span class="sxs-lookup"><span data-stu-id="8a603-357">1</span></span>|  
|<span data-ttu-id="8a603-358">Besitzer</span><span class="sxs-lookup"><span data-stu-id="8a603-358">Owner</span></span>|@Owner|<span data-ttu-id="8a603-359">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8a603-359">TABLE_SCHEMA</span></span>|<span data-ttu-id="8a603-360">2</span><span class="sxs-lookup"><span data-stu-id="8a603-360">2</span></span>|  
|<span data-ttu-id="8a603-361">Tabelle</span><span class="sxs-lookup"><span data-stu-id="8a603-361">Table</span></span>|@Table|<span data-ttu-id="8a603-362">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8a603-362">TABLE_NAME</span></span>|<span data-ttu-id="8a603-363">3</span><span class="sxs-lookup"><span data-stu-id="8a603-363">3</span></span>|  
|<span data-ttu-id="8a603-364">Spalte</span><span class="sxs-lookup"><span data-stu-id="8a603-364">Column</span></span>|@Column|<span data-ttu-id="8a603-365">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="8a603-365">COLUMN_NAME</span></span>|<span data-ttu-id="8a603-366">4</span><span class="sxs-lookup"><span data-stu-id="8a603-366">4</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8a603-367">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8a603-367">See Also</span></span>  
 [<span data-ttu-id="8a603-368">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="8a603-368">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
