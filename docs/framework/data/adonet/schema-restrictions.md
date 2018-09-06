---
title: Schemaeinschränkungen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
ms.openlocfilehash: 040ecd8a2ce223f89601de735b77ccc81638c7af
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43884730"
---
# <a name="schema-restrictions"></a><span data-ttu-id="a05a1-102">Schemaeinschränkungen</span><span class="sxs-lookup"><span data-stu-id="a05a1-102">Schema Restrictions</span></span>
<span data-ttu-id="a05a1-103">Der zweite optionale Parameter, der die **GetSchema** Methode ist, die Einschränkungen, die verwendet werden, um die Schemainformationen begrenzen zurückgegeben werden soll, und es wird zum Übergeben der **GetSchema** -Methode, wie ein Array von Zeichenfolgen .</span><span class="sxs-lookup"><span data-stu-id="a05a1-103">The second optional parameter of the **GetSchema** method is the restrictions that are used to limit the amount of schema information returned, and it is passed to the **GetSchema** method as an array of strings.</span></span> <span data-ttu-id="a05a1-104">Die Position im Array bestimmt die Werte, die zurückgegeben werden können. Dies entspricht der Anzahl der Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="a05a1-104">The position in the array determines the values that you can pass, and this is equivalent to the restriction number.</span></span>  
  
 <span data-ttu-id="a05a1-105">In der folgenden Tabelle werden beispielsweise die Einschränkungen beschrieben, die von der Schemaauflistung "Tables" mithilfe des .NET Framework-Datenanbieters für SQL Server unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="a05a1-105">For example, the following table describes the restrictions supported by the "Tables" schema collection using the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="a05a1-106">Zusätzliche Einschränkungen für SQL Server-Schemaauflistungen werden am Ende dieses Themas aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="a05a1-106">Additional restrictions for SQL Server schema collections are listed at the end of this topic.</span></span>  
  
|<span data-ttu-id="a05a1-107">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="a05a1-107">Restriction Name</span></span>|<span data-ttu-id="a05a1-108">Parametername</span><span class="sxs-lookup"><span data-stu-id="a05a1-108">Parameter Name</span></span>|<span data-ttu-id="a05a1-109">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="a05a1-109">Restriction Default</span></span>|<span data-ttu-id="a05a1-110">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="a05a1-110">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a05a1-111">Catalog</span><span class="sxs-lookup"><span data-stu-id="a05a1-111">Catalog</span></span>|@Catalog|<span data-ttu-id="a05a1-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a05a1-112">TABLE_CATALOG</span></span>|<span data-ttu-id="a05a1-113">1</span><span class="sxs-lookup"><span data-stu-id="a05a1-113">1</span></span>|  
|<span data-ttu-id="a05a1-114">Besitzer</span><span class="sxs-lookup"><span data-stu-id="a05a1-114">Owner</span></span>|@Owner|<span data-ttu-id="a05a1-115">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a05a1-115">TABLE_SCHEMA</span></span>|<span data-ttu-id="a05a1-116">2</span><span class="sxs-lookup"><span data-stu-id="a05a1-116">2</span></span>|  
|<span data-ttu-id="a05a1-117">Tabelle</span><span class="sxs-lookup"><span data-stu-id="a05a1-117">Table</span></span>|@Name|<span data-ttu-id="a05a1-118">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="a05a1-118">TABLE_NAME</span></span>|<span data-ttu-id="a05a1-119">3</span><span class="sxs-lookup"><span data-stu-id="a05a1-119">3</span></span>|  
|<span data-ttu-id="a05a1-120">TableType</span><span class="sxs-lookup"><span data-stu-id="a05a1-120">TableType</span></span>|@TableType|<span data-ttu-id="a05a1-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="a05a1-121">TABLE_TYPE</span></span>|<span data-ttu-id="a05a1-122">4</span><span class="sxs-lookup"><span data-stu-id="a05a1-122">4</span></span>|  
  
