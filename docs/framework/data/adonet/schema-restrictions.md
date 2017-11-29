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
ms.openlocfilehash: c254865800694af8eb754c3e8d4072688fd7e89a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="schema-restrictions"></a><span data-ttu-id="1e53e-102">Schemaeinschränkungen</span><span class="sxs-lookup"><span data-stu-id="1e53e-102">Schema Restrictions</span></span>
<span data-ttu-id="1e53e-103">Den optionalen zweiten Parameter von der **GetSchema** Methode ist die Einschränkungen, die verwendet werden, um die Begrenzung des Umfangs der Schemainformationen zurückgegeben und erfolgt eine Übergabe an die **GetSchema** -Methode ein Array von Zeichenfolgen .</span><span class="sxs-lookup"><span data-stu-id="1e53e-103">The second optional parameter of the **GetSchema** method is the restrictions that are used to limit the amount of schema information returned, and it is passed to the **GetSchema** method as an array of strings.</span></span> <span data-ttu-id="1e53e-104">Die Position im Array bestimmt die Werte, die zurückgegeben werden können. Dies entspricht der Anzahl der Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="1e53e-104">The position in the array determines the values that you can pass, and this is equivalent to the restriction number.</span></span>  
  
 <span data-ttu-id="1e53e-105">In der folgenden Tabelle werden beispielsweise die Einschränkungen beschrieben, die von der Schemaauflistung "Tables" mithilfe des .NET Framework-Datenanbieters für SQL Server unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="1e53e-105">For example, the following table describes the restrictions supported by the "Tables" schema collection using the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="1e53e-106">Zusätzliche Einschränkungen für SQL Server-Schemaauflistungen werden am Ende dieses Themas aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="1e53e-106">Additional restrictions for SQL Server schema collections are listed at the end of this topic.</span></span>  
  
|<span data-ttu-id="1e53e-107">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="1e53e-107">Restriction Name</span></span>|<span data-ttu-id="1e53e-108">Parametername</span><span class="sxs-lookup"><span data-stu-id="1e53e-108">Parameter Name</span></span>|<span data-ttu-id="1e53e-109">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="1e53e-109">Restriction Default</span></span>|<span data-ttu-id="1e53e-110">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="1e53e-110">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="1e53e-111">Catalog</span><span class="sxs-lookup"><span data-stu-id="1e53e-111">Catalog</span></span>|@Catalog|<span data-ttu-id="1e53e-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1e53e-112">TABLE_CATALOG</span></span>|<span data-ttu-id="1e53e-113">1</span><span class="sxs-lookup"><span data-stu-id="1e53e-113">1</span></span>|  
|<span data-ttu-id="1e53e-114">Besitzer</span><span class="sxs-lookup"><span data-stu-id="1e53e-114">Owner</span></span>|@Owner|<span data-ttu-id="1e53e-115">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1e53e-115">TABLE_SCHEMA</span></span>|<span data-ttu-id="1e53e-116">2</span><span class="sxs-lookup"><span data-stu-id="1e53e-116">2</span></span>|  
|<span data-ttu-id="1e53e-117">Tabelle</span><span class="sxs-lookup"><span data-stu-id="1e53e-117">Table</span></span>|@Name|<span data-ttu-id="1e53e-118">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1e53e-118">TABLE_NAME</span></span>|<span data-ttu-id="1e53e-119">3</span><span class="sxs-lookup"><span data-stu-id="1e53e-119">3</span></span>|  
|<span data-ttu-id="1e53e-120">TableType</span><span class="sxs-lookup"><span data-stu-id="1e53e-120">TableType</span></span>|@TableType|<span data-ttu-id="1e53e-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="1e53e-121">TABLE_TYPE</span></span>|<span data-ttu-id="1e53e-122">4</span><span class="sxs-lookup"><span data-stu-id="1e53e-122">4</span></span>|  
  
