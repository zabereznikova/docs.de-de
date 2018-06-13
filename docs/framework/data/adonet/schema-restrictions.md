---
title: Schemaeinschränkungen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
ms.openlocfilehash: c62f934561fa4a6c352ff84b8c1201461c42de39
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33357256"
---
# <a name="schema-restrictions"></a><span data-ttu-id="d0b41-102">Schemaeinschränkungen</span><span class="sxs-lookup"><span data-stu-id="d0b41-102">Schema Restrictions</span></span>
<span data-ttu-id="d0b41-103">Den optionalen zweiten Parameter von der **GetSchema** Methode ist die Einschränkungen, die verwendet werden, um die Begrenzung des Umfangs der Schemainformationen zurückgegeben und erfolgt eine Übergabe an die **GetSchema** -Methode ein Array von Zeichenfolgen .</span><span class="sxs-lookup"><span data-stu-id="d0b41-103">The second optional parameter of the **GetSchema** method is the restrictions that are used to limit the amount of schema information returned, and it is passed to the **GetSchema** method as an array of strings.</span></span> <span data-ttu-id="d0b41-104">Die Position im Array bestimmt die Werte, die zurückgegeben werden können. Dies entspricht der Anzahl der Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="d0b41-104">The position in the array determines the values that you can pass, and this is equivalent to the restriction number.</span></span>  
  
 <span data-ttu-id="d0b41-105">In der folgenden Tabelle werden beispielsweise die Einschränkungen beschrieben, die von der Schemaauflistung "Tables" mithilfe des .NET Framework-Datenanbieters für SQL Server unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="d0b41-105">For example, the following table describes the restrictions supported by the "Tables" schema collection using the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="d0b41-106">Zusätzliche Einschränkungen für SQL Server-Schemaauflistungen werden am Ende dieses Themas aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="d0b41-106">Additional restrictions for SQL Server schema collections are listed at the end of this topic.</span></span>  
  
|<span data-ttu-id="d0b41-107">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="d0b41-107">Restriction Name</span></span>|<span data-ttu-id="d0b41-108">Parametername</span><span class="sxs-lookup"><span data-stu-id="d0b41-108">Parameter Name</span></span>|<span data-ttu-id="d0b41-109">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="d0b41-109">Restriction Default</span></span>|<span data-ttu-id="d0b41-110">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="d0b41-110">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d0b41-111">Catalog</span><span class="sxs-lookup"><span data-stu-id="d0b41-111">Catalog</span></span>|@Catalog|<span data-ttu-id="d0b41-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d0b41-112">TABLE_CATALOG</span></span>|<span data-ttu-id="d0b41-113">1</span><span class="sxs-lookup"><span data-stu-id="d0b41-113">1</span></span>|  
|<span data-ttu-id="d0b41-114">Besitzer</span><span class="sxs-lookup"><span data-stu-id="d0b41-114">Owner</span></span>|@Owner|<span data-ttu-id="d0b41-115">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d0b41-115">TABLE_SCHEMA</span></span>|<span data-ttu-id="d0b41-116">2</span><span class="sxs-lookup"><span data-stu-id="d0b41-116">2</span></span>|  
|<span data-ttu-id="d0b41-117">Tabelle</span><span class="sxs-lookup"><span data-stu-id="d0b41-117">Table</span></span>|@Name|<span data-ttu-id="d0b41-118">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d0b41-118">TABLE_NAME</span></span>|<span data-ttu-id="d0b41-119">3</span><span class="sxs-lookup"><span data-stu-id="d0b41-119">3</span></span>|  
|<span data-ttu-id="d0b41-120">TableType</span><span class="sxs-lookup"><span data-stu-id="d0b41-120">TableType</span></span>|@TableType|<span data-ttu-id="d0b41-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d0b41-121">TABLE_TYPE</span></span>|<span data-ttu-id="d0b41-122">4</span><span class="sxs-lookup"><span data-stu-id="d0b41-122">4</span></span>|  
  
