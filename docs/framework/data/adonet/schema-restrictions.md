---
title: Schemaeinschränkungen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
ms.openlocfilehash: 040ecd8a2ce223f89601de735b77ccc81638c7af
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43563428"
---
# <a name="schema-restrictions"></a><span data-ttu-id="a5a80-102">Schemaeinschränkungen</span><span class="sxs-lookup"><span data-stu-id="a5a80-102">Schema Restrictions</span></span>
<span data-ttu-id="a5a80-103">Der zweite optionale Parameter, der die **GetSchema** Methode ist, die Einschränkungen, die verwendet werden, um die Schemainformationen begrenzen zurückgegeben werden soll, und es wird zum Übergeben der **GetSchema** -Methode, wie ein Array von Zeichenfolgen .</span><span class="sxs-lookup"><span data-stu-id="a5a80-103">The second optional parameter of the **GetSchema** method is the restrictions that are used to limit the amount of schema information returned, and it is passed to the **GetSchema** method as an array of strings.</span></span> <span data-ttu-id="a5a80-104">Die Position im Array bestimmt die Werte, die zurückgegeben werden können. Dies entspricht der Anzahl der Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="a5a80-104">The position in the array determines the values that you can pass, and this is equivalent to the restriction number.</span></span>  
  
 <span data-ttu-id="a5a80-105">In der folgenden Tabelle werden beispielsweise die Einschränkungen beschrieben, die von der Schemaauflistung "Tables" mithilfe des .NET Framework-Datenanbieters für SQL Server unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="a5a80-105">For example, the following table describes the restrictions supported by the "Tables" schema collection using the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="a5a80-106">Zusätzliche Einschränkungen für SQL Server-Schemaauflistungen werden am Ende dieses Themas aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="a5a80-106">Additional restrictions for SQL Server schema collections are listed at the end of this topic.</span></span>  
  
|<span data-ttu-id="a5a80-107">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="a5a80-107">Restriction Name</span></span>|<span data-ttu-id="a5a80-108">Parametername</span><span class="sxs-lookup"><span data-stu-id="a5a80-108">Parameter Name</span></span>|<span data-ttu-id="a5a80-109">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="a5a80-109">Restriction Default</span></span>|<span data-ttu-id="a5a80-110">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="a5a80-110">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a5a80-111">Catalog</span><span class="sxs-lookup"><span data-stu-id="a5a80-111">Catalog</span></span>|@Catalog|<span data-ttu-id="a5a80-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a5a80-112">TABLE_CATALOG</span></span>|<span data-ttu-id="a5a80-113">1</span><span class="sxs-lookup"><span data-stu-id="a5a80-113">1</span></span>|  
|<span data-ttu-id="a5a80-114">Besitzer</span><span class="sxs-lookup"><span data-stu-id="a5a80-114">Owner</span></span>|@Owner|<span data-ttu-id="a5a80-115">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a5a80-115">TABLE_SCHEMA</span></span>|<span data-ttu-id="a5a80-116">2</span><span class="sxs-lookup"><span data-stu-id="a5a80-116">2</span></span>|  
|<span data-ttu-id="a5a80-117">Tabelle</span><span class="sxs-lookup"><span data-stu-id="a5a80-117">Table</span></span>|@Name|<span data-ttu-id="a5a80-118">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="a5a80-118">TABLE_NAME</span></span>|<span data-ttu-id="a5a80-119">3</span><span class="sxs-lookup"><span data-stu-id="a5a80-119">3</span></span>|  
|<span data-ttu-id="a5a80-120">TableType</span><span class="sxs-lookup"><span data-stu-id="a5a80-120">TableType</span></span>|@TableType|<span data-ttu-id="a5a80-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="a5a80-121">TABLE_TYPE</span></span>|<span data-ttu-id="a5a80-122">4</span><span class="sxs-lookup"><span data-stu-id="a5a80-122">4</span></span>|  
  