## <a name="specifying-restriction-values"></a><span data-ttu-id="1e53e-123">Angeben der Einschränkungswerte</span><span class="sxs-lookup"><span data-stu-id="1e53e-123">Specifying Restriction Values</span></span>  
 <span data-ttu-id="1e53e-124">Wenn Sie eine der Einschränkungen der Tables-Schemaauflistung verwenden möchten, erstellen Sie ein Zeichenfolgenarray mit vier Elementen und fügen einen Wert in das Element ein, das mit der Einschränkungsnummer übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="1e53e-124">To use one of the restrictions of the "Tables" schema collection, simply create an array of strings with four elements, then place a value in the element that matches the restriction number.</span></span> <span data-ttu-id="1e53e-125">Z. B. zum Einschränken der Tabellen zurückgegeben, durch die **GetSchema** Methode, um nur die Tabellen im Schema "Sales" legen Sie das zweite Element des Arrays "Sales" vor der Übergabe an die **GetSchema** Methode.</span><span class="sxs-lookup"><span data-stu-id="1e53e-125">For example, to restrict the tables returned by the **GetSchema** method to only those tables in the "Sales" schema, set the second element of the array to "Sales" before passing it to the **GetSchema** method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1e53e-126">Die Einschränkungsauflistungen für den `SqlClient` und den `OracleClient` verfügen über eine zusätzliche `ParameterName`-Spalte.</span><span class="sxs-lookup"><span data-stu-id="1e53e-126">The restrictions collections for `SqlClient` and `OracleClient` have an additional `ParameterName` column.</span></span> <span data-ttu-id="1e53e-127">Die Spalte für den Einschränkungsstandard ist zwar aus Gründen der Abwärtskompatibilität vorhanden, wird aber derzeit ignoriert.</span><span class="sxs-lookup"><span data-stu-id="1e53e-127">The restriction default column is still there for backwards compatibility, but is currently ignored.</span></span> <span data-ttu-id="1e53e-128">Verwenden Sie Abfragen mit Parametern statt Zeichenfolgenersetzungen, um das Risiko eines SQL-Injection-Angriffs beim Angeben der Einschränkungswerte zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="1e53e-128">Parameterized queries rather than string replacement should be used to minimize the risk of an SQL injection attack when specifying restriction values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1e53e-129">Die Anzahl der Elementen im Array muss kleiner oder gleich der Anzahl der Einschränkungen sein, die für die angegebene Schemaauflistung unterstützt werden, da sonst eine <xref:System.ArgumentException> ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="1e53e-129">The number of elements in the array must be less than or equal to the number of restrictions supported for the specified schema collection else an <xref:System.ArgumentException> will be thrown.</span></span> <span data-ttu-id="1e53e-130">Es können weniger Elemente als die maximale Anzahl der Einschränkungen vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="1e53e-130">There can be fewer than the maximum number of restrictions.</span></span> <span data-ttu-id="1e53e-131">Es wird davon ausgegangen, dass die fehlenden Einschränkungen NULL (uneingeschränkt) sind.</span><span class="sxs-lookup"><span data-stu-id="1e53e-131">The missing restrictions are assumed to be null (unrestricted).</span></span>  
  
 <span data-ttu-id="1e53e-132">Sie können einen verwalteten .NET Framework-Anbieter, um die Liste der unterstützten Einschränkungen durch Aufrufen von Abfragen die **GetSchema** Methode mit dem Namen der schemaauflistung der Einschränkungen, die "Restrictions" lautet.</span><span class="sxs-lookup"><span data-stu-id="1e53e-132">You can query a .NET Framework managed provider to determine the list of supported restrictions by calling the **GetSchema** method with the name of the restrictions schema collection, which is "Restrictions".</span></span> <span data-ttu-id="1e53e-133">Dabei wird eine <xref:System.Data.DataTable> mit einer Liste der Auflistungsnamen, Einschränkungsnamen, Standardeinschränkungswerte und der Anzahl der Einschränkungen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1e53e-133">This will return a <xref:System.Data.DataTable> with a list of the collection names, the restriction names, the default restriction values, and the restriction numbers.</span></span>  
  
### <a name="example"></a><span data-ttu-id="1e53e-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1e53e-134">Example</span></span>  
 <span data-ttu-id="1e53e-135">Die folgenden Beispiele veranschaulichen, wie Sie die <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> Methode von der .NET Framework-Datenanbieter für SQL Server <xref:System.Data.SqlClient.SqlConnection> -Klasse zum Abrufen von Schemainformationen zu allen enthaltenen Tabellen die **AdventureWorks**Beispieldatenbank und zum Einschränken der Informationen, die an die Tabellen im "Sales"-Schema zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="1e53e-135">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database, and to restrict the information returned to only those tables in the "Sales" schema:</span></span>  
  
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
  
## <a name="sql-server-schema-restrictions"></a><span data-ttu-id="1e53e-136">SQL Server-Schemabeschränkungen</span><span class="sxs-lookup"><span data-stu-id="1e53e-136">SQL Server Schema Restrictions</span></span>  
 <span data-ttu-id="1e53e-137">In den folgenden Tabellen sind die Beschränkungen für SQL Server-Schemaauflistungen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="1e53e-137">The following tables list the restrictions for SQL Server schema collections.</span></span>  
  
### <a name="users"></a><span data-ttu-id="1e53e-138">Benutzer</span><span class="sxs-lookup"><span data-stu-id="1e53e-138">Users</span></span>  
  
|<span data-ttu-id="1e53e-139">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="1e53e-139">Restriction Name</span></span>|<span data-ttu-id="1e53e-140">Parametername</span><span class="sxs-lookup"><span data-stu-id="1e53e-140">Parameter Name</span></span>|<span data-ttu-id="1e53e-141">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="1e53e-141">Restriction Default</span></span>|<span data-ttu-id="1e53e-142">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="1e53e-142">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="1e53e-143">User_Name</span><span class="sxs-lookup"><span data-stu-id="1e53e-143">User_Name</span></span>|@Name|<span data-ttu-id="1e53e-144">Name</span><span class="sxs-lookup"><span data-stu-id="1e53e-144">name</span></span>|<span data-ttu-id="1e53e-145">1</span><span class="sxs-lookup"><span data-stu-id="1e53e-145">1</span></span>|  
  