## <a name="specifying-restriction-values"></a><span data-ttu-id="d0b41-123">Angeben der Einschränkungswerte</span><span class="sxs-lookup"><span data-stu-id="d0b41-123">Specifying Restriction Values</span></span>  
 <span data-ttu-id="d0b41-124">Wenn Sie eine der Einschränkungen der Tables-Schemaauflistung verwenden möchten, erstellen Sie ein Zeichenfolgenarray mit vier Elementen und fügen einen Wert in das Element ein, das mit der Einschränkungsnummer übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="d0b41-124">To use one of the restrictions of the "Tables" schema collection, simply create an array of strings with four elements, then place a value in the element that matches the restriction number.</span></span> <span data-ttu-id="d0b41-125">Z. B. zum Einschränken der Tabellen zurückgegeben, durch die **GetSchema** Methode, um nur die Tabellen im Schema "Sales" legen Sie das zweite Element des Arrays "Sales" vor der Übergabe an die **GetSchema** Methode.</span><span class="sxs-lookup"><span data-stu-id="d0b41-125">For example, to restrict the tables returned by the **GetSchema** method to only those tables in the "Sales" schema, set the second element of the array to "Sales" before passing it to the **GetSchema** method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d0b41-126">Die Einschränkungsauflistungen für den `SqlClient` und den `OracleClient` verfügen über eine zusätzliche `ParameterName`-Spalte.</span><span class="sxs-lookup"><span data-stu-id="d0b41-126">The restrictions collections for `SqlClient` and `OracleClient` have an additional `ParameterName` column.</span></span> <span data-ttu-id="d0b41-127">Die Spalte für den Einschränkungsstandard ist zwar aus Gründen der Abwärtskompatibilität vorhanden, wird aber derzeit ignoriert.</span><span class="sxs-lookup"><span data-stu-id="d0b41-127">The restriction default column is still there for backwards compatibility, but is currently ignored.</span></span> <span data-ttu-id="d0b41-128">Verwenden Sie Abfragen mit Parametern statt Zeichenfolgenersetzungen, um das Risiko eines SQL-Injection-Angriffs beim Angeben der Einschränkungswerte zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="d0b41-128">Parameterized queries rather than string replacement should be used to minimize the risk of an SQL injection attack when specifying restriction values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d0b41-129">Die Anzahl der Elementen im Array muss kleiner oder gleich der Anzahl der Einschränkungen sein, die für die angegebene Schemaauflistung unterstützt werden, da sonst eine <xref:System.ArgumentException> ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="d0b41-129">The number of elements in the array must be less than or equal to the number of restrictions supported for the specified schema collection else an <xref:System.ArgumentException> will be thrown.</span></span> <span data-ttu-id="d0b41-130">Es können weniger Elemente als die maximale Anzahl der Einschränkungen vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="d0b41-130">There can be fewer than the maximum number of restrictions.</span></span> <span data-ttu-id="d0b41-131">Es wird davon ausgegangen, dass die fehlenden Einschränkungen NULL (uneingeschränkt) sind.</span><span class="sxs-lookup"><span data-stu-id="d0b41-131">The missing restrictions are assumed to be null (unrestricted).</span></span>  
  
 <span data-ttu-id="d0b41-132">Sie können einen verwalteten .NET Framework-Anbieter, um die Liste der unterstützten Einschränkungen durch Aufrufen von Abfragen die **GetSchema** Methode mit dem Namen der schemaauflistung der Einschränkungen, die "Restrictions" lautet.</span><span class="sxs-lookup"><span data-stu-id="d0b41-132">You can query a .NET Framework managed provider to determine the list of supported restrictions by calling the **GetSchema** method with the name of the restrictions schema collection, which is "Restrictions".</span></span> <span data-ttu-id="d0b41-133">Dabei wird eine <xref:System.Data.DataTable> mit einer Liste der Auflistungsnamen, Einschränkungsnamen, Standardeinschränkungswerte und der Anzahl der Einschränkungen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d0b41-133">This will return a <xref:System.Data.DataTable> with a list of the collection names, the restriction names, the default restriction values, and the restriction numbers.</span></span>  
  
### <a name="example"></a><span data-ttu-id="d0b41-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d0b41-134">Example</span></span>  
 <span data-ttu-id="d0b41-135">Die folgenden Beispiele veranschaulichen, wie Sie die <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> Methode von der .NET Framework-Datenanbieter für SQL Server <xref:System.Data.SqlClient.SqlConnection> -Klasse zum Abrufen von Schemainformationen zu allen enthaltenen Tabellen die **AdventureWorks**Beispieldatenbank und zum Einschränken der Informationen, die an die Tabellen im "Sales"-Schema zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="d0b41-135">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database, and to restrict the information returned to only those tables in the "Sales" schema:</span></span>  
  
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
  
## <a name="sql-server-schema-restrictions"></a><span data-ttu-id="d0b41-136">SQL Server-Schemabeschränkungen</span><span class="sxs-lookup"><span data-stu-id="d0b41-136">SQL Server Schema Restrictions</span></span>  
 <span data-ttu-id="d0b41-137">In den folgenden Tabellen sind die Beschränkungen für SQL Server-Schemaauflistungen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="d0b41-137">The following tables list the restrictions for SQL Server schema collections.</span></span>  
  
### <a name="users"></a><span data-ttu-id="d0b41-138">Benutzer</span><span class="sxs-lookup"><span data-stu-id="d0b41-138">Users</span></span>  
  
|<span data-ttu-id="d0b41-139">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="d0b41-139">Restriction Name</span></span>|<span data-ttu-id="d0b41-140">Parametername</span><span class="sxs-lookup"><span data-stu-id="d0b41-140">Parameter Name</span></span>|<span data-ttu-id="d0b41-141">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="d0b41-141">Restriction Default</span></span>|<span data-ttu-id="d0b41-142">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="d0b41-142">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d0b41-143">User_Name</span><span class="sxs-lookup"><span data-stu-id="d0b41-143">User_Name</span></span>|@Name|<span data-ttu-id="d0b41-144">Name</span><span class="sxs-lookup"><span data-stu-id="d0b41-144">name</span></span>|<span data-ttu-id="d0b41-145">1</span><span class="sxs-lookup"><span data-stu-id="d0b41-145">1</span></span>|  
  