## <a name="specifying-restriction-values"></a><span data-ttu-id="a5a80-123">Angeben der Einschränkungswerte</span><span class="sxs-lookup"><span data-stu-id="a5a80-123">Specifying Restriction Values</span></span>  
 <span data-ttu-id="a5a80-124">Wenn Sie eine der Einschränkungen der Tables-Schemaauflistung verwenden möchten, erstellen Sie ein Zeichenfolgenarray mit vier Elementen und fügen einen Wert in das Element ein, das mit der Einschränkungsnummer übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="a5a80-124">To use one of the restrictions of the "Tables" schema collection, simply create an array of strings with four elements, then place a value in the element that matches the restriction number.</span></span> <span data-ttu-id="a5a80-125">Z. B. zum Einschränken der in den Tabellen zurückgegeben, durch die **GetSchema** Methode, um nur die Tabellen im Schema "Umsatz" legen Sie das zweite Element des Arrays, das "Sales" vor der Übergabe an die **GetSchema** Methode.</span><span class="sxs-lookup"><span data-stu-id="a5a80-125">For example, to restrict the tables returned by the **GetSchema** method to only those tables in the "Sales" schema, set the second element of the array to "Sales" before passing it to the **GetSchema** method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a5a80-126">Die Einschränkungsauflistungen für den `SqlClient` und den `OracleClient` verfügen über eine zusätzliche `ParameterName`-Spalte.</span><span class="sxs-lookup"><span data-stu-id="a5a80-126">The restrictions collections for `SqlClient` and `OracleClient` have an additional `ParameterName` column.</span></span> <span data-ttu-id="a5a80-127">Die Spalte für den Einschränkungsstandard ist zwar aus Gründen der Abwärtskompatibilität vorhanden, wird aber derzeit ignoriert.</span><span class="sxs-lookup"><span data-stu-id="a5a80-127">The restriction default column is still there for backwards compatibility, but is currently ignored.</span></span> <span data-ttu-id="a5a80-128">Verwenden Sie Abfragen mit Parametern statt Zeichenfolgenersetzungen, um das Risiko eines SQL-Injection-Angriffs beim Angeben der Einschränkungswerte zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="a5a80-128">Parameterized queries rather than string replacement should be used to minimize the risk of an SQL injection attack when specifying restriction values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a5a80-129">Die Anzahl der Elementen im Array muss kleiner oder gleich der Anzahl der Einschränkungen sein, die für die angegebene Schemaauflistung unterstützt werden, da sonst eine <xref:System.ArgumentException> ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="a5a80-129">The number of elements in the array must be less than or equal to the number of restrictions supported for the specified schema collection else an <xref:System.ArgumentException> will be thrown.</span></span> <span data-ttu-id="a5a80-130">Es können weniger Elemente als die maximale Anzahl der Einschränkungen vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="a5a80-130">There can be fewer than the maximum number of restrictions.</span></span> <span data-ttu-id="a5a80-131">Es wird davon ausgegangen, dass die fehlenden Einschränkungen NULL (uneingeschränkt) sind.</span><span class="sxs-lookup"><span data-stu-id="a5a80-131">The missing restrictions are assumed to be null (unrestricted).</span></span>  
  
 <span data-ttu-id="a5a80-132">Sie können einen verwalteten .NET Framework-Anbieter, um die Liste der unterstützten Einschränkungen durch den Aufruf zu bestimmen, Abfragen der **GetSchema** Methode durch den Namen der schemaauflistung der Einschränkungen, die "Restrictions" lautet.</span><span class="sxs-lookup"><span data-stu-id="a5a80-132">You can query a .NET Framework managed provider to determine the list of supported restrictions by calling the **GetSchema** method with the name of the restrictions schema collection, which is "Restrictions".</span></span> <span data-ttu-id="a5a80-133">Dabei wird eine <xref:System.Data.DataTable> mit einer Liste der Auflistungsnamen, Einschränkungsnamen, Standardeinschränkungswerte und der Anzahl der Einschränkungen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a5a80-133">This will return a <xref:System.Data.DataTable> with a list of the collection names, the restriction names, the default restriction values, and the restriction numbers.</span></span>  
  
### <a name="example"></a><span data-ttu-id="a5a80-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a5a80-134">Example</span></span>  
 <span data-ttu-id="a5a80-135">Die folgenden Beispiele veranschaulichen, wie Sie mit der <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> Methode von der .NET Framework-Datenanbieter für SQL Server <xref:System.Data.SqlClient.SqlConnection> -Klasse zum Abrufen von Schemainformationen zu allen enthaltenen Tabellen die **AdventureWorks**Beispieldatenbank und zum Einschränken der Informationen, die an die Tabellen im "Sales"-Schema zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="a5a80-135">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database, and to restrict the information returned to only those tables in the "Sales" schema:</span></span>  
  
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
  
## <a name="sql-server-schema-restrictions"></a><span data-ttu-id="a5a80-136">SQL Server-Schemabeschränkungen</span><span class="sxs-lookup"><span data-stu-id="a5a80-136">SQL Server Schema Restrictions</span></span>  
 <span data-ttu-id="a5a80-137">In den folgenden Tabellen sind die Beschränkungen für SQL Server-Schemaauflistungen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="a5a80-137">The following tables list the restrictions for SQL Server schema collections.</span></span>  
  
### <a name="users"></a><span data-ttu-id="a5a80-138">Benutzer</span><span class="sxs-lookup"><span data-stu-id="a5a80-138">Users</span></span>  
  
|<span data-ttu-id="a5a80-139">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="a5a80-139">Restriction Name</span></span>|<span data-ttu-id="a5a80-140">Parametername</span><span class="sxs-lookup"><span data-stu-id="a5a80-140">Parameter Name</span></span>|<span data-ttu-id="a5a80-141">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="a5a80-141">Restriction Default</span></span>|<span data-ttu-id="a5a80-142">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="a5a80-142">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a5a80-143">User_Name</span><span class="sxs-lookup"><span data-stu-id="a5a80-143">User_Name</span></span>|@Name|<span data-ttu-id="a5a80-144">Name</span><span class="sxs-lookup"><span data-stu-id="a5a80-144">name</span></span>|<span data-ttu-id="a5a80-145">1</span><span class="sxs-lookup"><span data-stu-id="a5a80-145">1</span></span>|  
  
