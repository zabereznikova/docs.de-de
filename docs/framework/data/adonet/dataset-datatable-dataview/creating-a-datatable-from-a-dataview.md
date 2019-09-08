---
title: Erstellen einer "DataTable" aus einer "DataView"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2d45cf41-d8ae-4409-af3e-a96a7e476d85
ms.openlocfilehash: 6e066bcbe02fa9cf498e11af431b9f6dcd4432ab
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785515"
---
# <a name="creating-a-datatable-from-a-dataview"></a><span data-ttu-id="c25ca-102">Erstellen einer "DataTable" aus einer "DataView"</span><span class="sxs-lookup"><span data-stu-id="c25ca-102">Creating a DataTable from a DataView</span></span>
<span data-ttu-id="c25ca-103">Nachdem Sie Daten aus einer Datenquelle abgerufen und eine <xref:System.Data.DataTable> mit Daten gefüllt haben, möchten Sie die zurückgegebenen Daten möglicherweise sortieren, filtern oder anderweitig einschränken, ohne sie erneut abrufen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="c25ca-103">Once you have retrieved data from a data source, and have filled a <xref:System.Data.DataTable> with the data, you may want to sort, filter, or otherwise limit the returned data without retrieving it again.</span></span> <span data-ttu-id="c25ca-104">Dies wird durch die <xref:System.Data.DataView>-Klasse ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="c25ca-104">The <xref:System.Data.DataView> class makes this possible.</span></span> <span data-ttu-id="c25ca-105">Wenn <xref:System.Data.DataTable> Sie ein neues aus der <xref:System.Data.DataView>erstellen müssen, können Sie außerdem die <xref:System.Data.DataView.ToTable%2A> -Methode verwenden, um alle Zeilen und Spalten oder eine Teilmenge der Daten in eine neue <xref:System.Data.DataTable>zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="c25ca-105">In addition, if you need to create a new <xref:System.Data.DataTable> from the <xref:System.Data.DataView>, you can use the <xref:System.Data.DataView.ToTable%2A> method to copy all the rows and columns, or a subset of the data into a new <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="c25ca-106">Die <xref:System.Data.DataView.ToTable%2A>-Methode stellt Überladungen für folgende Vorgänge bereit:</span><span class="sxs-lookup"><span data-stu-id="c25ca-106">The <xref:System.Data.DataView.ToTable%2A> method provides overloads to:</span></span>  
  
- <span data-ttu-id="c25ca-107">Erstellen einer <xref:System.Data.DataTable>, die Spalten enthält, bei denen es sich um eine Teilmenge der Spalten in der <xref:System.Data.DataView> handelt.</span><span class="sxs-lookup"><span data-stu-id="c25ca-107">Create a <xref:System.Data.DataTable> containing columns that are a subset of the columns in the <xref:System.Data.DataView>.</span></span>  
  