## <a name="specifying-restriction-values"></a><span data-ttu-id="a05a1-123">Angeben der Einschränkungswerte</span><span class="sxs-lookup"><span data-stu-id="a05a1-123">Specifying Restriction Values</span></span>  
 <span data-ttu-id="a05a1-124">Wenn Sie eine der Einschränkungen der Tables-Schemaauflistung verwenden möchten, erstellen Sie ein Zeichenfolgenarray mit vier Elementen und fügen einen Wert in das Element ein, das mit der Einschränkungsnummer übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="a05a1-124">To use one of the restrictions of the "Tables" schema collection, simply create an array of strings with four elements, then place a value in the element that matches the restriction number.</span></span> <span data-ttu-id="a05a1-125">Z. B. zum Einschränken der in den Tabellen zurückgegeben, durch die **GetSchema** Methode, um nur die Tabellen im Schema "Umsatz" legen Sie das zweite Element des Arrays, das "Sales" vor der Übergabe an die **GetSchema** Methode.</span><span class="sxs-lookup"><span data-stu-id="a05a1-125">For example, to restrict the tables returned by the **GetSchema** method to only those tables in the "Sales" schema, set the second element of the array to "Sales" before passing it to the **GetSchema** method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a05a1-126">Die Einschränkungsauflistungen für den `SqlClient` und den `OracleClient` verfügen über eine zusätzliche `ParameterName`-Spalte.</span><span class="sxs-lookup"><span data-stu-id="a05a1-126">The restrictions collections for `SqlClient` and `OracleClient` have an additional `ParameterName` column.</span></span> <span data-ttu-id="a05a1-127">Die Spalte für den Einschränkungsstandard ist zwar aus Gründen der Abwärtskompatibilität vorhanden, wird aber derzeit ignoriert.</span><span class="sxs-lookup"><span data-stu-id="a05a1-127">The restriction default column is still there for backwards compatibility, but is currently ignored.</span></span> <span data-ttu-id="a05a1-128">Verwenden Sie Abfragen mit Parametern statt Zeichenfolgenersetzungen, um das Risiko eines SQL-Injection-Angriffs beim Angeben der Einschränkungswerte zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="a05a1-128">Parameterized queries rather than string replacement should be used to minimize the risk of an SQL injection attack when specifying restriction values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a05a1-129">Die Anzahl der Elementen im Array muss kleiner oder gleich der Anzahl der Einschränkungen sein, die für die angegebene Schemaauflistung unterstützt werden, da sonst eine <xref:System.ArgumentException> ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="a05a1-129">The number of elements in the array must be less than or equal to the number of restrictions supported for the specified schema collection else an <xref:System.ArgumentException> will be thrown.</span></span> <span data-ttu-id="a05a1-130">Es können weniger Elemente als die maximale Anzahl der Einschränkungen vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="a05a1-130">There can be fewer than the maximum number of restrictions.</span></span> <span data-ttu-id="a05a1-131">Es wird davon ausgegangen, dass die fehlenden Einschränkungen NULL (uneingeschränkt) sind.</span><span class="sxs-lookup"><span data-stu-id="a05a1-131">The missing restrictions are assumed to be null (unrestricted).</span></span>  
  
 <span data-ttu-id="a05a1-132">Sie können einen verwalteten .NET Framework-Anbieter, um die Liste der unterstützten Einschränkungen durch den Aufruf zu bestimmen, Abfragen der **GetSchema** Methode durch den Namen der schemaauflistung der Einschränkungen, die "Restrictions" lautet.</span><span class="sxs-lookup"><span data-stu-id="a05a1-132">You can query a .NET Framework managed provider to determine the list of supported restrictions by calling the **GetSchema** method with the name of the restrictions schema collection, which is "Restrictions".</span></span> <span data-ttu-id="a05a1-133">Dabei wird eine <xref:System.Data.DataTable> mit einer Liste der Auflistungsnamen, Einschränkungsnamen, Standardeinschränkungswerte und der Anzahl der Einschränkungen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a05a1-133">This will return a <xref:System.Data.DataTable> with a list of the collection names, the restriction names, the default restriction values, and the restriction numbers.</span></span>  
  
### <a name="example"></a><span data-ttu-id="a05a1-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a05a1-134">Example</span></span>  
 <span data-ttu-id="a05a1-135">Die folgenden Beispiele veranschaulichen, wie Sie mit der <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> Methode von der .NET Framework-Datenanbieter für SQL Server <xref:System.Data.SqlClient.SqlConnection> -Klasse zum Abrufen von Schemainformationen zu allen enthaltenen Tabellen die **AdventureWorks**Beispieldatenbank und zum Einschränken der Informationen, die an die Tabellen im "Sales"-Schema zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="a05a1-135">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database, and to restrict the information returned to only those tables in the "Sales" schema:</span></span>  
  
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
  
## <a name="sql-server-schema-restrictions"></a><span data-ttu-id="a05a1-136">SQL Server-Schemabeschränkungen</span><span class="sxs-lookup"><span data-stu-id="a05a1-136">SQL Server Schema Restrictions</span></span>  
 <span data-ttu-id="a05a1-137">In den folgenden Tabellen sind die Beschränkungen für SQL Server-Schemaauflistungen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="a05a1-137">The following tables list the restrictions for SQL Server schema collections.</span></span>  
  
### <a name="users"></a><span data-ttu-id="a05a1-138">Benutzer</span><span class="sxs-lookup"><span data-stu-id="a05a1-138">Users</span></span>  
  
|<span data-ttu-id="a05a1-139">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="a05a1-139">Restriction Name</span></span>|<span data-ttu-id="a05a1-140">Parametername</span><span class="sxs-lookup"><span data-stu-id="a05a1-140">Parameter Name</span></span>|<span data-ttu-id="a05a1-141">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="a05a1-141">Restriction Default</span></span>|<span data-ttu-id="a05a1-142">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="a05a1-142">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a05a1-143">User_Name</span><span class="sxs-lookup"><span data-stu-id="a05a1-143">User_Name</span></span>|@Name|<span data-ttu-id="a05a1-144">Name</span><span class="sxs-lookup"><span data-stu-id="a05a1-144">name</span></span>|<span data-ttu-id="a05a1-145">1</span><span class="sxs-lookup"><span data-stu-id="a05a1-145">1</span></span>|  
  