### <a name="databases"></a><span data-ttu-id="1e53e-146">Databases</span><span class="sxs-lookup"><span data-stu-id="1e53e-146">Databases</span></span>  
  
|<span data-ttu-id="1e53e-147">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="1e53e-147">Restriction Name</span></span>|<span data-ttu-id="1e53e-148">Parametername</span><span class="sxs-lookup"><span data-stu-id="1e53e-148">Parameter Name</span></span>|<span data-ttu-id="1e53e-149">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="1e53e-149">Restriction Default</span></span>|<span data-ttu-id="1e53e-150">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="1e53e-150">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="1e53e-151">Name</span><span class="sxs-lookup"><span data-stu-id="1e53e-151">Name</span></span>|@Name|<span data-ttu-id="1e53e-152">Name</span><span class="sxs-lookup"><span data-stu-id="1e53e-152">Name</span></span>|<span data-ttu-id="1e53e-153">1</span><span class="sxs-lookup"><span data-stu-id="1e53e-153">1</span></span>|  
  
### <a name="tables"></a><span data-ttu-id="1e53e-154">Tabellen</span><span class="sxs-lookup"><span data-stu-id="1e53e-154">Tables</span></span>  
  
|<span data-ttu-id="1e53e-155">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="1e53e-155">Restriction Name</span></span>|<span data-ttu-id="1e53e-156">Parametername</span><span class="sxs-lookup"><span data-stu-id="1e53e-156">Parameter Name</span></span>|<span data-ttu-id="1e53e-157">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="1e53e-157">Restriction Default</span></span>|<span data-ttu-id="1e53e-158">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="1e53e-158">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="1e53e-159">Catalog</span><span class="sxs-lookup"><span data-stu-id="1e53e-159">Catalog</span></span>|@Catalog|<span data-ttu-id="1e53e-160">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1e53e-160">TABLE_CATALOG</span></span>|<span data-ttu-id="1e53e-161">1</span><span class="sxs-lookup"><span data-stu-id="1e53e-161">1</span></span>|  
|<span data-ttu-id="1e53e-162">Besitzer</span><span class="sxs-lookup"><span data-stu-id="1e53e-162">Owner</span></span>|@Owner|<span data-ttu-id="1e53e-163">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1e53e-163">TABLE_SCHEMA</span></span>|<span data-ttu-id="1e53e-164">2</span><span class="sxs-lookup"><span data-stu-id="1e53e-164">2</span></span>|  
|<span data-ttu-id="1e53e-165">Tabelle</span><span class="sxs-lookup"><span data-stu-id="1e53e-165">Table</span></span>|@Name|<span data-ttu-id="1e53e-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1e53e-166">TABLE_NAME</span></span>|<span data-ttu-id="1e53e-167">3</span><span class="sxs-lookup"><span data-stu-id="1e53e-167">3</span></span>|  
|<span data-ttu-id="1e53e-168">TableType</span><span class="sxs-lookup"><span data-stu-id="1e53e-168">TableType</span></span>|@TableType|<span data-ttu-id="1e53e-169">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="1e53e-169">TABLE_TYPE</span></span>|<span data-ttu-id="1e53e-170">4</span><span class="sxs-lookup"><span data-stu-id="1e53e-170">4</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="1e53e-171">Columns</span><span class="sxs-lookup"><span data-stu-id="1e53e-171">Columns</span></span>  
  
|<span data-ttu-id="1e53e-172">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="1e53e-172">Restriction Name</span></span>|<span data-ttu-id="1e53e-173">Parametername</span><span class="sxs-lookup"><span data-stu-id="1e53e-173">Parameter Name</span></span>|<span data-ttu-id="1e53e-174">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="1e53e-174">Restriction Default</span></span>|<span data-ttu-id="1e53e-175">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="1e53e-175">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="1e53e-176">Catalog</span><span class="sxs-lookup"><span data-stu-id="1e53e-176">Catalog</span></span>|@Catalog|<span data-ttu-id="1e53e-177">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1e53e-177">TABLE_CATALOG</span></span>|<span data-ttu-id="1e53e-178">1</span><span class="sxs-lookup"><span data-stu-id="1e53e-178">1</span></span>|  
|<span data-ttu-id="1e53e-179">Besitzer</span><span class="sxs-lookup"><span data-stu-id="1e53e-179">Owner</span></span>|@Owner|<span data-ttu-id="1e53e-180">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1e53e-180">TABLE_SCHEMA</span></span>|<span data-ttu-id="1e53e-181">2</span><span class="sxs-lookup"><span data-stu-id="1e53e-181">2</span></span>|  
|<span data-ttu-id="1e53e-182">Tabelle</span><span class="sxs-lookup"><span data-stu-id="1e53e-182">Table</span></span>|@Table|<span data-ttu-id="1e53e-183">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1e53e-183">TABLE_NAME</span></span>|<span data-ttu-id="1e53e-184">3</span><span class="sxs-lookup"><span data-stu-id="1e53e-184">3</span></span>|  
|<span data-ttu-id="1e53e-185">Spalte</span><span class="sxs-lookup"><span data-stu-id="1e53e-185">Column</span></span>|@Column|<span data-ttu-id="1e53e-186">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="1e53e-186">COLUMN_NAME</span></span>|<span data-ttu-id="1e53e-187">4</span><span class="sxs-lookup"><span data-stu-id="1e53e-187">4</span></span>|  
  
