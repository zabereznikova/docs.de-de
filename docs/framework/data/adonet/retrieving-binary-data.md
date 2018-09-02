---
title: Abrufen von Binärdaten
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 56c5a9e3-31f1-482f-bce0-ff1c41a658d0
ms.openlocfilehash: ec4ef17687e4e1bf2cc18182a64fc7361fe3b6f7
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43421982"
---
# <a name="retrieving-binary-data"></a><span data-ttu-id="7bedd-102">Abrufen von Binärdaten</span><span class="sxs-lookup"><span data-stu-id="7bedd-102">Retrieving Binary Data</span></span>
<span data-ttu-id="7bedd-103">In der Standardeinstellung die **DataReader** eingehende Daten als eine Zeile geladen wird, sobald eine ganze Datenzeile verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="7bedd-103">By default, the **DataReader** loads incoming data as a row as soon as an entire row of data is available.</span></span> <span data-ttu-id="7bedd-104">BLOBs (Binary Large Objects) müssen jedoch anders behandelt werden, da sie mehrere Gigabyte an Daten umfassen können, die nicht in eine einzelne Zeile passen.</span><span class="sxs-lookup"><span data-stu-id="7bedd-104">Binary large objects (BLOBs) need different treatment, however, because they can contain gigabytes of data that cannot be contained in a single row.</span></span> <span data-ttu-id="7bedd-105">Die **Command.ExecuteReader** Methode verfügt über eine Überladung auf, eine <xref:System.Data.CommandBehavior> Argument so ändern Sie das Standardverhalten der **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="7bedd-105">The **Command.ExecuteReader** method has an overload that will take a <xref:System.Data.CommandBehavior> argument to modify the default behavior of the **DataReader**.</span></span> <span data-ttu-id="7bedd-106">Können Sie übergeben <xref:System.Data.CommandBehavior.SequentialAccess> auf die **"ExecuteReader"** Methode, um das Standardverhalten ändern der **DataReader** , damit anstelle von Zeilen mit Daten werden geladen, Daten sequenziell geladen werden, wie sie empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="7bedd-106">You can pass <xref:System.Data.CommandBehavior.SequentialAccess> to the **ExecuteReader** method to modify the default behavior of the **DataReader** so that instead of loading rows of data, it will load data sequentially as it is received.</span></span> <span data-ttu-id="7bedd-107">Diese Methode eignet sich hervorragend zum Laden von BLOBs oder anderen großen Datenstrukturen.</span><span class="sxs-lookup"><span data-stu-id="7bedd-107">This is ideal for loading BLOBs or other large data structures.</span></span> <span data-ttu-id="7bedd-108">Beachten Sie, dass dieses Verhalten je nach Datenquelle verschieden sein kann.</span><span class="sxs-lookup"><span data-stu-id="7bedd-108">Note that this behavior may depend on your data source.</span></span> <span data-ttu-id="7bedd-109">Wenn beispielsweise ein BLOB von Microsoft Access zurückgegeben wird, werden die Daten beim Empfang nicht sequenziell geladen, sondern das BLOB wird vollständig in den Speicher geladen.</span><span class="sxs-lookup"><span data-stu-id="7bedd-109">For example, returning a BLOB from Microsoft Access will load the entire BLOB being loaded into memory, rather than sequentially as it is received.</span></span>  
  
 <span data-ttu-id="7bedd-110">Beim Festlegen der **DataReader** verwenden **SequentialAccess**, es ist wichtig, die Reihenfolge beachten, in dem Sie die zurückgegebenen Felder zugreifen.</span><span class="sxs-lookup"><span data-stu-id="7bedd-110">When setting the **DataReader** to use **SequentialAccess**, it is important to note the sequence in which you access the fields returned.</span></span> <span data-ttu-id="7bedd-111">Das Standardverhalten der **DataReader**, die eine ganze Zeile lädt, sobald sie verfügbar ist, ermöglicht den Zugriff auf die Felder in beliebiger Reihenfolge zurückgegeben werden, bis die nächste Zeile gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="7bedd-111">The default behavior of the **DataReader**, which loads an entire row as soon as it is available, allows you to access the fields returned in any order until the next row is read.</span></span> <span data-ttu-id="7bedd-112">Bei Verwendung **SequentialAccess** müssen Sie jedoch die vom zurückgegebenen Felder zugreifen der **DataReader** in der Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="7bedd-112">When using **SequentialAccess** however, you must access the fields returned by the **DataReader** in order.</span></span> <span data-ttu-id="7bedd-113">Wenn die Abfrage beispielsweise drei Spalten zurückgibt, von der die dritte ein BLOB ist, müssen zuerst die Werte des ersten und zweiten Felds zurückgegeben werden, bevor auf die BLOB-Daten im dritten Feld zugegriffen werden darf.</span><span class="sxs-lookup"><span data-stu-id="7bedd-113">For example, if your query returns three columns, the third of which is a BLOB, you must return the values of the first and second fields before accessing the BLOB data in the third field.</span></span> <span data-ttu-id="7bedd-114">Wenn Sie vor dem ersten und zweiten Feld auf das dritte Feld zugreifen, sind die Werte des ersten und zweiten Feldes nicht mehr verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7bedd-114">If you access the third field before the first or second fields, the first and second field values are no longer available.</span></span> <span data-ttu-id="7bedd-115">Grund hierfür ist, **SequentialAccess** wurde geändert, die **DataReader** , Daten in und die Daten zurückzugeben ist nicht verfügbar, nachdem die **DataReader** gelesen hat.</span><span class="sxs-lookup"><span data-stu-id="7bedd-115">This is because **SequentialAccess** has modified the **DataReader** to return data in sequence and the data is not available after the **DataReader** has read past it.</span></span>  
  
 <span data-ttu-id="7bedd-116">Verwenden Sie beim Zugriff auf die Daten im BLOB-Feld der **GetBytes** oder **GetChars** typisierten Zugriffsmethoden des der **DataReader**, die ein Array mit Daten füllen.</span><span class="sxs-lookup"><span data-stu-id="7bedd-116">When accessing the data in the BLOB field, use the **GetBytes** or **GetChars** typed accessors of the **DataReader**, which fill an array with data.</span></span> <span data-ttu-id="7bedd-117">Sie können auch **GetString** für Zeichendaten jedoch.</span><span class="sxs-lookup"><span data-stu-id="7bedd-117">You can also use **GetString** for character data; however.</span></span> <span data-ttu-id="7bedd-118">Möglicherweise möchten Sie keinen ganzen BLOB-Wert in eine einzelne Zeichenfolgenvariable laden.</span><span class="sxs-lookup"><span data-stu-id="7bedd-118">to conserve system resources you might not want to load an entire BLOB value into a single string variable.</span></span> <span data-ttu-id="7bedd-119">Sie können stattdessen eine bestimmte Puffergröße für Rückgabedaten und die Anfangsposition für das erste zu lesende Byte oder Zeichen in den Rückgabedaten angeben.</span><span class="sxs-lookup"><span data-stu-id="7bedd-119">You can instead specify a specific buffer size of data to be returned, and a starting location for the first byte or character to be read from the returned data.</span></span> <span data-ttu-id="7bedd-120">**GetBytes** und **GetChars** gibt eine `long` Wert, der die Anzahl der zurückgegebenen Bytes oder Zeichen darstellt.</span><span class="sxs-lookup"><span data-stu-id="7bedd-120">**GetBytes** and **GetChars** will return a `long` value, which represents the number of bytes or characters returned.</span></span> <span data-ttu-id="7bedd-121">Wenn Sie ein null-Array übergeben **GetBytes** oder **GetChars**, die long-Wert zurückgegeben werden, dass die Gesamtanzahl von Bytes oder Zeichen im BLOB.</span><span class="sxs-lookup"><span data-stu-id="7bedd-121">If you pass a null array to **GetBytes** or **GetChars**, the long value returned will be the total number of bytes or characters in the BLOB.</span></span> <span data-ttu-id="7bedd-122">Optional können Sie einen Index im Array als Anfangsposition für die gelesenen Daten angeben.</span><span class="sxs-lookup"><span data-stu-id="7bedd-122">You can optionally specify an index in the array as a starting position for the data being read.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7bedd-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7bedd-123">Example</span></span>  
 <span data-ttu-id="7bedd-124">Im folgenden Beispiel zurückgegeben, die Herausgeber-ID und das Logo von der **Pubs** -Beispieldatenbank in Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7bedd-124">The following example returns the publisher ID and logo from the **pubs** sample database in Microsoft SQL Server.</span></span> <span data-ttu-id="7bedd-125">Die Herausgeber-ID (`pub_id`) ist ein Zeichenfeld, und das Logo ist ein Bild, das ein BLOB darstellt.</span><span class="sxs-lookup"><span data-stu-id="7bedd-125">The publisher ID (`pub_id`) is a character field, and the logo is an image, which is a BLOB.</span></span> <span data-ttu-id="7bedd-126">Da die **Logo** Feld ist eine Bitmap ist, im Beispiel wird mithilfe von Binärdaten **GetBytes**.</span><span class="sxs-lookup"><span data-stu-id="7bedd-126">Because the **logo** field is a bitmap, the example returns binary data using **GetBytes**.</span></span> <span data-ttu-id="7bedd-127">Beachten Sie, dass für die aktuelle Datenzeile zuerst auf die Herausgeber-ID und dann auf das Logo zugegriffen wird, da der Zugriff auf die Felder der Reihe nach erfolgen muss.</span><span class="sxs-lookup"><span data-stu-id="7bedd-127">Notice that the publisher ID is accessed for the current row of data before the logo, because the fields must be accessed sequentially.</span></span>  
  