### <a name="databases"></a><span data-ttu-id="a05a1-146">Databases</span><span class="sxs-lookup"><span data-stu-id="a05a1-146">Databases</span></span>  
  
|<span data-ttu-id="a05a1-147">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="a05a1-147">Restriction Name</span></span>|<span data-ttu-id="a05a1-148">Parametername</span><span class="sxs-lookup"><span data-stu-id="a05a1-148">Parameter Name</span></span>|<span data-ttu-id="a05a1-149">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="a05a1-149">Restriction Default</span></span>|<span data-ttu-id="a05a1-150">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="a05a1-150">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a05a1-151">name</span><span class="sxs-lookup"><span data-stu-id="a05a1-151">Name</span></span>|@Name|<span data-ttu-id="a05a1-152">name</span><span class="sxs-lookup"><span data-stu-id="a05a1-152">Name</span></span>|<span data-ttu-id="a05a1-153">1</span><span class="sxs-lookup"><span data-stu-id="a05a1-153">1</span></span>|  
  
### <a name="tables"></a><span data-ttu-id="a05a1-154">Tabellen</span><span class="sxs-lookup"><span data-stu-id="a05a1-154">Tables</span></span>  
  
|<span data-ttu-id="a05a1-155">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="a05a1-155">Restriction Name</span></span>|<span data-ttu-id="a05a1-156">Parametername</span><span class="sxs-lookup"><span data-stu-id="a05a1-156">Parameter Name</span></span>|<span data-ttu-id="a05a1-157">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="a05a1-157">Restriction Default</span></span>|<span data-ttu-id="a05a1-158">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="a05a1-158">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a05a1-159">Catalog</span><span class="sxs-lookup"><span data-stu-id="a05a1-159">Catalog</span></span>|@Catalog|<span data-ttu-id="a05a1-160">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a05a1-160">TABLE_CATALOG</span></span>|<span data-ttu-id="a05a1-161">1</span><span class="sxs-lookup"><span data-stu-id="a05a1-161">1</span></span>|  
|<span data-ttu-id="a05a1-162">Besitzer</span><span class="sxs-lookup"><span data-stu-id="a05a1-162">Owner</span></span>|@Owner|<span data-ttu-id="a05a1-163">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a05a1-163">TABLE_SCHEMA</span></span>|<span data-ttu-id="a05a1-164">2</span><span class="sxs-lookup"><span data-stu-id="a05a1-164">2</span></span>|  
|<span data-ttu-id="a05a1-165">Tabelle</span><span class="sxs-lookup"><span data-stu-id="a05a1-165">Table</span></span>|@Name|<span data-ttu-id="a05a1-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="a05a1-166">TABLE_NAME</span></span>|<span data-ttu-id="a05a1-167">3</span><span class="sxs-lookup"><span data-stu-id="a05a1-167">3</span></span>|  
|<span data-ttu-id="a05a1-168">TableType</span><span class="sxs-lookup"><span data-stu-id="a05a1-168">TableType</span></span>|@TableType|<span data-ttu-id="a05a1-169">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="a05a1-169">TABLE_TYPE</span></span>|<span data-ttu-id="a05a1-170">4</span><span class="sxs-lookup"><span data-stu-id="a05a1-170">4</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="a05a1-171">Columns</span><span class="sxs-lookup"><span data-stu-id="a05a1-171">Columns</span></span>  
  
|<span data-ttu-id="a05a1-172">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="a05a1-172">Restriction Name</span></span>|<span data-ttu-id="a05a1-173">Parametername</span><span class="sxs-lookup"><span data-stu-id="a05a1-173">Parameter Name</span></span>|<span data-ttu-id="a05a1-174">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="a05a1-174">Restriction Default</span></span>|<span data-ttu-id="a05a1-175">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="a05a1-175">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a05a1-176">Catalog</span><span class="sxs-lookup"><span data-stu-id="a05a1-176">Catalog</span></span>|@Catalog|<span data-ttu-id="a05a1-177">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a05a1-177">TABLE_CATALOG</span></span>|<span data-ttu-id="a05a1-178">1</span><span class="sxs-lookup"><span data-stu-id="a05a1-178">1</span></span>|  
|<span data-ttu-id="a05a1-179">Besitzer</span><span class="sxs-lookup"><span data-stu-id="a05a1-179">Owner</span></span>|@Owner|<span data-ttu-id="a05a1-180">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a05a1-180">TABLE_SCHEMA</span></span>|<span data-ttu-id="a05a1-181">2</span><span class="sxs-lookup"><span data-stu-id="a05a1-181">2</span></span>|  
|<span data-ttu-id="a05a1-182">Tabelle</span><span class="sxs-lookup"><span data-stu-id="a05a1-182">Table</span></span>|@Table|<span data-ttu-id="a05a1-183">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="a05a1-183">TABLE_NAME</span></span>|<span data-ttu-id="a05a1-184">3</span><span class="sxs-lookup"><span data-stu-id="a05a1-184">3</span></span>|  
|<span data-ttu-id="a05a1-185">Spalte</span><span class="sxs-lookup"><span data-stu-id="a05a1-185">Column</span></span>|@Column|<span data-ttu-id="a05a1-186">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="a05a1-186">COLUMN_NAME</span></span>|<span data-ttu-id="a05a1-187">4</span><span class="sxs-lookup"><span data-stu-id="a05a1-187">4</span></span>|  
  