- <span data-ttu-id="c25ca-108">Erstellen Sie <xref:System.Data.DataTable> einen, der nur eindeutige Zeilen aus <xref:System.Data.DataView>dem enthält, analog zum eindeutigen Schlüsselwort in Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="c25ca-108">Create a <xref:System.Data.DataTable> that includes only distinct rows from the <xref:System.Data.DataView>, analogously to the DISTINCT keyword in Transact-SQL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c25ca-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c25ca-109">Example</span></span>  
 <span data-ttu-id="c25ca-110">Im folgenden Beispiel für eine Konsolenanwendung <xref:System.Data.DataTable> wird eine erstellt, die Daten aus der **Person. Contact** -Tabelle in der **AdventureWorks** -Beispieldatenbank enthält.</span><span class="sxs-lookup"><span data-stu-id="c25ca-110">The following console application example creates a <xref:System.Data.DataTable> that contains data from the **Person.Contact** table in the **AdventureWorks** sample database.</span></span> <span data-ttu-id="c25ca-111">Im folgenden Beispiel wird ein sortiertes und gefiltertes <xref:System.Data.DataView> erstellt, das auf dem <xref:System.Data.DataTable>basiert.</span><span class="sxs-lookup"><span data-stu-id="c25ca-111">Next, the example creates a sorted and filtered <xref:System.Data.DataView> based on the <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="c25ca-112">Nachdem der <xref:System.Data.DataTable> Inhalt von <xref:System.Data.DataView>und angezeigt wurde, erstellt das Beispiel eine neue <xref:System.Data.DataTable> aus der <xref:System.Data.DataView> durch Aufrufen der <xref:System.Data.DataView.ToTable%2A> -Methode, die nur eine Teilmenge der verfügbaren Spalten auswählt.</span><span class="sxs-lookup"><span data-stu-id="c25ca-112">After displaying the contents of the <xref:System.Data.DataTable> and the <xref:System.Data.DataView>, the example creates a new <xref:System.Data.DataTable> from the <xref:System.Data.DataView> by calling the <xref:System.Data.DataView.ToTable%2A> method, selecting only a subset of the available columns.</span></span> <span data-ttu-id="c25ca-113">Zum Schluss werden im Beispiel die Inhalte der neuen <xref:System.Data.DataTable> angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c25ca-113">Finally, the example displays the contents of the new <xref:System.Data.DataTable>.</span></span>  
  
```vb  
Private Sub DemonstrateDataView()  
    ' Retrieve a DataTable from the AdventureWorks sample database.  
    ' connectionString is assumed to be a valid connection string.  
    Dim adapter As New SqlDataAdapter( _  
       "SELECT FirstName, LastName, EmailAddress FROM Person.Contact WHERE FirstName LIKE 'Mich%'", connectionString)  
    Dim table As New DataTable  
  
    adapter.Fill(table)  
    Console.WriteLine("Original table name: " & table.TableName)  
    ' Print current table values.  
    PrintTableOrView(table, "Current Values in Table")  
  
    ' Now create a DataView based on the DataTable.  
    ' Sort and filter the data.  
    Dim view As DataView = table.DefaultView  
    view.Sort = "LastName, FirstName"  
    view.RowFilter = "LastName > 'M'"  
    PrintTableOrView(view, "Current Values in View")  
  
    ' Create a new DataTable based on the DataView,  
    ' requesting only two columns with distinct values  
    ' in the columns.  
    Dim newTable As DataTable = view.ToTable("UniqueLastNames", True, "FirstName", "LastName")  
    PrintTableOrView(newTable, "Table created from DataView")  
    Console.WriteLine("New table name: " & newTable.TableName)  
  
    Console.WriteLine("Press any key to continue.")  
    Console.ReadKey()  
    End Sub  
  
Private Sub PrintTableOrView(ByVal dv As DataView, ByVal label As String)  
    Dim sw As System.IO.StringWriter  
    Dim output As String  
    Dim table As DataTable = dv.Table  
  
    Console.WriteLine(label)  
  
    ' Loop through each row in the view.  
    For Each rowView As DataRowView In dv  
        sw = New System.IO.StringWriter  
  
        ' Loop through each column.  
        For Each col As DataColumn In table.Columns  
            ' Output the value of each column's data.  
            sw.Write(rowView(col.ColumnName).ToString() & ", ")  
        Next  
        output = sw.ToString  
        ' Trim off the trailing ", ", so the output looks correct.  
        If output.Length > 2 Then  
            output = output.Substring(0, output.Length - 2)  
        End If  
        ' Display the row in the console window.  
        Console.WriteLine(output)  
    Next  
    Console.WriteLine()  
End Sub  
  
Private Sub PrintTableOrView(ByVal table As DataTable, ByVal label As String)  
    Dim sw As System.IO.StringWriter  
    Dim output As String  
  
    Console.WriteLine(label)  
  
    ' Loop through each row in the table.  
    For Each row As DataRow In table.Rows  
        sw = New System.IO.StringWriter  
        ' Loop through each column.  
        For Each col As DataColumn In table.Columns  
            ' Output the value of each column's data.  
            sw.Write(row(col).ToString() & ", ")  
        Next  
        output = sw.ToString  
        ' Trim off the trailing ", ", so the output looks correct.  
        If output.Length > 2 Then  
            output = output.Substring(0, output.Length - 2)  
        End If  
        ' Display the row in the console window.  
        Console.WriteLine(output)  
    Next  
    Console.WriteLine()  
    End Sub  
End Module  
```  
  