### <a name="databases"></a><span data-ttu-id="d0b41-146">Databases</span><span class="sxs-lookup"><span data-stu-id="d0b41-146">Databases</span></span>  
  
|<span data-ttu-id="d0b41-147">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="d0b41-147">Restriction Name</span></span>|<span data-ttu-id="d0b41-148">Parametername</span><span class="sxs-lookup"><span data-stu-id="d0b41-148">Parameter Name</span></span>|<span data-ttu-id="d0b41-149">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="d0b41-149">Restriction Default</span></span>|<span data-ttu-id="d0b41-150">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="d0b41-150">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d0b41-151">name</span><span class="sxs-lookup"><span data-stu-id="d0b41-151">Name</span></span>|@Name|<span data-ttu-id="d0b41-152">name</span><span class="sxs-lookup"><span data-stu-id="d0b41-152">Name</span></span>|<span data-ttu-id="d0b41-153">1</span><span class="sxs-lookup"><span data-stu-id="d0b41-153">1</span></span>|  
  
### <a name="tables"></a><span data-ttu-id="d0b41-154">Tabellen</span><span class="sxs-lookup"><span data-stu-id="d0b41-154">Tables</span></span>  
  
|<span data-ttu-id="d0b41-155">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="d0b41-155">Restriction Name</span></span>|<span data-ttu-id="d0b41-156">Parametername</span><span class="sxs-lookup"><span data-stu-id="d0b41-156">Parameter Name</span></span>|<span data-ttu-id="d0b41-157">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="d0b41-157">Restriction Default</span></span>|<span data-ttu-id="d0b41-158">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="d0b41-158">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d0b41-159">Catalog</span><span class="sxs-lookup"><span data-stu-id="d0b41-159">Catalog</span></span>|@Catalog|<span data-ttu-id="d0b41-160">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d0b41-160">TABLE_CATALOG</span></span>|<span data-ttu-id="d0b41-161">1</span><span class="sxs-lookup"><span data-stu-id="d0b41-161">1</span></span>|  
|<span data-ttu-id="d0b41-162">Besitzer</span><span class="sxs-lookup"><span data-stu-id="d0b41-162">Owner</span></span>|@Owner|<span data-ttu-id="d0b41-163">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d0b41-163">TABLE_SCHEMA</span></span>|<span data-ttu-id="d0b41-164">2</span><span class="sxs-lookup"><span data-stu-id="d0b41-164">2</span></span>|  
|<span data-ttu-id="d0b41-165">Tabelle</span><span class="sxs-lookup"><span data-stu-id="d0b41-165">Table</span></span>|@Name|<span data-ttu-id="d0b41-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d0b41-166">TABLE_NAME</span></span>|<span data-ttu-id="d0b41-167">3</span><span class="sxs-lookup"><span data-stu-id="d0b41-167">3</span></span>|  
|<span data-ttu-id="d0b41-168">TableType</span><span class="sxs-lookup"><span data-stu-id="d0b41-168">TableType</span></span>|@TableType|<span data-ttu-id="d0b41-169">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d0b41-169">TABLE_TYPE</span></span>|<span data-ttu-id="d0b41-170">4</span><span class="sxs-lookup"><span data-stu-id="d0b41-170">4</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="d0b41-171">Columns</span><span class="sxs-lookup"><span data-stu-id="d0b41-171">Columns</span></span>  
  
|<span data-ttu-id="d0b41-172">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="d0b41-172">Restriction Name</span></span>|<span data-ttu-id="d0b41-173">Parametername</span><span class="sxs-lookup"><span data-stu-id="d0b41-173">Parameter Name</span></span>|<span data-ttu-id="d0b41-174">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="d0b41-174">Restriction Default</span></span>|<span data-ttu-id="d0b41-175">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="d0b41-175">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d0b41-176">Catalog</span><span class="sxs-lookup"><span data-stu-id="d0b41-176">Catalog</span></span>|@Catalog|<span data-ttu-id="d0b41-177">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d0b41-177">TABLE_CATALOG</span></span>|<span data-ttu-id="d0b41-178">1</span><span class="sxs-lookup"><span data-stu-id="d0b41-178">1</span></span>|  
|<span data-ttu-id="d0b41-179">Besitzer</span><span class="sxs-lookup"><span data-stu-id="d0b41-179">Owner</span></span>|@Owner|<span data-ttu-id="d0b41-180">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d0b41-180">TABLE_SCHEMA</span></span>|<span data-ttu-id="d0b41-181">2</span><span class="sxs-lookup"><span data-stu-id="d0b41-181">2</span></span>|  
|<span data-ttu-id="d0b41-182">Tabelle</span><span class="sxs-lookup"><span data-stu-id="d0b41-182">Table</span></span>|@Table|<span data-ttu-id="d0b41-183">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d0b41-183">TABLE_NAME</span></span>|<span data-ttu-id="d0b41-184">3</span><span class="sxs-lookup"><span data-stu-id="d0b41-184">3</span></span>|  
|<span data-ttu-id="d0b41-185">Spalte</span><span class="sxs-lookup"><span data-stu-id="d0b41-185">Column</span></span>|@Column|<span data-ttu-id="d0b41-186">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d0b41-186">COLUMN_NAME</span></span>|<span data-ttu-id="d0b41-187">4</span><span class="sxs-lookup"><span data-stu-id="d0b41-187">4</span></span>|  
  