### <a name="structuredtypemembers"></a><span data-ttu-id="1e53e-188">StructuredTypeMembers</span><span class="sxs-lookup"><span data-stu-id="1e53e-188">StructuredTypeMembers</span></span>  
  
|<span data-ttu-id="1e53e-189">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="1e53e-189">Restriction Name</span></span>|<span data-ttu-id="1e53e-190">Parametername</span><span class="sxs-lookup"><span data-stu-id="1e53e-190">Parameter Name</span></span>|<span data-ttu-id="1e53e-191">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="1e53e-191">Restriction Default</span></span>|<span data-ttu-id="1e53e-192">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="1e53e-192">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="1e53e-193">Catalog</span><span class="sxs-lookup"><span data-stu-id="1e53e-193">Catalog</span></span>|@Catalog|<span data-ttu-id="1e53e-194">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1e53e-194">TABLE_CATALOG</span></span>|<span data-ttu-id="1e53e-195">1</span><span class="sxs-lookup"><span data-stu-id="1e53e-195">1</span></span>|  
|<span data-ttu-id="1e53e-196">Besitzer</span><span class="sxs-lookup"><span data-stu-id="1e53e-196">Owner</span></span>|@Owner|<span data-ttu-id="1e53e-197">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1e53e-197">TABLE_SCHEMA</span></span>|<span data-ttu-id="1e53e-198">2</span><span class="sxs-lookup"><span data-stu-id="1e53e-198">2</span></span>|  
|<span data-ttu-id="1e53e-199">Tabelle</span><span class="sxs-lookup"><span data-stu-id="1e53e-199">Table</span></span>|@Table|<span data-ttu-id="1e53e-200">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1e53e-200">TABLE_NAME</span></span>|<span data-ttu-id="1e53e-201">3</span><span class="sxs-lookup"><span data-stu-id="1e53e-201">3</span></span>|  
|<span data-ttu-id="1e53e-202">Spalte</span><span class="sxs-lookup"><span data-stu-id="1e53e-202">Column</span></span>|@Column|<span data-ttu-id="1e53e-203">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="1e53e-203">COLUMN_NAME</span></span>|<span data-ttu-id="1e53e-204">4</span><span class="sxs-lookup"><span data-stu-id="1e53e-204">4</span></span>|  
  
### <a name="views"></a><span data-ttu-id="1e53e-205">Ansichten</span><span class="sxs-lookup"><span data-stu-id="1e53e-205">Views</span></span>  
  
|<span data-ttu-id="1e53e-206">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="1e53e-206">Restriction Name</span></span>|<span data-ttu-id="1e53e-207">Parametername</span><span class="sxs-lookup"><span data-stu-id="1e53e-207">Parameter Name</span></span>|<span data-ttu-id="1e53e-208">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="1e53e-208">Restriction Default</span></span>|<span data-ttu-id="1e53e-209">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="1e53e-209">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="1e53e-210">Catalog</span><span class="sxs-lookup"><span data-stu-id="1e53e-210">Catalog</span></span>|@Catalog|<span data-ttu-id="1e53e-211">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1e53e-211">TABLE_CATALOG</span></span>|<span data-ttu-id="1e53e-212">1</span><span class="sxs-lookup"><span data-stu-id="1e53e-212">1</span></span>|  
|<span data-ttu-id="1e53e-213">Besitzer</span><span class="sxs-lookup"><span data-stu-id="1e53e-213">Owner</span></span>|@Owner|<span data-ttu-id="1e53e-214">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1e53e-214">TABLE_SCHEMA</span></span>|<span data-ttu-id="1e53e-215">2</span><span class="sxs-lookup"><span data-stu-id="1e53e-215">2</span></span>|  
|<span data-ttu-id="1e53e-216">Tabelle</span><span class="sxs-lookup"><span data-stu-id="1e53e-216">Table</span></span>|@Table|<span data-ttu-id="1e53e-217">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1e53e-217">TABLE_NAME</span></span>|<span data-ttu-id="1e53e-218">3</span><span class="sxs-lookup"><span data-stu-id="1e53e-218">3</span></span>|  
  
### <a name="viewcolumns"></a><span data-ttu-id="1e53e-219">ViewColumns</span><span class="sxs-lookup"><span data-stu-id="1e53e-219">ViewColumns</span></span>  
  