### <a name="databases"></a><span data-ttu-id="a5a80-146">Databases</span><span class="sxs-lookup"><span data-stu-id="a5a80-146">Databases</span></span>  
  
|<span data-ttu-id="a5a80-147">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="a5a80-147">Restriction Name</span></span>|<span data-ttu-id="a5a80-148">Parametername</span><span class="sxs-lookup"><span data-stu-id="a5a80-148">Parameter Name</span></span>|<span data-ttu-id="a5a80-149">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="a5a80-149">Restriction Default</span></span>|<span data-ttu-id="a5a80-150">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="a5a80-150">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a5a80-151">name</span><span class="sxs-lookup"><span data-stu-id="a5a80-151">Name</span></span>|@Name|<span data-ttu-id="a5a80-152">name</span><span class="sxs-lookup"><span data-stu-id="a5a80-152">Name</span></span>|<span data-ttu-id="a5a80-153">1</span><span class="sxs-lookup"><span data-stu-id="a5a80-153">1</span></span>|  
  
### <a name="tables"></a><span data-ttu-id="a5a80-154">Tabellen</span><span class="sxs-lookup"><span data-stu-id="a5a80-154">Tables</span></span>  
  
|<span data-ttu-id="a5a80-155">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="a5a80-155">Restriction Name</span></span>|<span data-ttu-id="a5a80-156">Parametername</span><span class="sxs-lookup"><span data-stu-id="a5a80-156">Parameter Name</span></span>|<span data-ttu-id="a5a80-157">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="a5a80-157">Restriction Default</span></span>|<span data-ttu-id="a5a80-158">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="a5a80-158">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a5a80-159">Catalog</span><span class="sxs-lookup"><span data-stu-id="a5a80-159">Catalog</span></span>|@Catalog|<span data-ttu-id="a5a80-160">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a5a80-160">TABLE_CATALOG</span></span>|<span data-ttu-id="a5a80-161">1</span><span class="sxs-lookup"><span data-stu-id="a5a80-161">1</span></span>|  
|<span data-ttu-id="a5a80-162">Besitzer</span><span class="sxs-lookup"><span data-stu-id="a5a80-162">Owner</span></span>|@Owner|<span data-ttu-id="a5a80-163">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a5a80-163">TABLE_SCHEMA</span></span>|<span data-ttu-id="a5a80-164">2</span><span class="sxs-lookup"><span data-stu-id="a5a80-164">2</span></span>|  
|<span data-ttu-id="a5a80-165">Tabelle</span><span class="sxs-lookup"><span data-stu-id="a5a80-165">Table</span></span>|@Name|<span data-ttu-id="a5a80-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="a5a80-166">TABLE_NAME</span></span>|<span data-ttu-id="a5a80-167">3</span><span class="sxs-lookup"><span data-stu-id="a5a80-167">3</span></span>|  
|<span data-ttu-id="a5a80-168">TableType</span><span class="sxs-lookup"><span data-stu-id="a5a80-168">TableType</span></span>|@TableType|<span data-ttu-id="a5a80-169">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="a5a80-169">TABLE_TYPE</span></span>|<span data-ttu-id="a5a80-170">4</span><span class="sxs-lookup"><span data-stu-id="a5a80-170">4</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="a5a80-171">Columns</span><span class="sxs-lookup"><span data-stu-id="a5a80-171">Columns</span></span>  
  
|<span data-ttu-id="a5a80-172">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="a5a80-172">Restriction Name</span></span>|<span data-ttu-id="a5a80-173">Parametername</span><span class="sxs-lookup"><span data-stu-id="a5a80-173">Parameter Name</span></span>|<span data-ttu-id="a5a80-174">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="a5a80-174">Restriction Default</span></span>|<span data-ttu-id="a5a80-175">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="a5a80-175">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a5a80-176">Catalog</span><span class="sxs-lookup"><span data-stu-id="a5a80-176">Catalog</span></span>|@Catalog|<span data-ttu-id="a5a80-177">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a5a80-177">TABLE_CATALOG</span></span>|<span data-ttu-id="a5a80-178">1</span><span class="sxs-lookup"><span data-stu-id="a5a80-178">1</span></span>|  
|<span data-ttu-id="a5a80-179">Besitzer</span><span class="sxs-lookup"><span data-stu-id="a5a80-179">Owner</span></span>|@Owner|<span data-ttu-id="a5a80-180">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a5a80-180">TABLE_SCHEMA</span></span>|<span data-ttu-id="a5a80-181">2</span><span class="sxs-lookup"><span data-stu-id="a5a80-181">2</span></span>|  
|<span data-ttu-id="a5a80-182">Tabelle</span><span class="sxs-lookup"><span data-stu-id="a5a80-182">Table</span></span>|@Table|<span data-ttu-id="a5a80-183">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="a5a80-183">TABLE_NAME</span></span>|<span data-ttu-id="a5a80-184">3</span><span class="sxs-lookup"><span data-stu-id="a5a80-184">3</span></span>|  
|<span data-ttu-id="a5a80-185">Spalte</span><span class="sxs-lookup"><span data-stu-id="a5a80-185">Column</span></span>|@Column|<span data-ttu-id="a5a80-186">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="a5a80-186">COLUMN_NAME</span></span>|<span data-ttu-id="a5a80-187">4</span><span class="sxs-lookup"><span data-stu-id="a5a80-187">4</span></span>|  
  