### <a name="structuredtypemembers"></a><span data-ttu-id="a05a1-188">StructuredTypeMembers</span><span class="sxs-lookup"><span data-stu-id="a05a1-188">StructuredTypeMembers</span></span>  
  
|<span data-ttu-id="a05a1-189">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="a05a1-189">Restriction Name</span></span>|<span data-ttu-id="a05a1-190">Parametername</span><span class="sxs-lookup"><span data-stu-id="a05a1-190">Parameter Name</span></span>|<span data-ttu-id="a05a1-191">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="a05a1-191">Restriction Default</span></span>|<span data-ttu-id="a05a1-192">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="a05a1-192">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a05a1-193">Catalog</span><span class="sxs-lookup"><span data-stu-id="a05a1-193">Catalog</span></span>|@Catalog|<span data-ttu-id="a05a1-194">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a05a1-194">TABLE_CATALOG</span></span>|<span data-ttu-id="a05a1-195">1</span><span class="sxs-lookup"><span data-stu-id="a05a1-195">1</span></span>|  
|<span data-ttu-id="a05a1-196">Besitzer</span><span class="sxs-lookup"><span data-stu-id="a05a1-196">Owner</span></span>|@Owner|<span data-ttu-id="a05a1-197">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a05a1-197">TABLE_SCHEMA</span></span>|<span data-ttu-id="a05a1-198">2</span><span class="sxs-lookup"><span data-stu-id="a05a1-198">2</span></span>|  
|<span data-ttu-id="a05a1-199">Tabelle</span><span class="sxs-lookup"><span data-stu-id="a05a1-199">Table</span></span>|@Table|<span data-ttu-id="a05a1-200">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="a05a1-200">TABLE_NAME</span></span>|<span data-ttu-id="a05a1-201">3</span><span class="sxs-lookup"><span data-stu-id="a05a1-201">3</span></span>|  
|<span data-ttu-id="a05a1-202">Spalte</span><span class="sxs-lookup"><span data-stu-id="a05a1-202">Column</span></span>|@Column|<span data-ttu-id="a05a1-203">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="a05a1-203">COLUMN_NAME</span></span>|<span data-ttu-id="a05a1-204">4</span><span class="sxs-lookup"><span data-stu-id="a05a1-204">4</span></span>|  
  
### <a name="views"></a><span data-ttu-id="a05a1-205">Ansichten</span><span class="sxs-lookup"><span data-stu-id="a05a1-205">Views</span></span>  
  
|<span data-ttu-id="a05a1-206">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="a05a1-206">Restriction Name</span></span>|<span data-ttu-id="a05a1-207">Parametername</span><span class="sxs-lookup"><span data-stu-id="a05a1-207">Parameter Name</span></span>|<span data-ttu-id="a05a1-208">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="a05a1-208">Restriction Default</span></span>|<span data-ttu-id="a05a1-209">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="a05a1-209">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a05a1-210">Catalog</span><span class="sxs-lookup"><span data-stu-id="a05a1-210">Catalog</span></span>|@Catalog|<span data-ttu-id="a05a1-211">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a05a1-211">TABLE_CATALOG</span></span>|<span data-ttu-id="a05a1-212">1</span><span class="sxs-lookup"><span data-stu-id="a05a1-212">1</span></span>|  
|<span data-ttu-id="a05a1-213">Besitzer</span><span class="sxs-lookup"><span data-stu-id="a05a1-213">Owner</span></span>|@Owner|<span data-ttu-id="a05a1-214">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a05a1-214">TABLE_SCHEMA</span></span>|<span data-ttu-id="a05a1-215">2</span><span class="sxs-lookup"><span data-stu-id="a05a1-215">2</span></span>|  
|<span data-ttu-id="a05a1-216">Tabelle</span><span class="sxs-lookup"><span data-stu-id="a05a1-216">Table</span></span>|@Table|<span data-ttu-id="a05a1-217">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="a05a1-217">TABLE_NAME</span></span>|<span data-ttu-id="a05a1-218">3</span><span class="sxs-lookup"><span data-stu-id="a05a1-218">3</span></span>|  
  
### <a name="viewcolumns"></a><span data-ttu-id="a05a1-219">ViewColumns</span><span class="sxs-lookup"><span data-stu-id="a05a1-219">ViewColumns</span></span>  
  