|<span data-ttu-id="1e53e-220">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="1e53e-220">Restriction Name</span></span>|<span data-ttu-id="1e53e-221">Parametername</span><span class="sxs-lookup"><span data-stu-id="1e53e-221">Parameter Name</span></span>|<span data-ttu-id="1e53e-222">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="1e53e-222">Restriction Default</span></span>|<span data-ttu-id="1e53e-223">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="1e53e-223">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="1e53e-224">Catalog</span><span class="sxs-lookup"><span data-stu-id="1e53e-224">Catalog</span></span>|@Catalog|<span data-ttu-id="1e53e-225">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1e53e-225">VIEW_CATALOG</span></span>|<span data-ttu-id="1e53e-226">1</span><span class="sxs-lookup"><span data-stu-id="1e53e-226">1</span></span>|  
|<span data-ttu-id="1e53e-227">Besitzer</span><span class="sxs-lookup"><span data-stu-id="1e53e-227">Owner</span></span>|@Owner|<span data-ttu-id="1e53e-228">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1e53e-228">VIEW_SCHEMA</span></span>|<span data-ttu-id="1e53e-229">2</span><span class="sxs-lookup"><span data-stu-id="1e53e-229">2</span></span>|  
|<span data-ttu-id="1e53e-230">Tabelle</span><span class="sxs-lookup"><span data-stu-id="1e53e-230">Table</span></span>|@Table|<span data-ttu-id="1e53e-231">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="1e53e-231">VIEW_NAME</span></span>|<span data-ttu-id="1e53e-232">3</span><span class="sxs-lookup"><span data-stu-id="1e53e-232">3</span></span>|  
|<span data-ttu-id="1e53e-233">Spalte</span><span class="sxs-lookup"><span data-stu-id="1e53e-233">Column</span></span>|@Column|<span data-ttu-id="1e53e-234">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="1e53e-234">COLUMN_NAME</span></span>|<span data-ttu-id="1e53e-235">4</span><span class="sxs-lookup"><span data-stu-id="1e53e-235">4</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="1e53e-236">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="1e53e-236">ProcedureParameters</span></span>  
  
|<span data-ttu-id="1e53e-237">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="1e53e-237">Restriction Name</span></span>|<span data-ttu-id="1e53e-238">Parametername</span><span class="sxs-lookup"><span data-stu-id="1e53e-238">Parameter Name</span></span>|<span data-ttu-id="1e53e-239">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="1e53e-239">Restriction Default</span></span>|<span data-ttu-id="1e53e-240">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="1e53e-240">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="1e53e-241">Catalog</span><span class="sxs-lookup"><span data-stu-id="1e53e-241">Catalog</span></span>|@Catalog|<span data-ttu-id="1e53e-242">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1e53e-242">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="1e53e-243">1</span><span class="sxs-lookup"><span data-stu-id="1e53e-243">1</span></span>|  
|<span data-ttu-id="1e53e-244">Besitzer</span><span class="sxs-lookup"><span data-stu-id="1e53e-244">Owner</span></span>|@Owner|<span data-ttu-id="1e53e-245">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1e53e-245">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="1e53e-246">2</span><span class="sxs-lookup"><span data-stu-id="1e53e-246">2</span></span>|  
|<span data-ttu-id="1e53e-247">Name</span><span class="sxs-lookup"><span data-stu-id="1e53e-247">Name</span></span>|@Name|<span data-ttu-id="1e53e-248">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="1e53e-248">SPECIFIC_NAME</span></span>|<span data-ttu-id="1e53e-249">3</span><span class="sxs-lookup"><span data-stu-id="1e53e-249">3</span></span>|  
|<span data-ttu-id="1e53e-250">Parameter</span><span class="sxs-lookup"><span data-stu-id="1e53e-250">Parameter</span></span>|@Parameter|<span data-ttu-id="1e53e-251">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="1e53e-251">PARAMETER_NAME</span></span>|<span data-ttu-id="1e53e-252">4</span><span class="sxs-lookup"><span data-stu-id="1e53e-252">4</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="1e53e-253">Verfahren</span><span class="sxs-lookup"><span data-stu-id="1e53e-253">Procedures</span></span>  
  