```vb  
' Assumes that connection is a valid SqlConnection object.  
Dim command As SqlCommand = New SqlCommand( _  
  "SELECT pub_id, logo FROM pub_info", connection)  
  
' Writes the BLOB to a file (*.bmp).  
Dim stream As FileStream                   
' Streams the binary data to the FileStream object.  
Dim writer As BinaryWriter                 
' The size of the BLOB buffer.  
Dim bufferSize As Integer = 100        
' The BLOB byte() buffer to be filled by GetBytes.  
Dim outByte(bufferSize - 1) As Byte    
' The bytes returned from GetBytes.  
Dim retval As Long                     
' The starting position in the BLOB output.  
Dim startIndex As Long = 0             
  
' The publisher id to use in the file name.  
Dim pubID As String = ""              
  
' Open the connection and read data into the DataReader.  
connection.Open()  
Dim reader As SqlDataReader = command.ExecuteReader(CommandBehavior.SequentialAccess)  
  
Do While reader.Read()  
  ' Get the publisher id, which must occur before getting the logo.  
  pubID = reader.GetString(0)  
  
  ' Create a file to hold the output.  
  stream = New FileStream( _  
    "logo" & pubID & ".bmp", FileMode.OpenOrCreate, FileAccess.Write)  
  writer = New BinaryWriter(stream)  
  
  ' Reset the starting byte for a new BLOB.  
  startIndex = 0  
  
  ' Read bytes into outByte() and retain the number of bytes returned.  
  retval = reader.GetBytes(1, startIndex, outByte, 0, bufferSize)  
  
  ' Continue while there are bytes beyond the size of the buffer.  
  Do While retval = bufferSize  
    writer.Write(outByte)  
    writer.Flush()  
  
    ' Reposition start index to end of the last buffer and fill buffer.  
    startIndex += bufferSize  
    retval = reader.GetBytes(1, startIndex, outByte, 0, bufferSize)  
  Loop  
  
  ' Write the remaining buffer.  
  writer.Write(outByte, 0 , retval - 1)  
  writer.Flush()  
  
  ' Close the output file.  
  writer.Close()  
  stream.Close()  
Loop  
  
' Close the reader and the connection.  
reader.Close()  
connection.Close()  
```  
  
