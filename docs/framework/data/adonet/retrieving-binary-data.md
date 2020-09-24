---
title: Abrufen von Binärdaten
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 56c5a9e3-31f1-482f-bce0-ff1c41a658d0
ms.openlocfilehash: 11f7a81bc0d4b0e2a8d66387410d9a24503c7519
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150660"
---
# <a name="retrieving-binary-data"></a>Abrufen von Binärdaten

Standardmäßig lädt **DataReader** eingehende Daten als Zeile, sobald eine gesamte Daten Zeile verfügbar ist. BLOBs (Binary Large Objects) müssen jedoch anders behandelt werden, da sie mehrere Gigabyte an Daten umfassen können, die nicht in eine einzelne Zeile passen. Die **Command.Executereader** -Methode verfügt über eine-Überladung, die ein-Argument verwendet, <xref:System.Data.CommandBehavior> um das Standardverhalten des **DataReader**zu ändern. Sie können <xref:System.Data.CommandBehavior.SequentialAccess> an die **ExecuteReader** -Methode übergeben, um das Standardverhalten von **DataReader** so zu ändern, dass Daten nicht in Daten Zeilen geladen, sondern nacheinander geladen werden. Diese Methode eignet sich hervorragend zum Laden von BLOBs oder anderen großen Datenstrukturen. Beachten Sie, dass dieses Verhalten je nach Datenquelle verschieden sein kann. Wenn beispielsweise ein BLOB von Microsoft Access zurückgegeben wird, werden die Daten beim Empfang nicht sequenziell geladen, sondern das BLOB wird vollständig in den Speicher geladen.  
  
 Wenn Sie den **DataReader** für die Verwendung von **SequentialAccess**festlegen, ist es wichtig, die Reihenfolge zu beachten, in der Sie auf die zurückgegebenen Felder zugreifen. Das Standardverhalten des **DataReader**, der eine ganze Zeile lädt, sobald Sie verfügbar ist, ermöglicht Ihnen den Zugriff auf die Felder, die in beliebiger Reihenfolge zurückgegeben werden, bis die nächste Zeile gelesen wird. Bei Verwendung von **SequentialAccess** müssen Sie jedoch auf die vom **DataReader** zurückgegebenen Felder in der angegebenen Reihenfolge zugreifen. Wenn die Abfrage beispielsweise drei Spalten zurückgibt, von der die dritte ein BLOB ist, müssen zuerst die Werte des ersten und zweiten Felds zurückgegeben werden, bevor auf die BLOB-Daten im dritten Feld zugegriffen werden darf. Wenn Sie vor dem ersten und zweiten Feld auf das dritte Feld zugreifen, sind die Werte des ersten und zweiten Feldes nicht mehr verfügbar. Der Grund hierfür ist, dass **SequentialAccess** den **DataReader** so geändert hat, dass Daten nacheinander zurückgegeben werden, und die Daten sind nicht verfügbar, nachdem der **DataReader** ihn gelesen hat.  
  
 Verwenden Sie beim Zugriff auf die Daten im BLOB-Feld die typisierten Accessoren **GetBytes** oder **GetChars** des **DataReader**, die ein Array mit Daten füllen. Sie können auch **GetString** für Zeichendaten verwenden. Doch. Möglicherweise möchten Sie keinen ganzen BLOB-Wert in eine einzelne Zeichenfolgenvariable laden. Sie können stattdessen eine bestimmte Puffergröße für Rückgabedaten und die Anfangsposition für das erste zu lesende Byte oder Zeichen in den Rückgabedaten angeben. **GetBytes** und **GetChars** geben einen `long` Wert zurück, der die Anzahl von Bytes oder Zeichen darstellt, die zurückgegeben werden. Wenn Sie ein NULL-Array an **GetBytes** oder **GetChars**übergeben, ist der zurückgegebene Long-Wert die Gesamtzahl der Bytes oder Zeichen im BLOB. Optional können Sie einen Index im Array als Anfangsposition für die gelesenen Daten angeben.  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel werden die Herausgeber-ID und das Logo von der **Pubs** -Beispieldatenbank in Microsoft SQL Server zurückgegeben. Die Herausgeber-ID (`pub_id`) ist ein Zeichenfeld, und das Logo ist ein Bild, das ein BLOB darstellt. Da es sich bei dem **Logo** -Feld um eine Bitmap handelt, gibt das Beispiel Binärdaten mithilfe von **GetBytes**zurück. Beachten Sie, dass für die aktuelle Datenzeile zuerst auf die Herausgeber-ID und dann auf das Logo zugegriffen wird, da der Zugriff auf die Felder der Reihe nach erfolgen muss.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [SQL Server von Binärdaten und Daten mit umfangreichen Werten](./sql/sql-server-binary-and-large-value-data.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