### <a name="structuredtypemembers"></a><span data-ttu-id="d0b41-188">StructuredTypeMembers</span><span class="sxs-lookup"><span data-stu-id="d0b41-188">StructuredTypeMembers</span></span>  
  
|<span data-ttu-id="d0b41-189">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="d0b41-189">Restriction Name</span></span>|<span data-ttu-id="d0b41-190">Parametername</span><span class="sxs-lookup"><span data-stu-id="d0b41-190">Parameter Name</span></span>|<span data-ttu-id="d0b41-191">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="d0b41-191">Restriction Default</span></span>|<span data-ttu-id="d0b41-192">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="d0b41-192">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d0b41-193">Catalog</span><span class="sxs-lookup"><span data-stu-id="d0b41-193">Catalog</span></span>|@Catalog|<span data-ttu-id="d0b41-194">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d0b41-194">TABLE_CATALOG</span></span>|<span data-ttu-id="d0b41-195">1</span><span class="sxs-lookup"><span data-stu-id="d0b41-195">1</span></span>|  
|<span data-ttu-id="d0b41-196">Besitzer</span><span class="sxs-lookup"><span data-stu-id="d0b41-196">Owner</span></span>|@Owner|<span data-ttu-id="d0b41-197">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d0b41-197">TABLE_SCHEMA</span></span>|<span data-ttu-id="d0b41-198">2</span><span class="sxs-lookup"><span data-stu-id="d0b41-198">2</span></span>|  
|<span data-ttu-id="d0b41-199">Tabelle</span><span class="sxs-lookup"><span data-stu-id="d0b41-199">Table</span></span>|@Table|<span data-ttu-id="d0b41-200">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d0b41-200">TABLE_NAME</span></span>|<span data-ttu-id="d0b41-201">3</span><span class="sxs-lookup"><span data-stu-id="d0b41-201">3</span></span>|  
|<span data-ttu-id="d0b41-202">Spalte</span><span class="sxs-lookup"><span data-stu-id="d0b41-202">Column</span></span>|@Column|<span data-ttu-id="d0b41-203">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d0b41-203">COLUMN_NAME</span></span>|<span data-ttu-id="d0b41-204">4</span><span class="sxs-lookup"><span data-stu-id="d0b41-204">4</span></span>|  
  
### <a name="views"></a><span data-ttu-id="d0b41-205">Ansichten</span><span class="sxs-lookup"><span data-stu-id="d0b41-205">Views</span></span>  
  
|<span data-ttu-id="d0b41-206">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="d0b41-206">Restriction Name</span></span>|<span data-ttu-id="d0b41-207">Parametername</span><span class="sxs-lookup"><span data-stu-id="d0b41-207">Parameter Name</span></span>|<span data-ttu-id="d0b41-208">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="d0b41-208">Restriction Default</span></span>|<span data-ttu-id="d0b41-209">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="d0b41-209">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d0b41-210">Catalog</span><span class="sxs-lookup"><span data-stu-id="d0b41-210">Catalog</span></span>|@Catalog|<span data-ttu-id="d0b41-211">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d0b41-211">TABLE_CATALOG</span></span>|<span data-ttu-id="d0b41-212">1</span><span class="sxs-lookup"><span data-stu-id="d0b41-212">1</span></span>|  
|<span data-ttu-id="d0b41-213">Besitzer</span><span class="sxs-lookup"><span data-stu-id="d0b41-213">Owner</span></span>|@Owner|<span data-ttu-id="d0b41-214">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d0b41-214">TABLE_SCHEMA</span></span>|<span data-ttu-id="d0b41-215">2</span><span class="sxs-lookup"><span data-stu-id="d0b41-215">2</span></span>|  
|<span data-ttu-id="d0b41-216">Tabelle</span><span class="sxs-lookup"><span data-stu-id="d0b41-216">Table</span></span>|@Table|<span data-ttu-id="d0b41-217">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d0b41-217">TABLE_NAME</span></span>|<span data-ttu-id="d0b41-218">3</span><span class="sxs-lookup"><span data-stu-id="d0b41-218">3</span></span>|  
  
### <a name="viewcolumns"></a><span data-ttu-id="d0b41-219">ViewColumns</span><span class="sxs-lookup"><span data-stu-id="d0b41-219">ViewColumns</span></span>  
  
