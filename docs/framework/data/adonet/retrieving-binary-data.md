---
title: Abrufen von Binärdaten
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 56c5a9e3-31f1-482f-bce0-ff1c41a658d0
ms.openlocfilehash: 068b84e8704b54e6aea148ec5fc5bf9f0c4cb958
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59085973"
---
# <a name="retrieving-binary-data"></a>Abrufen von Binärdaten
In der Standardeinstellung die **DataReader** eingehende Daten als eine Zeile geladen wird, sobald eine ganze Datenzeile verfügbar ist. BLOBs (Binary Large Objects) müssen jedoch anders behandelt werden, da sie mehrere Gigabyte an Daten umfassen können, die nicht in eine einzelne Zeile passen. Die **Command.ExecuteReader** Methode verfügt über eine Überladung auf, eine <xref:System.Data.CommandBehavior> Argument so ändern Sie das Standardverhalten der **DataReader**. Können Sie übergeben <xref:System.Data.CommandBehavior.SequentialAccess> auf die **"ExecuteReader"** Methode, um das Standardverhalten ändern der **DataReader** , damit anstelle von Zeilen mit Daten werden geladen, Daten sequenziell geladen werden, wie sie empfangen wird. Diese Methode eignet sich hervorragend zum Laden von BLOBs oder anderen großen Datenstrukturen. Beachten Sie, dass dieses Verhalten je nach Datenquelle verschieden sein kann. Wenn beispielsweise ein BLOB von Microsoft Access zurückgegeben wird, werden die Daten beim Empfang nicht sequenziell geladen, sondern das BLOB wird vollständig in den Speicher geladen.  
  
 Beim Festlegen der **DataReader** verwenden **SequentialAccess**, es ist wichtig, die Reihenfolge beachten, in dem Sie die zurückgegebenen Felder zugreifen. Das Standardverhalten der **DataReader**, die eine ganze Zeile lädt, sobald sie verfügbar ist, ermöglicht den Zugriff auf die Felder in beliebiger Reihenfolge zurückgegeben werden, bis die nächste Zeile gelesen wird. Bei Verwendung **SequentialAccess** müssen Sie jedoch die vom zurückgegebenen Felder zugreifen der **DataReader** in der Reihenfolge. Wenn die Abfrage beispielsweise drei Spalten zurückgibt, von der die dritte ein BLOB ist, müssen zuerst die Werte des ersten und zweiten Felds zurückgegeben werden, bevor auf die BLOB-Daten im dritten Feld zugegriffen werden darf. Wenn Sie vor dem ersten und zweiten Feld auf das dritte Feld zugreifen, sind die Werte des ersten und zweiten Feldes nicht mehr verfügbar. Grund hierfür ist, **SequentialAccess** wurde geändert, die **DataReader** , Daten in und die Daten zurückzugeben ist nicht verfügbar, nachdem die **DataReader** gelesen hat.  
  
 Verwenden Sie beim Zugriff auf die Daten im BLOB-Feld der **GetBytes** oder **GetChars** typisierten Zugriffsmethoden des der **DataReader**, die ein Array mit Daten füllen. Sie können auch **GetString** für Zeichendaten jedoch. Möglicherweise möchten Sie keinen ganzen BLOB-Wert in eine einzelne Zeichenfolgenvariable laden. Sie können stattdessen eine bestimmte Puffergröße für Rückgabedaten und die Anfangsposition für das erste zu lesende Byte oder Zeichen in den Rückgabedaten angeben. **GetBytes** und **GetChars** gibt eine `long` Wert, der die Anzahl der zurückgegebenen Bytes oder Zeichen darstellt. Wenn Sie ein null-Array übergeben **GetBytes** oder **GetChars**, die long-Wert zurückgegeben werden, dass die Gesamtanzahl von Bytes oder Zeichen im BLOB. Optional können Sie einen Index im Array als Anfangsposition für die gelesenen Daten angeben.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel zurückgegeben, die Herausgeber-ID und das Logo von der **Pubs** -Beispieldatenbank in Microsoft SQL Server. Die Herausgeber-ID (`pub_id`) ist ein Zeichenfeld, und das Logo ist ein Bild, das ein BLOB darstellt. Da die **Logo** Feld ist eine Bitmap ist, im Beispiel wird mithilfe von Binärdaten **GetBytes**. Beachten Sie, dass für die aktuelle Datenzeile zuerst auf die Herausgeber-ID und dann auf das Logo zugegriffen wird, da der Zugriff auf die Felder der Reihe nach erfolgen muss.  
  
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
  
## <a name="see-also"></a>Siehe auch

- [SQL Server Binary and Large-Value Data (Binäre Daten und Daten mit umfangreichen Werten in SQL Server)](../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