|<span data-ttu-id="a05a1-220">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="a05a1-220">Restriction Name</span></span>|<span data-ttu-id="a05a1-221">Parametername</span><span class="sxs-lookup"><span data-stu-id="a05a1-221">Parameter Name</span></span>|<span data-ttu-id="a05a1-222">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="a05a1-222">Restriction Default</span></span>|<span data-ttu-id="a05a1-223">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="a05a1-223">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a05a1-224">Catalog</span><span class="sxs-lookup"><span data-stu-id="a05a1-224">Catalog</span></span>|@Catalog|<span data-ttu-id="a05a1-225">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a05a1-225">VIEW_CATALOG</span></span>|<span data-ttu-id="a05a1-226">1</span><span class="sxs-lookup"><span data-stu-id="a05a1-226">1</span></span>|  
|<span data-ttu-id="a05a1-227">Besitzer</span><span class="sxs-lookup"><span data-stu-id="a05a1-227">Owner</span></span>|@Owner|<span data-ttu-id="a05a1-228">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a05a1-228">VIEW_SCHEMA</span></span>|<span data-ttu-id="a05a1-229">2</span><span class="sxs-lookup"><span data-stu-id="a05a1-229">2</span></span>|  
|<span data-ttu-id="a05a1-230">Tabelle</span><span class="sxs-lookup"><span data-stu-id="a05a1-230">Table</span></span>|@Table|<span data-ttu-id="a05a1-231">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="a05a1-231">VIEW_NAME</span></span>|<span data-ttu-id="a05a1-232">3</span><span class="sxs-lookup"><span data-stu-id="a05a1-232">3</span></span>|  
|<span data-ttu-id="a05a1-233">Spalte</span><span class="sxs-lookup"><span data-stu-id="a05a1-233">Column</span></span>|@Column|<span data-ttu-id="a05a1-234">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="a05a1-234">COLUMN_NAME</span></span>|<span data-ttu-id="a05a1-235">4</span><span class="sxs-lookup"><span data-stu-id="a05a1-235">4</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="a05a1-236">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="a05a1-236">ProcedureParameters</span></span>  
  
|<span data-ttu-id="a05a1-237">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="a05a1-237">Restriction Name</span></span>|<span data-ttu-id="a05a1-238">Parametername</span><span class="sxs-lookup"><span data-stu-id="a05a1-238">Parameter Name</span></span>|<span data-ttu-id="a05a1-239">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="a05a1-239">Restriction Default</span></span>|<span data-ttu-id="a05a1-240">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="a05a1-240">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a05a1-241">Catalog</span><span class="sxs-lookup"><span data-stu-id="a05a1-241">Catalog</span></span>|@Catalog|<span data-ttu-id="a05a1-242">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a05a1-242">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="a05a1-243">1</span><span class="sxs-lookup"><span data-stu-id="a05a1-243">1</span></span>|  
|<span data-ttu-id="a05a1-244">Besitzer</span><span class="sxs-lookup"><span data-stu-id="a05a1-244">Owner</span></span>|@Owner|<span data-ttu-id="a05a1-245">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a05a1-245">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="a05a1-246">2</span><span class="sxs-lookup"><span data-stu-id="a05a1-246">2</span></span>|  
|<span data-ttu-id="a05a1-247">name</span><span class="sxs-lookup"><span data-stu-id="a05a1-247">Name</span></span>|@Name|<span data-ttu-id="a05a1-248">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="a05a1-248">SPECIFIC_NAME</span></span>|<span data-ttu-id="a05a1-249">3</span><span class="sxs-lookup"><span data-stu-id="a05a1-249">3</span></span>|  
|<span data-ttu-id="a05a1-250">Parameter</span><span class="sxs-lookup"><span data-stu-id="a05a1-250">Parameter</span></span>|@Parameter|<span data-ttu-id="a05a1-251">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="a05a1-251">PARAMETER_NAME</span></span>|<span data-ttu-id="a05a1-252">4</span><span class="sxs-lookup"><span data-stu-id="a05a1-252">4</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="a05a1-253">Verfahren</span><span class="sxs-lookup"><span data-stu-id="a05a1-253">Procedures</span></span>  
  