|<span data-ttu-id="1e53e-254">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="1e53e-254">Restriction Name</span></span>|<span data-ttu-id="1e53e-255">Parametername</span><span class="sxs-lookup"><span data-stu-id="1e53e-255">Parameter Name</span></span>|<span data-ttu-id="1e53e-256">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="1e53e-256">Restriction Default</span></span>|<span data-ttu-id="1e53e-257">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="1e53e-257">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="1e53e-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="1e53e-258">Catalog</span></span>|@Catalog|<span data-ttu-id="1e53e-259">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1e53e-259">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="1e53e-260">1</span><span class="sxs-lookup"><span data-stu-id="1e53e-260">1</span></span>|  
|<span data-ttu-id="1e53e-261">Besitzer</span><span class="sxs-lookup"><span data-stu-id="1e53e-261">Owner</span></span>|@Owner|<span data-ttu-id="1e53e-262">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1e53e-262">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="1e53e-263">2</span><span class="sxs-lookup"><span data-stu-id="1e53e-263">2</span></span>|  
|<span data-ttu-id="1e53e-264">Name</span><span class="sxs-lookup"><span data-stu-id="1e53e-264">Name</span></span>|@Name|<span data-ttu-id="1e53e-265">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="1e53e-265">SPECIFIC_NAME</span></span>|<span data-ttu-id="1e53e-266">3</span><span class="sxs-lookup"><span data-stu-id="1e53e-266">3</span></span>|  
|<span data-ttu-id="1e53e-267">Typ</span><span class="sxs-lookup"><span data-stu-id="1e53e-267">Type</span></span>|@Type|<span data-ttu-id="1e53e-268">ROUTINE_TYPE</span><span class="sxs-lookup"><span data-stu-id="1e53e-268">ROUTINE_TYPE</span></span>|<span data-ttu-id="1e53e-269">4</span><span class="sxs-lookup"><span data-stu-id="1e53e-269">4</span></span>|  
  
### <a name="indexcolumns"></a><span data-ttu-id="1e53e-270">IndexColumns</span><span class="sxs-lookup"><span data-stu-id="1e53e-270">IndexColumns</span></span>  
  
|<span data-ttu-id="1e53e-271">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="1e53e-271">Restriction Name</span></span>|<span data-ttu-id="1e53e-272">Parametername</span><span class="sxs-lookup"><span data-stu-id="1e53e-272">Parameter Name</span></span>|<span data-ttu-id="1e53e-273">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="1e53e-273">Restriction Default</span></span>|<span data-ttu-id="1e53e-274">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="1e53e-274">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="1e53e-275">Catalog</span><span class="sxs-lookup"><span data-stu-id="1e53e-275">Catalog</span></span>|@Catalog|<span data-ttu-id="1e53e-276">db_name()</span><span class="sxs-lookup"><span data-stu-id="1e53e-276">db_name()</span></span>|<span data-ttu-id="1e53e-277">1</span><span class="sxs-lookup"><span data-stu-id="1e53e-277">1</span></span>|  
|<span data-ttu-id="1e53e-278">Besitzer</span><span class="sxs-lookup"><span data-stu-id="1e53e-278">Owner</span></span>|@Owner|<span data-ttu-id="1e53e-279">user_name()</span><span class="sxs-lookup"><span data-stu-id="1e53e-279">user_name()</span></span>|<span data-ttu-id="1e53e-280">2</span><span class="sxs-lookup"><span data-stu-id="1e53e-280">2</span></span>|  
|<span data-ttu-id="1e53e-281">Tabelle</span><span class="sxs-lookup"><span data-stu-id="1e53e-281">Table</span></span>|@Table|<span data-ttu-id="1e53e-282">o.name</span><span class="sxs-lookup"><span data-stu-id="1e53e-282">o.name</span></span>|<span data-ttu-id="1e53e-283">3</span><span class="sxs-lookup"><span data-stu-id="1e53e-283">3</span></span>|  
|<span data-ttu-id="1e53e-284">ConstraintName</span><span class="sxs-lookup"><span data-stu-id="1e53e-284">ConstraintName</span></span>|@ConstraintName|<span data-ttu-id="1e53e-285">x.name</span><span class="sxs-lookup"><span data-stu-id="1e53e-285">x.name</span></span>|<span data-ttu-id="1e53e-286">4</span><span class="sxs-lookup"><span data-stu-id="1e53e-286">4</span></span>|  
|<span data-ttu-id="1e53e-287">Spalte</span><span class="sxs-lookup"><span data-stu-id="1e53e-287">Column</span></span>|@Column|<span data-ttu-id="1e53e-288">c.name</span><span class="sxs-lookup"><span data-stu-id="1e53e-288">c.name</span></span>|<span data-ttu-id="1e53e-289">5</span><span class="sxs-lookup"><span data-stu-id="1e53e-289">5</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="1e53e-290">Indexes</span><span class="sxs-lookup"><span data-stu-id="1e53e-290">Indexes</span></span>  
  
