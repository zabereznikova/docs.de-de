---
title: Einfügen eines Bilds aus einer Datei
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 35900aa2-5615-4174-8212-ba184c6b82fb
ms.openlocfilehash: f2bc67b4130633fba3a6e42e2b6925fc09f835c3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59116229"
---
# <a name="inserting-an-image-from-a-file"></a><span data-ttu-id="a11bb-102">Einfügen eines Bilds aus einer Datei</span><span class="sxs-lookup"><span data-stu-id="a11bb-102">Inserting an Image from a File</span></span>
<span data-ttu-id="a11bb-103">Je nach Feldtyp in der Datenquelle können Sie ein Binary Large Object (BLOB) entweder als Binär- oder Zeichendaten in eine Datenbank schreiben.</span><span class="sxs-lookup"><span data-stu-id="a11bb-103">You can write a binary large object (BLOB) to a database as either binary or character data, depending on the type of field at your data source.</span></span> <span data-ttu-id="a11bb-104">BLOB ist ein generischer Begriff und verweist auf die Datentypen `text`, `ntext` und `image`, die in der Regel Dokumente und Bilder enthalten.</span><span class="sxs-lookup"><span data-stu-id="a11bb-104">BLOB is a generic term that refers to the `text`, `ntext`, and `image` data types, which typically contain documents and pictures.</span></span>  
  
 <span data-ttu-id="a11bb-105">Um einen BLOB-Wert in der Datenbank zu schreiben, geben Sie die entsprechende INSERT- oder UPDATE-Anweisung aus, und übergeben Sie den BLOB-Wert als Eingabeparameter (finden Sie unter [Konfigurieren von Parametern und Parameterdatentypen](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)).</span><span class="sxs-lookup"><span data-stu-id="a11bb-105">To write a BLOB value to your database, issue the appropriate INSERT or UPDATE statement and pass the BLOB value as an input parameter (see [Configuring Parameters and Parameter Data Types](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)).</span></span> <span data-ttu-id="a11bb-106">Wenn das BLOB als Text gespeichert ist (z. B. ein SQL Server-Feld vom Typ `text`), können Sie das BLOB als Zeichenfolgenparameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="a11bb-106">If your BLOB is stored as text, such as a SQL Server `text` field, you can pass the BLOB as a string parameter.</span></span> <span data-ttu-id="a11bb-107">Wenn das BLOB im Binärformat gespeichert ist (z. B. ein SQL Server-Feld vom Typ `image`), können Sie ein Array vom Typ `byte` als Binärparameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="a11bb-107">If the BLOB is stored in binary format, such as a SQL Server `image` field, you can pass an array of type `byte` as a binary parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a11bb-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a11bb-108">Example</span></span>  
 <span data-ttu-id="a11bb-109">Im folgenden Codebeispiel werden der Tabelle Employees in der Northwind-Datenbank Mitarbeiterinformationen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a11bb-109">The following code example adds employee information to the Employees table in the Northwind database.</span></span> <span data-ttu-id="a11bb-110">Ein Foto des Mitarbeiters wird aus einer Datei geladen und dem Photo-Feld der Tabelle, einem Bildfeld, hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a11bb-110">A photo of the employee is read from a file and added to the Photo field in the table, which is an image field.</span></span>  
  