|<span data-ttu-id="a05a1-254">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="a05a1-254">Restriction Name</span></span>|<span data-ttu-id="a05a1-255">Parametername</span><span class="sxs-lookup"><span data-stu-id="a05a1-255">Parameter Name</span></span>|<span data-ttu-id="a05a1-256">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="a05a1-256">Restriction Default</span></span>|<span data-ttu-id="a05a1-257">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="a05a1-257">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a05a1-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="a05a1-258">Catalog</span></span>|@Catalog|<span data-ttu-id="a05a1-259">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a05a1-259">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="a05a1-260">1</span><span class="sxs-lookup"><span data-stu-id="a05a1-260">1</span></span>|  
|<span data-ttu-id="a05a1-261">Besitzer</span><span class="sxs-lookup"><span data-stu-id="a05a1-261">Owner</span></span>|@Owner|<span data-ttu-id="a05a1-262">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a05a1-262">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="a05a1-263">2</span><span class="sxs-lookup"><span data-stu-id="a05a1-263">2</span></span>|  
|<span data-ttu-id="a05a1-264">name</span><span class="sxs-lookup"><span data-stu-id="a05a1-264">Name</span></span>|@Name|<span data-ttu-id="a05a1-265">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="a05a1-265">SPECIFIC_NAME</span></span>|<span data-ttu-id="a05a1-266">3</span><span class="sxs-lookup"><span data-stu-id="a05a1-266">3</span></span>|  
|<span data-ttu-id="a05a1-267">Typ</span><span class="sxs-lookup"><span data-stu-id="a05a1-267">Type</span></span>|@Type|<span data-ttu-id="a05a1-268">ROUTINE_TYPE</span><span class="sxs-lookup"><span data-stu-id="a05a1-268">ROUTINE_TYPE</span></span>|<span data-ttu-id="a05a1-269">4</span><span class="sxs-lookup"><span data-stu-id="a05a1-269">4</span></span>|  
  
### <a name="indexcolumns"></a><span data-ttu-id="a05a1-270">IndexColumns</span><span class="sxs-lookup"><span data-stu-id="a05a1-270">IndexColumns</span></span>  
  
|<span data-ttu-id="a05a1-271">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="a05a1-271">Restriction Name</span></span>|<span data-ttu-id="a05a1-272">Parametername</span><span class="sxs-lookup"><span data-stu-id="a05a1-272">Parameter Name</span></span>|<span data-ttu-id="a05a1-273">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="a05a1-273">Restriction Default</span></span>|<span data-ttu-id="a05a1-274">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="a05a1-274">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a05a1-275">Catalog</span><span class="sxs-lookup"><span data-stu-id="a05a1-275">Catalog</span></span>|@Catalog|<span data-ttu-id="a05a1-276">db_name()</span><span class="sxs-lookup"><span data-stu-id="a05a1-276">db_name()</span></span>|<span data-ttu-id="a05a1-277">1</span><span class="sxs-lookup"><span data-stu-id="a05a1-277">1</span></span>|  
|<span data-ttu-id="a05a1-278">Besitzer</span><span class="sxs-lookup"><span data-stu-id="a05a1-278">Owner</span></span>|@Owner|<span data-ttu-id="a05a1-279">user_name()</span><span class="sxs-lookup"><span data-stu-id="a05a1-279">user_name()</span></span>|<span data-ttu-id="a05a1-280">2</span><span class="sxs-lookup"><span data-stu-id="a05a1-280">2</span></span>|  
|<span data-ttu-id="a05a1-281">Tabelle</span><span class="sxs-lookup"><span data-stu-id="a05a1-281">Table</span></span>|@Table|<span data-ttu-id="a05a1-282">o.name</span><span class="sxs-lookup"><span data-stu-id="a05a1-282">o.name</span></span>|<span data-ttu-id="a05a1-283">3</span><span class="sxs-lookup"><span data-stu-id="a05a1-283">3</span></span>|  
|<span data-ttu-id="a05a1-284">ConstraintName</span><span class="sxs-lookup"><span data-stu-id="a05a1-284">ConstraintName</span></span>|@ConstraintName|<span data-ttu-id="a05a1-285">x.name</span><span class="sxs-lookup"><span data-stu-id="a05a1-285">x.name</span></span>|<span data-ttu-id="a05a1-286">4</span><span class="sxs-lookup"><span data-stu-id="a05a1-286">4</span></span>|  
|<span data-ttu-id="a05a1-287">Spalte</span><span class="sxs-lookup"><span data-stu-id="a05a1-287">Column</span></span>|@Column|<span data-ttu-id="a05a1-288">c.name</span><span class="sxs-lookup"><span data-stu-id="a05a1-288">c.name</span></span>|<span data-ttu-id="a05a1-289">5</span><span class="sxs-lookup"><span data-stu-id="a05a1-289">5</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="a05a1-290">Indexes</span><span class="sxs-lookup"><span data-stu-id="a05a1-290">Indexes</span></span>  
  