|<span data-ttu-id="d0b41-220">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="d0b41-220">Restriction Name</span></span>|<span data-ttu-id="d0b41-221">Parametername</span><span class="sxs-lookup"><span data-stu-id="d0b41-221">Parameter Name</span></span>|<span data-ttu-id="d0b41-222">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="d0b41-222">Restriction Default</span></span>|<span data-ttu-id="d0b41-223">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="d0b41-223">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d0b41-224">Catalog</span><span class="sxs-lookup"><span data-stu-id="d0b41-224">Catalog</span></span>|@Catalog|<span data-ttu-id="d0b41-225">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d0b41-225">VIEW_CATALOG</span></span>|<span data-ttu-id="d0b41-226">1</span><span class="sxs-lookup"><span data-stu-id="d0b41-226">1</span></span>|  
|<span data-ttu-id="d0b41-227">Besitzer</span><span class="sxs-lookup"><span data-stu-id="d0b41-227">Owner</span></span>|@Owner|<span data-ttu-id="d0b41-228">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d0b41-228">VIEW_SCHEMA</span></span>|<span data-ttu-id="d0b41-229">2</span><span class="sxs-lookup"><span data-stu-id="d0b41-229">2</span></span>|  
|<span data-ttu-id="d0b41-230">Tabelle</span><span class="sxs-lookup"><span data-stu-id="d0b41-230">Table</span></span>|@Table|<span data-ttu-id="d0b41-231">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="d0b41-231">VIEW_NAME</span></span>|<span data-ttu-id="d0b41-232">3</span><span class="sxs-lookup"><span data-stu-id="d0b41-232">3</span></span>|  
|<span data-ttu-id="d0b41-233">Spalte</span><span class="sxs-lookup"><span data-stu-id="d0b41-233">Column</span></span>|@Column|<span data-ttu-id="d0b41-234">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d0b41-234">COLUMN_NAME</span></span>|<span data-ttu-id="d0b41-235">4</span><span class="sxs-lookup"><span data-stu-id="d0b41-235">4</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="d0b41-236">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="d0b41-236">ProcedureParameters</span></span>  
  
|<span data-ttu-id="d0b41-237">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="d0b41-237">Restriction Name</span></span>|<span data-ttu-id="d0b41-238">Parametername</span><span class="sxs-lookup"><span data-stu-id="d0b41-238">Parameter Name</span></span>|<span data-ttu-id="d0b41-239">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="d0b41-239">Restriction Default</span></span>|<span data-ttu-id="d0b41-240">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="d0b41-240">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d0b41-241">Catalog</span><span class="sxs-lookup"><span data-stu-id="d0b41-241">Catalog</span></span>|@Catalog|<span data-ttu-id="d0b41-242">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d0b41-242">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="d0b41-243">1</span><span class="sxs-lookup"><span data-stu-id="d0b41-243">1</span></span>|  
|<span data-ttu-id="d0b41-244">Besitzer</span><span class="sxs-lookup"><span data-stu-id="d0b41-244">Owner</span></span>|@Owner|<span data-ttu-id="d0b41-245">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d0b41-245">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="d0b41-246">2</span><span class="sxs-lookup"><span data-stu-id="d0b41-246">2</span></span>|  
|<span data-ttu-id="d0b41-247">name</span><span class="sxs-lookup"><span data-stu-id="d0b41-247">Name</span></span>|@Name|<span data-ttu-id="d0b41-248">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="d0b41-248">SPECIFIC_NAME</span></span>|<span data-ttu-id="d0b41-249">3</span><span class="sxs-lookup"><span data-stu-id="d0b41-249">3</span></span>|  
|<span data-ttu-id="d0b41-250">Parameter</span><span class="sxs-lookup"><span data-stu-id="d0b41-250">Parameter</span></span>|@Parameter|<span data-ttu-id="d0b41-251">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="d0b41-251">PARAMETER_NAME</span></span>|<span data-ttu-id="d0b41-252">4</span><span class="sxs-lookup"><span data-stu-id="d0b41-252">4</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="d0b41-253">Verfahren</span><span class="sxs-lookup"><span data-stu-id="d0b41-253">Procedures</span></span>  
  