|<span data-ttu-id="1e53e-291">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="1e53e-291">Restriction Name</span></span>|<span data-ttu-id="1e53e-292">Parametername</span><span class="sxs-lookup"><span data-stu-id="1e53e-292">Parameter Name</span></span>|<span data-ttu-id="1e53e-293">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="1e53e-293">Restriction Default</span></span>|<span data-ttu-id="1e53e-294">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="1e53e-294">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="1e53e-295">Catalog</span><span class="sxs-lookup"><span data-stu-id="1e53e-295">Catalog</span></span>|@Catalog|<span data-ttu-id="1e53e-296">db_name()</span><span class="sxs-lookup"><span data-stu-id="1e53e-296">db_name()</span></span>|<span data-ttu-id="1e53e-297">1</span><span class="sxs-lookup"><span data-stu-id="1e53e-297">1</span></span>|  
|<span data-ttu-id="1e53e-298">Besitzer</span><span class="sxs-lookup"><span data-stu-id="1e53e-298">Owner</span></span>|@Owner|<span data-ttu-id="1e53e-299">user_name()</span><span class="sxs-lookup"><span data-stu-id="1e53e-299">user_name()</span></span>|<span data-ttu-id="1e53e-300">2</span><span class="sxs-lookup"><span data-stu-id="1e53e-300">2</span></span>|  
|<span data-ttu-id="1e53e-301">Tabelle</span><span class="sxs-lookup"><span data-stu-id="1e53e-301">Table</span></span>|@Table|<span data-ttu-id="1e53e-302">o.name</span><span class="sxs-lookup"><span data-stu-id="1e53e-302">o.name</span></span>|<span data-ttu-id="1e53e-303">3</span><span class="sxs-lookup"><span data-stu-id="1e53e-303">3</span></span>|  
  
### <a name="userdefinedtypes"></a><span data-ttu-id="1e53e-304">UserDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="1e53e-304">UserDefinedTypes</span></span>  
  
|<span data-ttu-id="1e53e-305">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="1e53e-305">Restriction Name</span></span>|<span data-ttu-id="1e53e-306">Parametername</span><span class="sxs-lookup"><span data-stu-id="1e53e-306">Parameter Name</span></span>|<span data-ttu-id="1e53e-307">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="1e53e-307">Restriction Default</span></span>|<span data-ttu-id="1e53e-308">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="1e53e-308">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="1e53e-309">assembly_name</span><span class="sxs-lookup"><span data-stu-id="1e53e-309">assembly_name</span></span>|@AssemblyName|<span data-ttu-id="1e53e-310">assemblies.name</span><span class="sxs-lookup"><span data-stu-id="1e53e-310">assemblies.name</span></span>|<span data-ttu-id="1e53e-311">1</span><span class="sxs-lookup"><span data-stu-id="1e53e-311">1</span></span>|  
|<span data-ttu-id="1e53e-312">udt_name</span><span class="sxs-lookup"><span data-stu-id="1e53e-312">udt_name</span></span>|@UDTName|<span data-ttu-id="1e53e-313">types.assembly_class</span><span class="sxs-lookup"><span data-stu-id="1e53e-313">types.assembly_class</span></span>|<span data-ttu-id="1e53e-314">2</span><span class="sxs-lookup"><span data-stu-id="1e53e-314">2</span></span>|  
  
### <a name="foreignkeys"></a><span data-ttu-id="1e53e-315">ForeignKeys</span><span class="sxs-lookup"><span data-stu-id="1e53e-315">ForeignKeys</span></span>  
  
|<span data-ttu-id="1e53e-316">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="1e53e-316">Restriction Name</span></span>|<span data-ttu-id="1e53e-317">Parametername</span><span class="sxs-lookup"><span data-stu-id="1e53e-317">Parameter Name</span></span>|<span data-ttu-id="1e53e-318">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="1e53e-318">Restriction Default</span></span>|<span data-ttu-id="1e53e-319">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="1e53e-319">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="1e53e-320">Catalog</span><span class="sxs-lookup"><span data-stu-id="1e53e-320">Catalog</span></span>|@Catalog|<span data-ttu-id="1e53e-321">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1e53e-321">CONSTRAINT_CATALOG</span></span>|<span data-ttu-id="1e53e-322">1</span><span class="sxs-lookup"><span data-stu-id="1e53e-322">1</span></span>|  
|<span data-ttu-id="1e53e-323">Besitzer</span><span class="sxs-lookup"><span data-stu-id="1e53e-323">Owner</span></span>|@Owner|<span data-ttu-id="1e53e-324">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1e53e-324">CONSTRAINT_SCHEMA</span></span>|<span data-ttu-id="1e53e-325">2</span><span class="sxs-lookup"><span data-stu-id="1e53e-325">2</span></span>|  
|<span data-ttu-id="1e53e-326">Tabelle</span><span class="sxs-lookup"><span data-stu-id="1e53e-326">Table</span></span>|@Table|<span data-ttu-id="1e53e-327">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1e53e-327">TABLE_NAME</span></span>|<span data-ttu-id="1e53e-328">3</span><span class="sxs-lookup"><span data-stu-id="1e53e-328">3</span></span>|  
|<span data-ttu-id="1e53e-329">Name</span><span class="sxs-lookup"><span data-stu-id="1e53e-329">Name</span></span>|@Name|<span data-ttu-id="1e53e-330">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="1e53e-330">CONSTRAINT_NAME</span></span>|<span data-ttu-id="1e53e-331">4</span><span class="sxs-lookup"><span data-stu-id="1e53e-331">4</span></span>|  
  