### <a name="structuredtypemembers"></a><span data-ttu-id="a5a80-188">StructuredTypeMembers</span><span class="sxs-lookup"><span data-stu-id="a5a80-188">StructuredTypeMembers</span></span>  
  
|<span data-ttu-id="a5a80-189">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="a5a80-189">Restriction Name</span></span>|<span data-ttu-id="a5a80-190">Parametername</span><span class="sxs-lookup"><span data-stu-id="a5a80-190">Parameter Name</span></span>|<span data-ttu-id="a5a80-191">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="a5a80-191">Restriction Default</span></span>|<span data-ttu-id="a5a80-192">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="a5a80-192">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a5a80-193">Catalog</span><span class="sxs-lookup"><span data-stu-id="a5a80-193">Catalog</span></span>|@Catalog|<span data-ttu-id="a5a80-194">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a5a80-194">TABLE_CATALOG</span></span>|<span data-ttu-id="a5a80-195">1</span><span class="sxs-lookup"><span data-stu-id="a5a80-195">1</span></span>|  
|<span data-ttu-id="a5a80-196">Besitzer</span><span class="sxs-lookup"><span data-stu-id="a5a80-196">Owner</span></span>|@Owner|<span data-ttu-id="a5a80-197">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a5a80-197">TABLE_SCHEMA</span></span>|<span data-ttu-id="a5a80-198">2</span><span class="sxs-lookup"><span data-stu-id="a5a80-198">2</span></span>|  
|<span data-ttu-id="a5a80-199">Tabelle</span><span class="sxs-lookup"><span data-stu-id="a5a80-199">Table</span></span>|@Table|<span data-ttu-id="a5a80-200">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="a5a80-200">TABLE_NAME</span></span>|<span data-ttu-id="a5a80-201">3</span><span class="sxs-lookup"><span data-stu-id="a5a80-201">3</span></span>|  
|<span data-ttu-id="a5a80-202">Spalte</span><span class="sxs-lookup"><span data-stu-id="a5a80-202">Column</span></span>|@Column|<span data-ttu-id="a5a80-203">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="a5a80-203">COLUMN_NAME</span></span>|<span data-ttu-id="a5a80-204">4</span><span class="sxs-lookup"><span data-stu-id="a5a80-204">4</span></span>|  
  
### <a name="views"></a><span data-ttu-id="a5a80-205">Ansichten</span><span class="sxs-lookup"><span data-stu-id="a5a80-205">Views</span></span>  
  
|<span data-ttu-id="a5a80-206">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="a5a80-206">Restriction Name</span></span>|<span data-ttu-id="a5a80-207">Parametername</span><span class="sxs-lookup"><span data-stu-id="a5a80-207">Parameter Name</span></span>|<span data-ttu-id="a5a80-208">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="a5a80-208">Restriction Default</span></span>|<span data-ttu-id="a5a80-209">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="a5a80-209">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a5a80-210">Catalog</span><span class="sxs-lookup"><span data-stu-id="a5a80-210">Catalog</span></span>|@Catalog|<span data-ttu-id="a5a80-211">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a5a80-211">TABLE_CATALOG</span></span>|<span data-ttu-id="a5a80-212">1</span><span class="sxs-lookup"><span data-stu-id="a5a80-212">1</span></span>|  
|<span data-ttu-id="a5a80-213">Besitzer</span><span class="sxs-lookup"><span data-stu-id="a5a80-213">Owner</span></span>|@Owner|<span data-ttu-id="a5a80-214">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a5a80-214">TABLE_SCHEMA</span></span>|<span data-ttu-id="a5a80-215">2</span><span class="sxs-lookup"><span data-stu-id="a5a80-215">2</span></span>|  
|<span data-ttu-id="a5a80-216">Tabelle</span><span class="sxs-lookup"><span data-stu-id="a5a80-216">Table</span></span>|@Table|<span data-ttu-id="a5a80-217">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="a5a80-217">TABLE_NAME</span></span>|<span data-ttu-id="a5a80-218">3</span><span class="sxs-lookup"><span data-stu-id="a5a80-218">3</span></span>|  
  
### <a name="viewcolumns"></a><span data-ttu-id="a5a80-219">ViewColumns</span><span class="sxs-lookup"><span data-stu-id="a5a80-219">ViewColumns</span></span>  
  
