---
title: "Abrufen von Bin&#228;rdaten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 56c5a9e3-31f1-482f-bce0-ff1c41a658d0
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# Abrufen von Bin&#228;rdaten
In der Standardeinstellung lädt der **DataReader** eingehende Daten als Zeile, sobald eine ganze Datenzeile verfügbar ist.  BLOBs \(Binary Large Objects\) müssen jedoch anders behandelt werden, da sie mehrere Gigabyte an Daten umfassen können, die nicht in eine einzelne Zeile passen.  Die **Command.ExecuteReader**\-Methode weist eine Überladung auf, die eine Änderung des Standardverhaltens von **DataReader** mit einem <xref:System.Data.CommandBehavior>\-Argument erforderlich macht.  Durch Übergeben von <xref:System.Data.CommandBehavior> an die **ExecuteReader**\-Methode kann das Standardverhalten von **DataReader** so geändert werden, dass nicht Datenzeilen, sondern die Daten beim Empfang nacheinander geladen werden.  Diese Methode eignet sich hervorragend zum Laden von BLOBs oder anderen großen Datenstrukturen.  Beachten Sie, dass dieses Verhalten je nach Datenquelle verschieden sein kann.  Wenn beispielsweise ein BLOB von Microsoft Access zurückgegeben wird, werden die Daten beim Empfang nicht sequenziell geladen, sondern das BLOB wird vollständig in den Speicher geladen.  
  
 Wenn Sie für **DataReader** die Verwendung von **SequentialAccess** festlegen, müssen Sie die Reihenfolge beachten, in der Sie auf die zurückgegebenen Felder zugreifen.  Das Standardverhalten von **DataReader** \(Laden der ganzen Zeile sobald sie verfügbar ist\) ermöglicht Ihnen den Zugriff auf die zurückgegebenen Felder in beliebiger Reihenfolge, bis die nächste Zeile gelesen wird.  Beim Verwenden von **SequentialAccess** muss jedoch auf die vom **DataReader** zurückgegebenen Felder in der entsprechenden Reihenfolge zugegriffen werden.  Wenn die Abfrage beispielsweise drei Spalten zurückgibt, von der die dritte ein BLOB ist, müssen zuerst die Werte des ersten und zweiten Felds zurückgegeben werden, bevor auf die BLOB\-Daten im dritten Feld zugegriffen werden darf.  Wenn Sie vor dem ersten und zweiten Feld auf das dritte Feld zugreifen, sind die Werte des ersten und zweiten Feldes nicht mehr verfügbar.  Dies liegt daran, dass der **DataReader** mit **SequentialAccess** geändert wurde, sodass Daten nur noch der Reihe nach zurückgegeben werden und die Daten nicht mehr verfügbar sind, nachdem der **DataReader** über das Ende dieser Daten hinaus gelesen hat.  
  
 Verwenden Sie zum Zugreifen auf die Daten im BLOB\-Feld die typisierten Accessoren **GetBytes** oder **GetChars** des **DataReader**, die ein Array mit Daten füllen.  Sie können jedoch auch **GetString** für Zeichendaten verwenden.  Möglicherweise möchten Sie keinen ganzen BLOB\-Wert in eine einzelne Zeichenfolgenvariable laden.  Sie können stattdessen eine bestimmte Puffergröße für Rückgabedaten und die Anfangsposition für das erste zu lesende Byte oder Zeichen in den Rückgabedaten angeben.  Mit **GetBytes** und **GetChars** wird ein `long`\-Wert zurückgegeben, der der Anzahl der zurückgegebenen Bytes oder Zeichen entspricht.  Wenn Sie an **GetBytes** oder **GetChars** ein NULL\-Array übergeben, entspricht der zurückgegebene long\-Wert der Gesamtzahl von Bytes oder Zeichen im BLOB.  Optional können Sie einen Index im Array als Anfangsposition für die gelesenen Daten angeben.  
  
## Beispiel  
 Im folgenden Beispiel werden die Herausgeber\-ID und das Logo von der **pubs**\-Beispieldatenbank in Microsoft SQL Server zurückgegeben.  Die Herausgeber\-ID \(`pub_id`\) ist ein Zeichenfeld, und das Logo ist ein Bild, das ein BLOB darstellt.  Da das **logo**\-Feld ein Bitmap ist, werden im Beispiel mithilfe von **GetBytes** Binärdaten zurückgegeben.  Beachten Sie, dass für die aktuelle Datenzeile zuerst auf die Herausgeber\-ID und dann auf das Logo zugegriffen wird, da der Zugriff auf die Felder der Reihe nach erfolgen muss.  
  
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
  writer.Write(outByte, 0, (int)retval - 1);  
  writer.Flush();  
  
  // Close the output file.  
  writer.Close();  
  stream.Close();  
}  
  
// Close the reader and the connection.  
reader.Close();  
connection.Close();  
```  
  
## Siehe auch  
 [Working with DataReaders](http://msdn.microsoft.com/de-de/126a966a-d08d-4d22-a19f-f432908b2b54)   
 [Binäre Daten und Daten mit umfangreichen Werten in SQL Server](../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)