|<span data-ttu-id="a05a1-291">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="a05a1-291">Restriction Name</span></span>|<span data-ttu-id="a05a1-292">Parametername</span><span class="sxs-lookup"><span data-stu-id="a05a1-292">Parameter Name</span></span>|<span data-ttu-id="a05a1-293">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="a05a1-293">Restriction Default</span></span>|<span data-ttu-id="a05a1-294">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="a05a1-294">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a05a1-295">Catalog</span><span class="sxs-lookup"><span data-stu-id="a05a1-295">Catalog</span></span>|@Catalog|<span data-ttu-id="a05a1-296">db_name()</span><span class="sxs-lookup"><span data-stu-id="a05a1-296">db_name()</span></span>|<span data-ttu-id="a05a1-297">1</span><span class="sxs-lookup"><span data-stu-id="a05a1-297">1</span></span>|  
|<span data-ttu-id="a05a1-298">Besitzer</span><span class="sxs-lookup"><span data-stu-id="a05a1-298">Owner</span></span>|@Owner|<span data-ttu-id="a05a1-299">user_name()</span><span class="sxs-lookup"><span data-stu-id="a05a1-299">user_name()</span></span>|<span data-ttu-id="a05a1-300">2</span><span class="sxs-lookup"><span data-stu-id="a05a1-300">2</span></span>|  
|<span data-ttu-id="a05a1-301">Tabelle</span><span class="sxs-lookup"><span data-stu-id="a05a1-301">Table</span></span>|@Table|<span data-ttu-id="a05a1-302">o.name</span><span class="sxs-lookup"><span data-stu-id="a05a1-302">o.name</span></span>|<span data-ttu-id="a05a1-303">3</span><span class="sxs-lookup"><span data-stu-id="a05a1-303">3</span></span>|  
  
### <a name="userdefinedtypes"></a><span data-ttu-id="a05a1-304">UserDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="a05a1-304">UserDefinedTypes</span></span>  
  
|<span data-ttu-id="a05a1-305">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="a05a1-305">Restriction Name</span></span>|<span data-ttu-id="a05a1-306">Parametername</span><span class="sxs-lookup"><span data-stu-id="a05a1-306">Parameter Name</span></span>|<span data-ttu-id="a05a1-307">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="a05a1-307">Restriction Default</span></span>|<span data-ttu-id="a05a1-308">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="a05a1-308">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a05a1-309">assembly_name</span><span class="sxs-lookup"><span data-stu-id="a05a1-309">assembly_name</span></span>|@AssemblyName|<span data-ttu-id="a05a1-310">assemblies.name</span><span class="sxs-lookup"><span data-stu-id="a05a1-310">assemblies.name</span></span>|<span data-ttu-id="a05a1-311">1</span><span class="sxs-lookup"><span data-stu-id="a05a1-311">1</span></span>|  
|<span data-ttu-id="a05a1-312">udt_name</span><span class="sxs-lookup"><span data-stu-id="a05a1-312">udt_name</span></span>|@UDTName|<span data-ttu-id="a05a1-313">types.assembly_class</span><span class="sxs-lookup"><span data-stu-id="a05a1-313">types.assembly_class</span></span>|<span data-ttu-id="a05a1-314">2</span><span class="sxs-lookup"><span data-stu-id="a05a1-314">2</span></span>|  
  
### <a name="foreignkeys"></a><span data-ttu-id="a05a1-315">ForeignKeys</span><span class="sxs-lookup"><span data-stu-id="a05a1-315">ForeignKeys</span></span>  
  
|<span data-ttu-id="a05a1-316">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="a05a1-316">Restriction Name</span></span>|<span data-ttu-id="a05a1-317">Parametername</span><span class="sxs-lookup"><span data-stu-id="a05a1-317">Parameter Name</span></span>|<span data-ttu-id="a05a1-318">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="a05a1-318">Restriction Default</span></span>|<span data-ttu-id="a05a1-319">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="a05a1-319">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a05a1-320">Catalog</span><span class="sxs-lookup"><span data-stu-id="a05a1-320">Catalog</span></span>|@Catalog|<span data-ttu-id="a05a1-321">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a05a1-321">CONSTRAINT_CATALOG</span></span>|<span data-ttu-id="a05a1-322">1</span><span class="sxs-lookup"><span data-stu-id="a05a1-322">1</span></span>|  
|<span data-ttu-id="a05a1-323">Besitzer</span><span class="sxs-lookup"><span data-stu-id="a05a1-323">Owner</span></span>|@Owner|<span data-ttu-id="a05a1-324">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a05a1-324">CONSTRAINT_SCHEMA</span></span>|<span data-ttu-id="a05a1-325">2</span><span class="sxs-lookup"><span data-stu-id="a05a1-325">2</span></span>|  
|<span data-ttu-id="a05a1-326">Tabelle</span><span class="sxs-lookup"><span data-stu-id="a05a1-326">Table</span></span>|@Table|<span data-ttu-id="a05a1-327">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="a05a1-327">TABLE_NAME</span></span>|<span data-ttu-id="a05a1-328">3</span><span class="sxs-lookup"><span data-stu-id="a05a1-328">3</span></span>|  
|<span data-ttu-id="a05a1-329">name</span><span class="sxs-lookup"><span data-stu-id="a05a1-329">Name</span></span>|@Name|<span data-ttu-id="a05a1-330">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="a05a1-330">CONSTRAINT_NAME</span></span>|<span data-ttu-id="a05a1-331">4</span><span class="sxs-lookup"><span data-stu-id="a05a1-331">4</span></span>|  
  