|<span data-ttu-id="a5a80-220">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="a5a80-220">Restriction Name</span></span>|<span data-ttu-id="a5a80-221">Parametername</span><span class="sxs-lookup"><span data-stu-id="a5a80-221">Parameter Name</span></span>|<span data-ttu-id="a5a80-222">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="a5a80-222">Restriction Default</span></span>|<span data-ttu-id="a5a80-223">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="a5a80-223">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a5a80-224">Catalog</span><span class="sxs-lookup"><span data-stu-id="a5a80-224">Catalog</span></span>|@Catalog|<span data-ttu-id="a5a80-225">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a5a80-225">VIEW_CATALOG</span></span>|<span data-ttu-id="a5a80-226">1</span><span class="sxs-lookup"><span data-stu-id="a5a80-226">1</span></span>|  
|<span data-ttu-id="a5a80-227">Besitzer</span><span class="sxs-lookup"><span data-stu-id="a5a80-227">Owner</span></span>|@Owner|<span data-ttu-id="a5a80-228">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a5a80-228">VIEW_SCHEMA</span></span>|<span data-ttu-id="a5a80-229">2</span><span class="sxs-lookup"><span data-stu-id="a5a80-229">2</span></span>|  
|<span data-ttu-id="a5a80-230">Tabelle</span><span class="sxs-lookup"><span data-stu-id="a5a80-230">Table</span></span>|@Table|<span data-ttu-id="a5a80-231">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="a5a80-231">VIEW_NAME</span></span>|<span data-ttu-id="a5a80-232">3</span><span class="sxs-lookup"><span data-stu-id="a5a80-232">3</span></span>|  
|<span data-ttu-id="a5a80-233">Spalte</span><span class="sxs-lookup"><span data-stu-id="a5a80-233">Column</span></span>|@Column|<span data-ttu-id="a5a80-234">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="a5a80-234">COLUMN_NAME</span></span>|<span data-ttu-id="a5a80-235">4</span><span class="sxs-lookup"><span data-stu-id="a5a80-235">4</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="a5a80-236">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="a5a80-236">ProcedureParameters</span></span>  
  
|<span data-ttu-id="a5a80-237">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="a5a80-237">Restriction Name</span></span>|<span data-ttu-id="a5a80-238">Parametername</span><span class="sxs-lookup"><span data-stu-id="a5a80-238">Parameter Name</span></span>|<span data-ttu-id="a5a80-239">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="a5a80-239">Restriction Default</span></span>|<span data-ttu-id="a5a80-240">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="a5a80-240">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a5a80-241">Catalog</span><span class="sxs-lookup"><span data-stu-id="a5a80-241">Catalog</span></span>|@Catalog|<span data-ttu-id="a5a80-242">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a5a80-242">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="a5a80-243">1</span><span class="sxs-lookup"><span data-stu-id="a5a80-243">1</span></span>|  
|<span data-ttu-id="a5a80-244">Besitzer</span><span class="sxs-lookup"><span data-stu-id="a5a80-244">Owner</span></span>|@Owner|<span data-ttu-id="a5a80-245">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a5a80-245">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="a5a80-246">2</span><span class="sxs-lookup"><span data-stu-id="a5a80-246">2</span></span>|  
|<span data-ttu-id="a5a80-247">name</span><span class="sxs-lookup"><span data-stu-id="a5a80-247">Name</span></span>|@Name|<span data-ttu-id="a5a80-248">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="a5a80-248">SPECIFIC_NAME</span></span>|<span data-ttu-id="a5a80-249">3</span><span class="sxs-lookup"><span data-stu-id="a5a80-249">3</span></span>|  
|<span data-ttu-id="a5a80-250">Parameter</span><span class="sxs-lookup"><span data-stu-id="a5a80-250">Parameter</span></span>|@Parameter|<span data-ttu-id="a5a80-251">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="a5a80-251">PARAMETER_NAME</span></span>|<span data-ttu-id="a5a80-252">4</span><span class="sxs-lookup"><span data-stu-id="a5a80-252">4</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="a5a80-253">Verfahren</span><span class="sxs-lookup"><span data-stu-id="a5a80-253">Procedures</span></span>  
  
|<span data-ttu-id="a5a80-254">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="a5a80-254">Restriction Name</span></span>|<span data-ttu-id="a5a80-255">Parametername</span><span class="sxs-lookup"><span data-stu-id="a5a80-255">Parameter Name</span></span>|<span data-ttu-id="a5a80-256">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="a5a80-256">Restriction Default</span></span>|<span data-ttu-id="a5a80-257">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="a5a80-257">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a5a80-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="a5a80-258">Catalog</span></span>|@Catalog|<span data-ttu-id="a5a80-259">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a5a80-259">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="a5a80-260">1</span><span class="sxs-lookup"><span data-stu-id="a5a80-260">1</span></span>|  
|<span data-ttu-id="a5a80-261">Besitzer</span><span class="sxs-lookup"><span data-stu-id="a5a80-261">Owner</span></span>|@Owner|<span data-ttu-id="a5a80-262">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a5a80-262">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="a5a80-263">2</span><span class="sxs-lookup"><span data-stu-id="a5a80-263">2</span></span>|  
|<span data-ttu-id="a5a80-264">name</span><span class="sxs-lookup"><span data-stu-id="a5a80-264">Name</span></span>|@Name|<span data-ttu-id="a5a80-265">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="a5a80-265">SPECIFIC_NAME</span></span>|<span data-ttu-id="a5a80-266">3</span><span class="sxs-lookup"><span data-stu-id="a5a80-266">3</span></span>|  
|<span data-ttu-id="a5a80-267">Typ</span><span class="sxs-lookup"><span data-stu-id="a5a80-267">Type</span></span>|@Type|<span data-ttu-id="a5a80-268">ROUTINE_TYPE</span><span class="sxs-lookup"><span data-stu-id="a5a80-268">ROUTINE_TYPE</span></span>|<span data-ttu-id="a5a80-269">4</span><span class="sxs-lookup"><span data-stu-id="a5a80-269">4</span></span>|  
  