|<span data-ttu-id="d0b41-254">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="d0b41-254">Restriction Name</span></span>|<span data-ttu-id="d0b41-255">Parametername</span><span class="sxs-lookup"><span data-stu-id="d0b41-255">Parameter Name</span></span>|<span data-ttu-id="d0b41-256">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="d0b41-256">Restriction Default</span></span>|<span data-ttu-id="d0b41-257">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="d0b41-257">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d0b41-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="d0b41-258">Catalog</span></span>|@Catalog|<span data-ttu-id="d0b41-259">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d0b41-259">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="d0b41-260">1</span><span class="sxs-lookup"><span data-stu-id="d0b41-260">1</span></span>|  
|<span data-ttu-id="d0b41-261">Besitzer</span><span class="sxs-lookup"><span data-stu-id="d0b41-261">Owner</span></span>|@Owner|<span data-ttu-id="d0b41-262">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d0b41-262">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="d0b41-263">2</span><span class="sxs-lookup"><span data-stu-id="d0b41-263">2</span></span>|  
|<span data-ttu-id="d0b41-264">name</span><span class="sxs-lookup"><span data-stu-id="d0b41-264">Name</span></span>|@Name|<span data-ttu-id="d0b41-265">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="d0b41-265">SPECIFIC_NAME</span></span>|<span data-ttu-id="d0b41-266">3</span><span class="sxs-lookup"><span data-stu-id="d0b41-266">3</span></span>|  
|<span data-ttu-id="d0b41-267">Typ</span><span class="sxs-lookup"><span data-stu-id="d0b41-267">Type</span></span>|@Type|<span data-ttu-id="d0b41-268">ROUTINE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d0b41-268">ROUTINE_TYPE</span></span>|<span data-ttu-id="d0b41-269">4</span><span class="sxs-lookup"><span data-stu-id="d0b41-269">4</span></span>|  
  
### <a name="indexcolumns"></a><span data-ttu-id="d0b41-270">IndexColumns</span><span class="sxs-lookup"><span data-stu-id="d0b41-270">IndexColumns</span></span>  
  
|<span data-ttu-id="d0b41-271">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="d0b41-271">Restriction Name</span></span>|<span data-ttu-id="d0b41-272">Parametername</span><span class="sxs-lookup"><span data-stu-id="d0b41-272">Parameter Name</span></span>|<span data-ttu-id="d0b41-273">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="d0b41-273">Restriction Default</span></span>|<span data-ttu-id="d0b41-274">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="d0b41-274">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d0b41-275">Catalog</span><span class="sxs-lookup"><span data-stu-id="d0b41-275">Catalog</span></span>|@Catalog|<span data-ttu-id="d0b41-276">db_name()</span><span class="sxs-lookup"><span data-stu-id="d0b41-276">db_name()</span></span>|<span data-ttu-id="d0b41-277">1</span><span class="sxs-lookup"><span data-stu-id="d0b41-277">1</span></span>|  
|<span data-ttu-id="d0b41-278">Besitzer</span><span class="sxs-lookup"><span data-stu-id="d0b41-278">Owner</span></span>|@Owner|<span data-ttu-id="d0b41-279">user_name()</span><span class="sxs-lookup"><span data-stu-id="d0b41-279">user_name()</span></span>|<span data-ttu-id="d0b41-280">2</span><span class="sxs-lookup"><span data-stu-id="d0b41-280">2</span></span>|  
|<span data-ttu-id="d0b41-281">Tabelle</span><span class="sxs-lookup"><span data-stu-id="d0b41-281">Table</span></span>|@Table|<span data-ttu-id="d0b41-282">o.name</span><span class="sxs-lookup"><span data-stu-id="d0b41-282">o.name</span></span>|<span data-ttu-id="d0b41-283">3</span><span class="sxs-lookup"><span data-stu-id="d0b41-283">3</span></span>|  
|<span data-ttu-id="d0b41-284">ConstraintName</span><span class="sxs-lookup"><span data-stu-id="d0b41-284">ConstraintName</span></span>|@ConstraintName|<span data-ttu-id="d0b41-285">x.name</span><span class="sxs-lookup"><span data-stu-id="d0b41-285">x.name</span></span>|<span data-ttu-id="d0b41-286">4</span><span class="sxs-lookup"><span data-stu-id="d0b41-286">4</span></span>|  
|<span data-ttu-id="d0b41-287">Spalte</span><span class="sxs-lookup"><span data-stu-id="d0b41-287">Column</span></span>|@Column|<span data-ttu-id="d0b41-288">c.name</span><span class="sxs-lookup"><span data-stu-id="d0b41-288">c.name</span></span>|<span data-ttu-id="d0b41-289">5</span><span class="sxs-lookup"><span data-stu-id="d0b41-289">5</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="d0b41-290">Indexes</span><span class="sxs-lookup"><span data-stu-id="d0b41-290">Indexes</span></span>  
  