## <a name="sql-server-2008-schema-restrictions"></a><span data-ttu-id="a05a1-332">SQL Server 2008-Schemabeschränkungen</span><span class="sxs-lookup"><span data-stu-id="a05a1-332">SQL Server 2008 Schema Restrictions</span></span>  
 <span data-ttu-id="a05a1-333">In den folgenden Tabellen sind die Beschränkungen für SQL Server 2008-Schemaauflistungen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="a05a1-333">The following tables list the restrictions for SQL Server 2008 schema collections.</span></span> <span data-ttu-id="a05a1-334">Diese Beschränkungen gelten ab Version 3.5 SP1 von .NET Framework und SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="a05a1-334">These restrictions are valid beginning with version 3.5 SP1 of the .NET Framework and SQL Server 2008.</span></span> <span data-ttu-id="a05a1-335">Sie werden in früheren Versionen von .NET Framework und SQL Server nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a05a1-335">They are not supported in earlier versions of the .NET Framework and SQL Server.</span></span>  
  
### <a name="columnsetcolumns"></a><span data-ttu-id="a05a1-336">ColumnSetColumns</span><span class="sxs-lookup"><span data-stu-id="a05a1-336">ColumnSetColumns</span></span>  
  
|<span data-ttu-id="a05a1-337">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="a05a1-337">Restriction Name</span></span>|<span data-ttu-id="a05a1-338">Parametername</span><span class="sxs-lookup"><span data-stu-id="a05a1-338">Parameter Name</span></span>|<span data-ttu-id="a05a1-339">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="a05a1-339">Restriction Default</span></span>|<span data-ttu-id="a05a1-340">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="a05a1-340">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a05a1-341">Catalog</span><span class="sxs-lookup"><span data-stu-id="a05a1-341">Catalog</span></span>|@Catalog|<span data-ttu-id="a05a1-342">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a05a1-342">TABLE_CATALOG</span></span>|<span data-ttu-id="a05a1-343">1</span><span class="sxs-lookup"><span data-stu-id="a05a1-343">1</span></span>|  
|<span data-ttu-id="a05a1-344">Besitzer</span><span class="sxs-lookup"><span data-stu-id="a05a1-344">Owner</span></span>|@Owner|<span data-ttu-id="a05a1-345">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a05a1-345">TABLE_SCHEMA</span></span>|<span data-ttu-id="a05a1-346">2</span><span class="sxs-lookup"><span data-stu-id="a05a1-346">2</span></span>|  
|<span data-ttu-id="a05a1-347">Tabelle</span><span class="sxs-lookup"><span data-stu-id="a05a1-347">Table</span></span>|@Table|<span data-ttu-id="a05a1-348">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="a05a1-348">TABLE_NAME</span></span>|<span data-ttu-id="a05a1-349">3</span><span class="sxs-lookup"><span data-stu-id="a05a1-349">3</span></span>|  
  
### <a name="allcolumns"></a><span data-ttu-id="a05a1-350">AllColumns</span><span class="sxs-lookup"><span data-stu-id="a05a1-350">AllColumns</span></span>  
  
|<span data-ttu-id="a05a1-351">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="a05a1-351">Restriction Name</span></span>|<span data-ttu-id="a05a1-352">Parametername</span><span class="sxs-lookup"><span data-stu-id="a05a1-352">Parameter Name</span></span>|<span data-ttu-id="a05a1-353">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="a05a1-353">Restriction Default</span></span>|<span data-ttu-id="a05a1-354">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="a05a1-354">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a05a1-355">Catalog</span><span class="sxs-lookup"><span data-stu-id="a05a1-355">Catalog</span></span>|@Catalog|<span data-ttu-id="a05a1-356">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a05a1-356">TABLE_CATALOG</span></span>|<span data-ttu-id="a05a1-357">1</span><span class="sxs-lookup"><span data-stu-id="a05a1-357">1</span></span>|  
|<span data-ttu-id="a05a1-358">Besitzer</span><span class="sxs-lookup"><span data-stu-id="a05a1-358">Owner</span></span>|@Owner|<span data-ttu-id="a05a1-359">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a05a1-359">TABLE_SCHEMA</span></span>|<span data-ttu-id="a05a1-360">2</span><span class="sxs-lookup"><span data-stu-id="a05a1-360">2</span></span>|  
|<span data-ttu-id="a05a1-361">Tabelle</span><span class="sxs-lookup"><span data-stu-id="a05a1-361">Table</span></span>|@Table|<span data-ttu-id="a05a1-362">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="a05a1-362">TABLE_NAME</span></span>|<span data-ttu-id="a05a1-363">3</span><span class="sxs-lookup"><span data-stu-id="a05a1-363">3</span></span>|  
|<span data-ttu-id="a05a1-364">Spalte</span><span class="sxs-lookup"><span data-stu-id="a05a1-364">Column</span></span>|@Column|<span data-ttu-id="a05a1-365">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="a05a1-365">COLUMN_NAME</span></span>|<span data-ttu-id="a05a1-366">4</span><span class="sxs-lookup"><span data-stu-id="a05a1-366">4</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a05a1-367">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a05a1-367">See Also</span></span>  
 [<span data-ttu-id="a05a1-368">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="a05a1-368">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