### <a name="indexcolumns"></a><span data-ttu-id="a5a80-270">IndexColumns</span><span class="sxs-lookup"><span data-stu-id="a5a80-270">IndexColumns</span></span>  
  
|<span data-ttu-id="a5a80-271">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="a5a80-271">Restriction Name</span></span>|<span data-ttu-id="a5a80-272">Parametername</span><span class="sxs-lookup"><span data-stu-id="a5a80-272">Parameter Name</span></span>|<span data-ttu-id="a5a80-273">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="a5a80-273">Restriction Default</span></span>|<span data-ttu-id="a5a80-274">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="a5a80-274">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a5a80-275">Catalog</span><span class="sxs-lookup"><span data-stu-id="a5a80-275">Catalog</span></span>|@Catalog|<span data-ttu-id="a5a80-276">db_name()</span><span class="sxs-lookup"><span data-stu-id="a5a80-276">db_name()</span></span>|<span data-ttu-id="a5a80-277">1</span><span class="sxs-lookup"><span data-stu-id="a5a80-277">1</span></span>|  
|<span data-ttu-id="a5a80-278">Besitzer</span><span class="sxs-lookup"><span data-stu-id="a5a80-278">Owner</span></span>|@Owner|<span data-ttu-id="a5a80-279">user_name()</span><span class="sxs-lookup"><span data-stu-id="a5a80-279">user_name()</span></span>|<span data-ttu-id="a5a80-280">2</span><span class="sxs-lookup"><span data-stu-id="a5a80-280">2</span></span>|  
|<span data-ttu-id="a5a80-281">Tabelle</span><span class="sxs-lookup"><span data-stu-id="a5a80-281">Table</span></span>|@Table|<span data-ttu-id="a5a80-282">o.name</span><span class="sxs-lookup"><span data-stu-id="a5a80-282">o.name</span></span>|<span data-ttu-id="a5a80-283">3</span><span class="sxs-lookup"><span data-stu-id="a5a80-283">3</span></span>|  
|<span data-ttu-id="a5a80-284">ConstraintName</span><span class="sxs-lookup"><span data-stu-id="a5a80-284">ConstraintName</span></span>|@ConstraintName|<span data-ttu-id="a5a80-285">x.name</span><span class="sxs-lookup"><span data-stu-id="a5a80-285">x.name</span></span>|<span data-ttu-id="a5a80-286">4</span><span class="sxs-lookup"><span data-stu-id="a5a80-286">4</span></span>|  
|<span data-ttu-id="a5a80-287">Spalte</span><span class="sxs-lookup"><span data-stu-id="a5a80-287">Column</span></span>|@Column|<span data-ttu-id="a5a80-288">c.name</span><span class="sxs-lookup"><span data-stu-id="a5a80-288">c.name</span></span>|<span data-ttu-id="a5a80-289">5</span><span class="sxs-lookup"><span data-stu-id="a5a80-289">5</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="a5a80-290">Indexes</span><span class="sxs-lookup"><span data-stu-id="a5a80-290">Indexes</span></span>  
  
|<span data-ttu-id="a5a80-291">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="a5a80-291">Restriction Name</span></span>|<span data-ttu-id="a5a80-292">Parametername</span><span class="sxs-lookup"><span data-stu-id="a5a80-292">Parameter Name</span></span>|<span data-ttu-id="a5a80-293">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="a5a80-293">Restriction Default</span></span>|<span data-ttu-id="a5a80-294">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="a5a80-294">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a5a80-295">Catalog</span><span class="sxs-lookup"><span data-stu-id="a5a80-295">Catalog</span></span>|@Catalog|<span data-ttu-id="a5a80-296">db_name()</span><span class="sxs-lookup"><span data-stu-id="a5a80-296">db_name()</span></span>|<span data-ttu-id="a5a80-297">1</span><span class="sxs-lookup"><span data-stu-id="a5a80-297">1</span></span>|  
|<span data-ttu-id="a5a80-298">Besitzer</span><span class="sxs-lookup"><span data-stu-id="a5a80-298">Owner</span></span>|@Owner|<span data-ttu-id="a5a80-299">user_name()</span><span class="sxs-lookup"><span data-stu-id="a5a80-299">user_name()</span></span>|<span data-ttu-id="a5a80-300">2</span><span class="sxs-lookup"><span data-stu-id="a5a80-300">2</span></span>|  
|<span data-ttu-id="a5a80-301">Tabelle</span><span class="sxs-lookup"><span data-stu-id="a5a80-301">Table</span></span>|@Table|<span data-ttu-id="a5a80-302">o.name</span><span class="sxs-lookup"><span data-stu-id="a5a80-302">o.name</span></span>|<span data-ttu-id="a5a80-303">3</span><span class="sxs-lookup"><span data-stu-id="a5a80-303">3</span></span>|  
  
