---
title: Einfügen eines Bilds aus einer Datei
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 35900aa2-5615-4174-8212-ba184c6b82fb
ms.openlocfilehash: 94ec554ca2dc5ed4eb6792b9b42ae6f1b856f51e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148607"
---
# <a name="inserting-an-image-from-a-file"></a><span data-ttu-id="6ae97-102">Einfügen eines Bilds aus einer Datei</span><span class="sxs-lookup"><span data-stu-id="6ae97-102">Inserting an Image from a File</span></span>
<span data-ttu-id="6ae97-103">Je nach Feldtyp in Ihrer Datenquelle können Sie ein Blob (Binary Large Object) entweder als Binär- oder Zeichendaten in eine Datenbank schreiben.</span><span class="sxs-lookup"><span data-stu-id="6ae97-103">You can write a binary large object (BLOB) to a database as either binary or character data, depending on the type of field at your data source.</span></span> <span data-ttu-id="6ae97-104">„Blob“ ist ein allgemeiner Begriff, der sich auf die Datentypen `text`, `ntext` und `image` bezieht, die in der Regel Dokumente und Bilder enthalten.</span><span class="sxs-lookup"><span data-stu-id="6ae97-104">BLOB is a generic term that refers to the `text`, `ntext`, and `image` data types, which typically contain documents and pictures.</span></span>  
  
 <span data-ttu-id="6ae97-105">Um einen BLOB-Wert in Ihre Datenbank zu schreiben, geben Sie die entsprechende INSERT- oder UPDATE-Anweisung aus, und übergeben Sie den BLOB-Wert als Eingabeparameter (siehe [Konfigurieren von Parametern und Parameterdatentypen](../configuring-parameters-and-parameter-data-types.md)).</span><span class="sxs-lookup"><span data-stu-id="6ae97-105">To write a BLOB value to your database, issue the appropriate INSERT or UPDATE statement and pass the BLOB value as an input parameter (see [Configuring Parameters and Parameter Data Types](../configuring-parameters-and-parameter-data-types.md)).</span></span> <span data-ttu-id="6ae97-106">Wenn Ihr Blob in Form von Text gespeichert wird, z. B. als `text`-Feld in SQL Server, können Sie das Blob als Zeichenfolgenparameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="6ae97-106">If your BLOB is stored as text, such as a SQL Server `text` field, you can pass the BLOB as a string parameter.</span></span> <span data-ttu-id="6ae97-107">Wenn das Blob im Binärformat gespeichert wird, z. B. als `image`-Feld in SQL Server, können Sie ein Array vom Typ `byte` als binären Parameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="6ae97-107">If the BLOB is stored in binary format, such as a SQL Server `image` field, you can pass an array of type `byte` as a binary parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ae97-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6ae97-108">Example</span></span>  
 <span data-ttu-id="6ae97-109">Im folgenden Codebeispiel werden Mitarbeiterinformationen zur Tabelle „Employees“ in der Datenbank „Northwind“ hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6ae97-109">The following code example adds employee information to the Employees table in the Northwind database.</span></span> <span data-ttu-id="6ae97-110">Ein Foto des Mitarbeiters wird aus einer Datei gelesen und zum Feld „Photo“ in der Tabelle hinzugefügt. Dieses Feld ist ein Bildfeld.</span><span class="sxs-lookup"><span data-stu-id="6ae97-110">A photo of the employee is read from a file and added to the Photo field in the table, which is an image field.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6ae97-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6ae97-111">See also</span></span>

- [<span data-ttu-id="6ae97-112">Verwenden von Befehlen zum Ändern von Daten</span><span class="sxs-lookup"><span data-stu-id="6ae97-112">Using Commands to Modify Data</span></span>](../using-commands-to-modify-data.md)
- [<span data-ttu-id="6ae97-113">Abrufen von Binärdaten</span><span class="sxs-lookup"><span data-stu-id="6ae97-113">Retrieving Binary Data</span></span>](../retrieving-binary-data.md)
- [<span data-ttu-id="6ae97-114">SQL Server-Binär- und Großwertdaten</span><span class="sxs-lookup"><span data-stu-id="6ae97-114">SQL Server Binary and Large-Value Data</span></span>](sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="6ae97-115">SQL Server-Datentypzuordnungen</span><span class="sxs-lookup"><span data-stu-id="6ae97-115">SQL Server Data Type Mappings</span></span>](../sql-server-data-type-mappings.md)
- [<span data-ttu-id="6ae97-116">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6ae97-116">ADO.NET Overview</span></span>](../ado-net-overview.md)