|<span data-ttu-id="d0b41-291">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="d0b41-291">Restriction Name</span></span>|<span data-ttu-id="d0b41-292">Parametername</span><span class="sxs-lookup"><span data-stu-id="d0b41-292">Parameter Name</span></span>|<span data-ttu-id="d0b41-293">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="d0b41-293">Restriction Default</span></span>|<span data-ttu-id="d0b41-294">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="d0b41-294">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d0b41-295">Catalog</span><span class="sxs-lookup"><span data-stu-id="d0b41-295">Catalog</span></span>|@Catalog|<span data-ttu-id="d0b41-296">db_name()</span><span class="sxs-lookup"><span data-stu-id="d0b41-296">db_name()</span></span>|<span data-ttu-id="d0b41-297">1</span><span class="sxs-lookup"><span data-stu-id="d0b41-297">1</span></span>|  
|<span data-ttu-id="d0b41-298">Besitzer</span><span class="sxs-lookup"><span data-stu-id="d0b41-298">Owner</span></span>|@Owner|<span data-ttu-id="d0b41-299">user_name()</span><span class="sxs-lookup"><span data-stu-id="d0b41-299">user_name()</span></span>|<span data-ttu-id="d0b41-300">2</span><span class="sxs-lookup"><span data-stu-id="d0b41-300">2</span></span>|  
|<span data-ttu-id="d0b41-301">Tabelle</span><span class="sxs-lookup"><span data-stu-id="d0b41-301">Table</span></span>|@Table|<span data-ttu-id="d0b41-302">o.name</span><span class="sxs-lookup"><span data-stu-id="d0b41-302">o.name</span></span>|<span data-ttu-id="d0b41-303">3</span><span class="sxs-lookup"><span data-stu-id="d0b41-303">3</span></span>|  
  
### <a name="userdefinedtypes"></a><span data-ttu-id="d0b41-304">UserDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="d0b41-304">UserDefinedTypes</span></span>  
  
|<span data-ttu-id="d0b41-305">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="d0b41-305">Restriction Name</span></span>|<span data-ttu-id="d0b41-306">Parametername</span><span class="sxs-lookup"><span data-stu-id="d0b41-306">Parameter Name</span></span>|<span data-ttu-id="d0b41-307">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="d0b41-307">Restriction Default</span></span>|<span data-ttu-id="d0b41-308">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="d0b41-308">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d0b41-309">assembly_name</span><span class="sxs-lookup"><span data-stu-id="d0b41-309">assembly_name</span></span>|@AssemblyName|<span data-ttu-id="d0b41-310">assemblies.name</span><span class="sxs-lookup"><span data-stu-id="d0b41-310">assemblies.name</span></span>|<span data-ttu-id="d0b41-311">1</span><span class="sxs-lookup"><span data-stu-id="d0b41-311">1</span></span>|  
|<span data-ttu-id="d0b41-312">udt_name</span><span class="sxs-lookup"><span data-stu-id="d0b41-312">udt_name</span></span>|@UDTName|<span data-ttu-id="d0b41-313">types.assembly_class</span><span class="sxs-lookup"><span data-stu-id="d0b41-313">types.assembly_class</span></span>|<span data-ttu-id="d0b41-314">2</span><span class="sxs-lookup"><span data-stu-id="d0b41-314">2</span></span>|  
  
### <a name="foreignkeys"></a><span data-ttu-id="d0b41-315">ForeignKeys</span><span class="sxs-lookup"><span data-stu-id="d0b41-315">ForeignKeys</span></span>  
  
|<span data-ttu-id="d0b41-316">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="d0b41-316">Restriction Name</span></span>|<span data-ttu-id="d0b41-317">Parametername</span><span class="sxs-lookup"><span data-stu-id="d0b41-317">Parameter Name</span></span>|<span data-ttu-id="d0b41-318">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="d0b41-318">Restriction Default</span></span>|<span data-ttu-id="d0b41-319">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="d0b41-319">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d0b41-320">Catalog</span><span class="sxs-lookup"><span data-stu-id="d0b41-320">Catalog</span></span>|@Catalog|<span data-ttu-id="d0b41-321">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d0b41-321">CONSTRAINT_CATALOG</span></span>|<span data-ttu-id="d0b41-322">1</span><span class="sxs-lookup"><span data-stu-id="d0b41-322">1</span></span>|  
|<span data-ttu-id="d0b41-323">Besitzer</span><span class="sxs-lookup"><span data-stu-id="d0b41-323">Owner</span></span>|@Owner|<span data-ttu-id="d0b41-324">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d0b41-324">CONSTRAINT_SCHEMA</span></span>|<span data-ttu-id="d0b41-325">2</span><span class="sxs-lookup"><span data-stu-id="d0b41-325">2</span></span>|  
|<span data-ttu-id="d0b41-326">Tabelle</span><span class="sxs-lookup"><span data-stu-id="d0b41-326">Table</span></span>|@Table|<span data-ttu-id="d0b41-327">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d0b41-327">TABLE_NAME</span></span>|<span data-ttu-id="d0b41-328">3</span><span class="sxs-lookup"><span data-stu-id="d0b41-328">3</span></span>|  
|<span data-ttu-id="d0b41-329">name</span><span class="sxs-lookup"><span data-stu-id="d0b41-329">Name</span></span>|@Name|<span data-ttu-id="d0b41-330">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="d0b41-330">CONSTRAINT_NAME</span></span>|<span data-ttu-id="d0b41-331">4</span><span class="sxs-lookup"><span data-stu-id="d0b41-331">4</span></span>|  
  