### <a name="userdefinedtypes"></a><span data-ttu-id="a5a80-304">UserDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="a5a80-304">UserDefinedTypes</span></span>  
  
|<span data-ttu-id="a5a80-305">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="a5a80-305">Restriction Name</span></span>|<span data-ttu-id="a5a80-306">Parametername</span><span class="sxs-lookup"><span data-stu-id="a5a80-306">Parameter Name</span></span>|<span data-ttu-id="a5a80-307">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="a5a80-307">Restriction Default</span></span>|<span data-ttu-id="a5a80-308">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="a5a80-308">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a5a80-309">assembly_name</span><span class="sxs-lookup"><span data-stu-id="a5a80-309">assembly_name</span></span>|@AssemblyName|<span data-ttu-id="a5a80-310">assemblies.name</span><span class="sxs-lookup"><span data-stu-id="a5a80-310">assemblies.name</span></span>|<span data-ttu-id="a5a80-311">1</span><span class="sxs-lookup"><span data-stu-id="a5a80-311">1</span></span>|  
|<span data-ttu-id="a5a80-312">udt_name</span><span class="sxs-lookup"><span data-stu-id="a5a80-312">udt_name</span></span>|@UDTName|<span data-ttu-id="a5a80-313">types.assembly_class</span><span class="sxs-lookup"><span data-stu-id="a5a80-313">types.assembly_class</span></span>|<span data-ttu-id="a5a80-314">2</span><span class="sxs-lookup"><span data-stu-id="a5a80-314">2</span></span>|  
  
### <a name="foreignkeys"></a><span data-ttu-id="a5a80-315">ForeignKeys</span><span class="sxs-lookup"><span data-stu-id="a5a80-315">ForeignKeys</span></span>  
  
|<span data-ttu-id="a5a80-316">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="a5a80-316">Restriction Name</span></span>|<span data-ttu-id="a5a80-317">Parametername</span><span class="sxs-lookup"><span data-stu-id="a5a80-317">Parameter Name</span></span>|<span data-ttu-id="a5a80-318">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="a5a80-318">Restriction Default</span></span>|<span data-ttu-id="a5a80-319">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="a5a80-319">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a5a80-320">Catalog</span><span class="sxs-lookup"><span data-stu-id="a5a80-320">Catalog</span></span>|@Catalog|<span data-ttu-id="a5a80-321">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a5a80-321">CONSTRAINT_CATALOG</span></span>|<span data-ttu-id="a5a80-322">1</span><span class="sxs-lookup"><span data-stu-id="a5a80-322">1</span></span>|  
|<span data-ttu-id="a5a80-323">Besitzer</span><span class="sxs-lookup"><span data-stu-id="a5a80-323">Owner</span></span>|@Owner|<span data-ttu-id="a5a80-324">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a5a80-324">CONSTRAINT_SCHEMA</span></span>|<span data-ttu-id="a5a80-325">2</span><span class="sxs-lookup"><span data-stu-id="a5a80-325">2</span></span>|  
|<span data-ttu-id="a5a80-326">Tabelle</span><span class="sxs-lookup"><span data-stu-id="a5a80-326">Table</span></span>|@Table|<span data-ttu-id="a5a80-327">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="a5a80-327">TABLE_NAME</span></span>|<span data-ttu-id="a5a80-328">3</span><span class="sxs-lookup"><span data-stu-id="a5a80-328">3</span></span>|  
|<span data-ttu-id="a5a80-329">name</span><span class="sxs-lookup"><span data-stu-id="a5a80-329">Name</span></span>|@Name|<span data-ttu-id="a5a80-330">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="a5a80-330">CONSTRAINT_NAME</span></span>|<span data-ttu-id="a5a80-331">4</span><span class="sxs-lookup"><span data-stu-id="a5a80-331">4</span></span>|  
  