```csharp  
// Assumes that connection is a valid SqlConnection object.  
SqlCommand command = new SqlCommand(  
  "SELECT pub_id, logo FROM pub_info", connection);  
  
// Writes the BLOB to a file (*.bmp).  
FileStream stream;                            
// Streams the BLOB to the FileStream object.  
BinaryWriter writer;                          
  
// Size of the BLOB buffer.  
int bufferSize = 100;                     
// The BLOB byte[] buffer to be filled by GetBytes.  
byte[] outByte = new byte[bufferSize];    
// The bytes returned from GetBytes.  
long retval;                              
// The starting position in the BLOB output.  
long startIndex = 0;                      
  
// The publisher id to use in the file name.  
string pubID = "";                       
  
// Open the connection and read data into the DataReader.  
connection.Open();  
SqlDataReader reader = command.ExecuteReader(CommandBehavior.SequentialAccess);  
  
while (reader.Read())  
{  
  // Get the publisher id, which must occur before getting the logo.  
  pubID = reader.GetString(0);    
  
  // Create a file to hold the output.  
  stream = new FileStream(  
    "logo" + pubID + ".bmp", FileMode.OpenOrCreate, FileAccess.Write);  
  writer = new BinaryWriter(stream);  
  
  // Reset the starting byte for the new BLOB.  
  startIndex = 0;  
  
  // Read bytes into outByte[] and retain the number of bytes returned.  
  retval = reader.GetBytes(1, startIndex, outByte, 0, bufferSize);  
  
  // Continue while there are bytes beyond the size of the buffer.  
  while (retval == bufferSize)  
  {  
    writer.Write(outByte);  
    writer.Flush();  
  
    // Reposition start index to end of last buffer and fill buffer.  
    startIndex += bufferSize;  
    retval = reader.GetBytes(1, startIndex, outByte, 0, bufferSize);  
  }  
  
  // Write the remaining buffer.  
  writer.Write(outByte, 0, (int)retval);  
  writer.Flush();  
  
  // Close the output file.  
  writer.Close();  
  stream.Close();  
}  
  
// Close the reader and the connection.  
reader.Close();  
connection.Close();  
```  
  
## <a name="see-also"></a><span data-ttu-id="7bedd-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7bedd-128">See Also</span></span>  
 [<span data-ttu-id="7bedd-129">Arbeiten mit "DataReaders"</span><span class="sxs-lookup"><span data-stu-id="7bedd-129">Working with DataReaders</span></span>](https://msdn.microsoft.com/library/126a966a-d08d-4d22-a19f-f432908b2b54)  
 [<span data-ttu-id="7bedd-130">SQL Server Binary and Large-Value Data (Binäre Daten und Daten mit umfangreichen Werten in SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7bedd-130">SQL Server Binary and Large-Value Data</span></span>](../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)  
 [<span data-ttu-id="7bedd-131">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="7bedd-131">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