## <a name="sql-server-2008-schema-restrictions"></a><span data-ttu-id="1e53e-332">SQL Server 2008-Schemabeschränkungen</span><span class="sxs-lookup"><span data-stu-id="1e53e-332">SQL Server 2008 Schema Restrictions</span></span>  
 <span data-ttu-id="1e53e-333">In den folgenden Tabellen sind die Beschränkungen für SQL Server 2008-Schemaauflistungen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="1e53e-333">The following tables list the restrictions for SQL Server 2008 schema collections.</span></span> <span data-ttu-id="1e53e-334">Diese Beschränkungen gelten ab Version 3.5 SP1 von .NET Framework und SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="1e53e-334">These restrictions are valid beginning with version 3.5 SP1 of the .NET Framework and SQL Server 2008.</span></span> <span data-ttu-id="1e53e-335">Sie werden in früheren Versionen von .NET Framework und SQL Server nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1e53e-335">They are not supported in earlier versions of the .NET Framework and SQL Server.</span></span>  
  
### <a name="columnsetcolumns"></a><span data-ttu-id="1e53e-336">ColumnSetColumns</span><span class="sxs-lookup"><span data-stu-id="1e53e-336">ColumnSetColumns</span></span>  
  
|<span data-ttu-id="1e53e-337">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="1e53e-337">Restriction Name</span></span>|<span data-ttu-id="1e53e-338">Parametername</span><span class="sxs-lookup"><span data-stu-id="1e53e-338">Parameter Name</span></span>|<span data-ttu-id="1e53e-339">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="1e53e-339">Restriction Default</span></span>|<span data-ttu-id="1e53e-340">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="1e53e-340">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="1e53e-341">Catalog</span><span class="sxs-lookup"><span data-stu-id="1e53e-341">Catalog</span></span>|@Catalog|<span data-ttu-id="1e53e-342">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1e53e-342">TABLE_CATALOG</span></span>|<span data-ttu-id="1e53e-343">1</span><span class="sxs-lookup"><span data-stu-id="1e53e-343">1</span></span>|  
|<span data-ttu-id="1e53e-344">Besitzer</span><span class="sxs-lookup"><span data-stu-id="1e53e-344">Owner</span></span>|@Owner|<span data-ttu-id="1e53e-345">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1e53e-345">TABLE_SCHEMA</span></span>|<span data-ttu-id="1e53e-346">2</span><span class="sxs-lookup"><span data-stu-id="1e53e-346">2</span></span>|  
|<span data-ttu-id="1e53e-347">Tabelle</span><span class="sxs-lookup"><span data-stu-id="1e53e-347">Table</span></span>|@Table|<span data-ttu-id="1e53e-348">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1e53e-348">TABLE_NAME</span></span>|<span data-ttu-id="1e53e-349">3</span><span class="sxs-lookup"><span data-stu-id="1e53e-349">3</span></span>|  
  
### <a name="allcolumns"></a><span data-ttu-id="1e53e-350">AllColumns</span><span class="sxs-lookup"><span data-stu-id="1e53e-350">AllColumns</span></span>  
  
|<span data-ttu-id="1e53e-351">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="1e53e-351">Restriction Name</span></span>|<span data-ttu-id="1e53e-352">Parametername</span><span class="sxs-lookup"><span data-stu-id="1e53e-352">Parameter Name</span></span>|<span data-ttu-id="1e53e-353">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="1e53e-353">Restriction Default</span></span>|<span data-ttu-id="1e53e-354">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="1e53e-354">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="1e53e-355">Catalog</span><span class="sxs-lookup"><span data-stu-id="1e53e-355">Catalog</span></span>|@Catalog|<span data-ttu-id="1e53e-356">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1e53e-356">TABLE_CATALOG</span></span>|<span data-ttu-id="1e53e-357">1</span><span class="sxs-lookup"><span data-stu-id="1e53e-357">1</span></span>|  
|<span data-ttu-id="1e53e-358">Besitzer</span><span class="sxs-lookup"><span data-stu-id="1e53e-358">Owner</span></span>|@Owner|<span data-ttu-id="1e53e-359">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1e53e-359">TABLE_SCHEMA</span></span>|<span data-ttu-id="1e53e-360">2</span><span class="sxs-lookup"><span data-stu-id="1e53e-360">2</span></span>|  
|<span data-ttu-id="1e53e-361">Tabelle</span><span class="sxs-lookup"><span data-stu-id="1e53e-361">Table</span></span>|@Table|<span data-ttu-id="1e53e-362">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1e53e-362">TABLE_NAME</span></span>|<span data-ttu-id="1e53e-363">3</span><span class="sxs-lookup"><span data-stu-id="1e53e-363">3</span></span>|  
|<span data-ttu-id="1e53e-364">Spalte</span><span class="sxs-lookup"><span data-stu-id="1e53e-364">Column</span></span>|@Column|<span data-ttu-id="1e53e-365">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="1e53e-365">COLUMN_NAME</span></span>|<span data-ttu-id="1e53e-366">4</span><span class="sxs-lookup"><span data-stu-id="1e53e-366">4</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1e53e-367">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1e53e-367">See Also</span></span>  
 [<span data-ttu-id="1e53e-368">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="1e53e-368">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