## <a name="sql-server-2008-schema-restrictions"></a><span data-ttu-id="a5a80-332">SQL Server 2008-Schemabeschränkungen</span><span class="sxs-lookup"><span data-stu-id="a5a80-332">SQL Server 2008 Schema Restrictions</span></span>  
 <span data-ttu-id="a5a80-333">In den folgenden Tabellen sind die Beschränkungen für SQL Server 2008-Schemaauflistungen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="a5a80-333">The following tables list the restrictions for SQL Server 2008 schema collections.</span></span> <span data-ttu-id="a5a80-334">Diese Beschränkungen gelten ab Version 3.5 SP1 von .NET Framework und SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="a5a80-334">These restrictions are valid beginning with version 3.5 SP1 of the .NET Framework and SQL Server 2008.</span></span> <span data-ttu-id="a5a80-335">Sie werden in früheren Versionen von .NET Framework und SQL Server nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a5a80-335">They are not supported in earlier versions of the .NET Framework and SQL Server.</span></span>  
  
### <a name="columnsetcolumns"></a><span data-ttu-id="a5a80-336">ColumnSetColumns</span><span class="sxs-lookup"><span data-stu-id="a5a80-336">ColumnSetColumns</span></span>  
  
|<span data-ttu-id="a5a80-337">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="a5a80-337">Restriction Name</span></span>|<span data-ttu-id="a5a80-338">Parametername</span><span class="sxs-lookup"><span data-stu-id="a5a80-338">Parameter Name</span></span>|<span data-ttu-id="a5a80-339">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="a5a80-339">Restriction Default</span></span>|<span data-ttu-id="a5a80-340">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="a5a80-340">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a5a80-341">Catalog</span><span class="sxs-lookup"><span data-stu-id="a5a80-341">Catalog</span></span>|@Catalog|<span data-ttu-id="a5a80-342">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a5a80-342">TABLE_CATALOG</span></span>|<span data-ttu-id="a5a80-343">1</span><span class="sxs-lookup"><span data-stu-id="a5a80-343">1</span></span>|  
|<span data-ttu-id="a5a80-344">Besitzer</span><span class="sxs-lookup"><span data-stu-id="a5a80-344">Owner</span></span>|@Owner|<span data-ttu-id="a5a80-345">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a5a80-345">TABLE_SCHEMA</span></span>|<span data-ttu-id="a5a80-346">2</span><span class="sxs-lookup"><span data-stu-id="a5a80-346">2</span></span>|  
|<span data-ttu-id="a5a80-347">Tabelle</span><span class="sxs-lookup"><span data-stu-id="a5a80-347">Table</span></span>|@Table|<span data-ttu-id="a5a80-348">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="a5a80-348">TABLE_NAME</span></span>|<span data-ttu-id="a5a80-349">3</span><span class="sxs-lookup"><span data-stu-id="a5a80-349">3</span></span>|  
  
### <a name="allcolumns"></a><span data-ttu-id="a5a80-350">AllColumns</span><span class="sxs-lookup"><span data-stu-id="a5a80-350">AllColumns</span></span>  
  
|<span data-ttu-id="a5a80-351">Einschränkungsname</span><span class="sxs-lookup"><span data-stu-id="a5a80-351">Restriction Name</span></span>|<span data-ttu-id="a5a80-352">Parametername</span><span class="sxs-lookup"><span data-stu-id="a5a80-352">Parameter Name</span></span>|<span data-ttu-id="a5a80-353">Einschränkungsstandard</span><span class="sxs-lookup"><span data-stu-id="a5a80-353">Restriction Default</span></span>|<span data-ttu-id="a5a80-354">Einschränkungsnummer</span><span class="sxs-lookup"><span data-stu-id="a5a80-354">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a5a80-355">Catalog</span><span class="sxs-lookup"><span data-stu-id="a5a80-355">Catalog</span></span>|@Catalog|<span data-ttu-id="a5a80-356">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a5a80-356">TABLE_CATALOG</span></span>|<span data-ttu-id="a5a80-357">1</span><span class="sxs-lookup"><span data-stu-id="a5a80-357">1</span></span>|  
|<span data-ttu-id="a5a80-358">Besitzer</span><span class="sxs-lookup"><span data-stu-id="a5a80-358">Owner</span></span>|@Owner|<span data-ttu-id="a5a80-359">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a5a80-359">TABLE_SCHEMA</span></span>|<span data-ttu-id="a5a80-360">2</span><span class="sxs-lookup"><span data-stu-id="a5a80-360">2</span></span>|  
|<span data-ttu-id="a5a80-361">Tabelle</span><span class="sxs-lookup"><span data-stu-id="a5a80-361">Table</span></span>|@Table|<span data-ttu-id="a5a80-362">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="a5a80-362">TABLE_NAME</span></span>|<span data-ttu-id="a5a80-363">3</span><span class="sxs-lookup"><span data-stu-id="a5a80-363">3</span></span>|  
|<span data-ttu-id="a5a80-364">Spalte</span><span class="sxs-lookup"><span data-stu-id="a5a80-364">Column</span></span>|@Column|<span data-ttu-id="a5a80-365">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="a5a80-365">COLUMN_NAME</span></span>|<span data-ttu-id="a5a80-366">4</span><span class="sxs-lookup"><span data-stu-id="a5a80-366">4</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a5a80-367">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a5a80-367">See Also</span></span>  
 [<span data-ttu-id="a5a80-368">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="a5a80-368">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