## <a name="sql-server-2008-schema-restrictions"></a><span data-ttu-id="d0b41-332">SQL Server 2008-Schemabeschränkungen</span><span class="sxs-lookup"><span data-stu-id="d0b41-332">SQL Server 2008 Schema Restrictions</span></span>  
 <span data-ttu-id="d0b41-333">In den folgenden Tabellen sind die Beschränkungen für SQL Server 2008-Schemaauflistungen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="d0b41-333">The following tables list the restrictions for SQL Server 2008 schema collections.</span></span> <span data-ttu-id="d0b41-334">Diese Beschränkungen gelten ab Version 3.5 SP1 von .NET Framework und SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="d0b41-334">These restrictions are valid beginning with version 3.5 SP1 of the .NET Framework and SQL Server 2008.</span></span> <span data-ttu-id="d0b41-335">Sie werden in früheren Versionen von .NET Framework und SQL Server nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d0b41-335">They are not supported in earlier versions of the .NET Framework and SQL Server.</span></span>  
  
### <a name="columnsetcolumns"></a><span data-ttu-id="d0b41-336">ColumnSetColumns</span><span class="sxs-lookup"><span data-stu-id="d0b41-336">ColumnSetColumns</span></span>  
  
|<span data-ttu-id="d0b41-337">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="d0b41-337">Restriction Name</span></span>|<span data-ttu-id="d0b41-338">Parametername</span><span class="sxs-lookup"><span data-stu-id="d0b41-338">Parameter Name</span></span>|<span data-ttu-id="d0b41-339">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="d0b41-339">Restriction Default</span></span>|<span data-ttu-id="d0b41-340">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="d0b41-340">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d0b41-341">Catalog</span><span class="sxs-lookup"><span data-stu-id="d0b41-341">Catalog</span></span>|@Catalog|<span data-ttu-id="d0b41-342">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d0b41-342">TABLE_CATALOG</span></span>|<span data-ttu-id="d0b41-343">1</span><span class="sxs-lookup"><span data-stu-id="d0b41-343">1</span></span>|  
|<span data-ttu-id="d0b41-344">Besitzer</span><span class="sxs-lookup"><span data-stu-id="d0b41-344">Owner</span></span>|@Owner|<span data-ttu-id="d0b41-345">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d0b41-345">TABLE_SCHEMA</span></span>|<span data-ttu-id="d0b41-346">2</span><span class="sxs-lookup"><span data-stu-id="d0b41-346">2</span></span>|  
|<span data-ttu-id="d0b41-347">Tabelle</span><span class="sxs-lookup"><span data-stu-id="d0b41-347">Table</span></span>|@Table|<span data-ttu-id="d0b41-348">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d0b41-348">TABLE_NAME</span></span>|<span data-ttu-id="d0b41-349">3</span><span class="sxs-lookup"><span data-stu-id="d0b41-349">3</span></span>|  
  
### <a name="allcolumns"></a><span data-ttu-id="d0b41-350">AllColumns</span><span class="sxs-lookup"><span data-stu-id="d0b41-350">AllColumns</span></span>  
  
|<span data-ttu-id="d0b41-351">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="d0b41-351">Restriction Name</span></span>|<span data-ttu-id="d0b41-352">Parametername</span><span class="sxs-lookup"><span data-stu-id="d0b41-352">Parameter Name</span></span>|<span data-ttu-id="d0b41-353">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="d0b41-353">Restriction Default</span></span>|<span data-ttu-id="d0b41-354">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="d0b41-354">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d0b41-355">Catalog</span><span class="sxs-lookup"><span data-stu-id="d0b41-355">Catalog</span></span>|@Catalog|<span data-ttu-id="d0b41-356">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d0b41-356">TABLE_CATALOG</span></span>|<span data-ttu-id="d0b41-357">1</span><span class="sxs-lookup"><span data-stu-id="d0b41-357">1</span></span>|  
|<span data-ttu-id="d0b41-358">Besitzer</span><span class="sxs-lookup"><span data-stu-id="d0b41-358">Owner</span></span>|@Owner|<span data-ttu-id="d0b41-359">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d0b41-359">TABLE_SCHEMA</span></span>|<span data-ttu-id="d0b41-360">2</span><span class="sxs-lookup"><span data-stu-id="d0b41-360">2</span></span>|  
|<span data-ttu-id="d0b41-361">Tabelle</span><span class="sxs-lookup"><span data-stu-id="d0b41-361">Table</span></span>|@Table|<span data-ttu-id="d0b41-362">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d0b41-362">TABLE_NAME</span></span>|<span data-ttu-id="d0b41-363">3</span><span class="sxs-lookup"><span data-stu-id="d0b41-363">3</span></span>|  
|<span data-ttu-id="d0b41-364">Spalte</span><span class="sxs-lookup"><span data-stu-id="d0b41-364">Column</span></span>|@Column|<span data-ttu-id="d0b41-365">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d0b41-365">COLUMN_NAME</span></span>|<span data-ttu-id="d0b41-366">4</span><span class="sxs-lookup"><span data-stu-id="d0b41-366">4</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d0b41-367">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d0b41-367">See Also</span></span>  
 [<span data-ttu-id="d0b41-368">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="d0b41-368">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
