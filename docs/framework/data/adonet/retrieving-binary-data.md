---
title: Abrufen von Binärdaten
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 56c5a9e3-31f1-482f-bce0-ff1c41a658d0
ms.openlocfilehash: c914a9b0780e2e87e177502b0f9faff0e7c4b617
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149049"
---
# <a name="retrieving-binary-data"></a>Abrufen von Binärdaten
Standardmäßig lädt der **DataReader** eingehende Daten als Zeile, sobald eine ganze Datenzeile verfügbar ist. BLOBs (Binary Large Objects) müssen jedoch anders behandelt werden, da sie mehrere Gigabyte an Daten umfassen können, die nicht in eine einzelne Zeile passen. Die **Command.ExecuteReader-Methode** verfügt über eine <xref:System.Data.CommandBehavior> Überladung, die ein Argument verwendet, um das Standardverhalten des **DataReader**zu ändern. Sie können <xref:System.Data.CommandBehavior.SequentialAccess> an die **ExecuteReader-Methode** übergeben, um das Standardverhalten des **DataReaders** so zu ändern, dass Daten beim Empfangen sequenziell geladen werden, anstatt Datenzeilen zu laden. Diese Methode eignet sich hervorragend zum Laden von BLOBs oder anderen großen Datenstrukturen. Beachten Sie, dass dieses Verhalten je nach Datenquelle verschieden sein kann. Wenn beispielsweise ein BLOB von Microsoft Access zurückgegeben wird, werden die Daten beim Empfang nicht sequenziell geladen, sondern das BLOB wird vollständig in den Speicher geladen.  
  
 Wenn Sie den **DataReader** so einstellen, dass **SequentialAccess**verwendet wird, ist es wichtig, die Reihenfolge zu beachten, in der Sie auf die zurückgegebenen Felder zugreifen. Das Standardverhalten des **DataReader**, der eine ganze Zeile lädt, sobald sie verfügbar ist, ermöglicht Ihnen den Zugriff auf die Felder, die in beliebiger Reihenfolge zurückgegeben werden, bis die nächste Zeile gelesen wird. Bei verwendung **ssequentialAccess** müssen Sie jedoch in der Reihenfolge auf die vom **DataReader** zurückgegebenen Felder zugreifen. Wenn die Abfrage beispielsweise drei Spalten zurückgibt, von der die dritte ein BLOB ist, müssen zuerst die Werte des ersten und zweiten Felds zurückgegeben werden, bevor auf die BLOB-Daten im dritten Feld zugegriffen werden darf. Wenn Sie vor dem ersten und zweiten Feld auf das dritte Feld zugreifen, sind die Werte des ersten und zweiten Feldes nicht mehr verfügbar. Dies liegt daran, dass **SequentialAccess** den **DataReader** so geändert hat, dass Daten nacheinander zurückgegeben werden und die Daten nicht verfügbar sind, nachdem der **DataReader** sie gelesen hat.  
  
 Verwenden Sie beim Zugriff auf die Daten im BLOB-Feld die vom **Typ GetBytes** oder **GetChars** typisierten Accessoren des **DataReader**, die ein Array mit Daten füllen. Sie können **GetString** auch für Zeichendaten verwenden. Jedoch. Möglicherweise möchten Sie keinen ganzen BLOB-Wert in eine einzelne Zeichenfolgenvariable laden. Sie können stattdessen eine bestimmte Puffergröße für Rückgabedaten und die Anfangsposition für das erste zu lesende Byte oder Zeichen in den Rückgabedaten angeben. **GetBytes** und **GetChars** `long` geben einen Wert zurück, der die Anzahl der zurückgegebenen Bytes oder Zeichen darstellt. Wenn Sie ein Nullarray an **GetBytes** oder **GetChars**übergeben, ist der zurückgegebene Long-Wert die Gesamtzahl der Bytes oder Zeichen im BLOB. Optional können Sie einen Index im Array als Anfangsposition für die gelesenen Daten angeben.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden die Herausgeber-ID und das Logo aus der **pubs-Beispieldatenbank** in Microsoft SQL Server zurückgegeben. Die Herausgeber-ID (`pub_id`) ist ein Zeichenfeld, und das Logo ist ein Bild, das ein BLOB darstellt. Da es sich bei dem **Logofeld** um eine Bitmap handelt, gibt das Beispiel Binärdaten mit **GetBytes**zurück. Beachten Sie, dass für die aktuelle Datenzeile zuerst auf die Herausgeber-ID und dann auf das Logo zugegriffen wird, da der Zugriff auf die Felder der Reihe nach erfolgen muss.  
  
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

- [SQL Server-Binär- und Großwertdaten](./sql/sql-server-binary-and-large-value-data.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