```vb  
Public Shared Sub AddEmployee( _  
  lastName As String, _  
  firstName As String, _  
  title As String, _  
  hireDate As DateTime, _  
  reportsTo As Integer, _  
  photoFilePath As String, _  
  connectionString As String)  
  
  Dim photo() as Byte = GetPhoto(photoFilePath)  
  
  Using connection As SqlConnection = New SqlConnection( _  
    connectionString)  
  
  Dim command As SqlCommand = New SqlCommand( _  
    "INSERT INTO Employees (LastName, FirstName, Title, " & _  
    "HireDate, ReportsTo, Photo) " & _  
    "Values(@LastName, @FirstName, @Title, " & _  
    "@HireDate, @ReportsTo, @Photo)", connection)   
  
  command.Parameters.Add("@LastName",  _  
    SqlDbType.NVarChar, 20).Value = lastName  
  command.Parameters.Add("@FirstName", _  
    SqlDbType.NVarChar, 10).Value = firstName  
  command.Parameters.Add("@Title", _  
    SqlDbType.NVarChar, 30).Value = title  
  command.Parameters.Add("@HireDate", _  
    SqlDbType.DateTime).Value = hireDate  
  command.Parameters.Add("@ReportsTo", _  
    SqlDbType.Int).Value = reportsTo  
  
  command.Parameters.Add("@Photo", _  
    SqlDbType.Image, photo.Length).Value = photo  
  
  connection.Open()  
  command.ExecuteNonQuery()  
  
  End Using  
End Sub  
  
Public Shared Function GetPhoto(filePath As String) As Byte()  
  Dim stream As FileStream = new FileStream( _  
     filePath, FileMode.Open, FileAccess.Read)  
  Dim reader As BinaryReader = new BinaryReader(stream)  
  
  Dim photo() As Byte = reader.ReadBytes(stream.Length)  
  
  reader.Close()  
  stream.Close()  
  
  Return photo  
End Function  
```  
  
```csharp  
public static void AddEmployee(  
  string lastName,   
  string firstName,   
  string title,   
  DateTime hireDate,   
  int reportsTo,   
  string photoFilePath,   
  string connectionString)  
{  
  byte[] photo = GetPhoto(photoFilePath);  
  
  using (SqlConnection connection = new SqlConnection(  
    connectionString))  
  
  SqlCommand command = new SqlCommand(  
    "INSERT INTO Employees (LastName, FirstName, " +  
    "Title, HireDate, ReportsTo, Photo) " +  
    "Values(@LastName, @FirstName, @Title, " +  
    "@HireDate, @ReportsTo, @Photo)", connection);   
  
  command.Parameters.Add("@LastName",    
     SqlDbType.NVarChar, 20).Value = lastName;  
  command.Parameters.Add("@FirstName",   
      SqlDbType.NVarChar, 10).Value = firstName;  
  command.Parameters.Add("@Title",       
      SqlDbType.NVarChar, 30).Value = title;  
  command.Parameters.Add("@HireDate",   
       SqlDbType.DateTime).Value = hireDate;  
  command.Parameters.Add("@ReportsTo",   
      SqlDbType.Int).Value = reportsTo;  
  
  command.Parameters.Add("@Photo",  
      SqlDbType.Image, photo.Length).Value = photo;  
  
  connection.Open();  
  command.ExecuteNonQuery();  
  }  
}  
  
public static byte[] GetPhoto(string filePath)  
{  
  FileStream stream = new FileStream(  
      filePath, FileMode.Open, FileAccess.Read);  
  BinaryReader reader = new BinaryReader(stream);  
  
  byte[] photo = reader.ReadBytes((int)stream.Length);  
  
  reader.Close();  
  stream.Close();  
  
  return photo;  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="a11bb-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a11bb-111">See also</span></span>

- [<span data-ttu-id="a11bb-112">Verwenden von Befehlen zum Ändern von Daten</span><span class="sxs-lookup"><span data-stu-id="a11bb-112">Using Commands to Modify Data</span></span>](../../../../../docs/framework/data/adonet/using-commands-to-modify-data.md)
- [<span data-ttu-id="a11bb-113">Abrufen von Binärdaten</span><span class="sxs-lookup"><span data-stu-id="a11bb-113">Retrieving Binary Data</span></span>](../../../../../docs/framework/data/adonet/retrieving-binary-data.md)
- [<span data-ttu-id="a11bb-114">SQL Server Binary and Large-Value Data (Binäre Daten und Daten mit umfangreichen Werten in SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a11bb-114">SQL Server Binary and Large-Value Data</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="a11bb-115">SQL Server-Datentypzuordnungen</span><span class="sxs-lookup"><span data-stu-id="a11bb-115">SQL Server Data Type Mappings</span></span>](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)
- [<span data-ttu-id="a11bb-116">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="a11bb-116">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