```csharp  
private static void DemonstrateDataView()  
{  
// Retrieve a DataTable from the AdventureWorks sample database.  
// connectionString is assumed to be a valid connection string.  
SqlDataAdapter adapter = new SqlDataAdapter(  
    "SELECT FirstName, LastName, EmailAddress " +  
    "FROM Person.Contact WHERE FirstName LIKE 'Mich%'",   
       GetConnectionString());  
DataTable table = new DataTable();  
  
adapter.Fill(table);  
Console.WriteLine("Original table name: " + table.TableName);  
// Print current table values.  
PrintTableOrView(table, "Current Values in Table");  
  
// Now create a DataView based on the DataTable.  
// Sort and filter the data.  
DataView view = table.DefaultView;  
view.Sort = "LastName, FirstName";  
view.RowFilter = "LastName > 'M'";  
PrintTableOrView(view, "Current Values in View");  
  
// Create a new DataTable based on the DataView,  
// requesting only two columns with distinct values  
// in the columns.  
DataTable newTable = view.ToTable("UniqueLastNames",  
     true, "FirstName", "LastName");  
PrintTableOrView(newTable, "Table created from DataView");  
Console.WriteLine("New table name: " + newTable.TableName);  
  
Console.WriteLine("Press any key to continue.");  
Console.ReadKey();  
}  
  
private static void PrintTableOrView(DataView dv, string label)  
{  
System.IO.StringWriter sw;  
string output;  
DataTable table = dv.Table;  
  
Console.WriteLine(label);  
  
// Loop through each row in the view.  
foreach (DataRowView rowView in dv)  
{  
    sw = new System.IO.StringWriter();  
  
    // Loop through each column.  
    foreach (DataColumn col in table.Columns)  
    {  
        // Output the value of each column's data.  
        sw.Write(rowView[col.ColumnName].ToString() + ", ");  
    }  
    output = sw.ToString();  
    // Trim off the trailing ", ", so the output looks correct.  
    if (output.Length > 2)  
    {  
        output = output.Substring(0, output.Length - 2);  
    }  
    // Display the row in the console window.  
    Console.WriteLine(output);  
}  
Console.WriteLine();  
}  
  
private static void PrintTableOrView(DataTable table, string label)  
{  
System.IO.StringWriter sw;  
string output;  
  
Console.WriteLine(label);  
  
// Loop through each row in the table.  
foreach (DataRow row in table.Rows)  
{  
    sw = new System.IO.StringWriter();  
    // Loop through each column.  
    foreach (DataColumn col in table.Columns)  
    {  
        // Output the value of each column's data.  
        sw.Write(row[col].ToString() + ", ");  
    }  
    output = sw.ToString();  
    // Trim off the trailing ", ", so the output looks correct.  
    if (output.Length > 2)  
    {  
        output = output.Substring(0, output.Length - 2);  
    }  
    // Display the row in the console window.  
    Console.WriteLine(output);  
} //  
Console.WriteLine();  
}  
```  
  
 <span data-ttu-id="c25ca-114">}</span><span class="sxs-lookup"><span data-stu-id="c25ca-114">}</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c25ca-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c25ca-115">See also</span></span>

- <xref:System.Data.DataView.ToTable%2A>
- [<span data-ttu-id="c25ca-116">DataViews</span><span class="sxs-lookup"><span data-stu-id="c25ca-116">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="c25ca-117">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c25ca-117">ADO.NET Overview</span></span>](../ado-net-overview.md)
