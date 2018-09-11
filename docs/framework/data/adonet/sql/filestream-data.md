---
title: FILESTREAM-Daten
ms.date: 03/30/2017
ms.assetid: bd8b845c-0f09-4295-b466-97ef106eefa8
ms.openlocfilehash: eef03d171d288cb2bc62c3aaa477a95a5ce718c3
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44275107"
---
# <a name="filestream-data"></a>FILESTREAM-Daten
Das FILESTREAM-Speicherattribut wird für Binärdaten (BLOBs) verwendet, die in einer varbinary(max)-Spalte gespeichert sind. Vor FILESTREAM erforderte das Speichern von Binärdaten besondere Maßnahmen. Unstrukturierte Daten wie z. B. Textdokumente, Bilder und Videos werden häufig außerhalb der Datenbank gespeichert und sind daher schwieriger zu verwalten.  
  
> [!NOTE]
>  Sie müssen .NET Framework 3.5 SP1 (oder höher) installieren, um mithilfe von SqlClient mit FILESTREAM-Daten zu arbeiten.  
  
 Wenn das FILESTREAM-Attribut für eine varbinary(max)-Spalte festgelegt ist, werden die Daten von SQL Server im lokalen NTFS-Dateisystem und nicht in der Datenbankdatei gespeichert. Obwohl die Speicherung separat erfolgt, können dieselben [!INCLUDE[tsql](../../../../../includes/tsql-md.md)]-Anweisungen verwendet werden, die für das Arbeiten mit in der Datenbank gespeicherten varbinary(max)-Daten unterstützt werden.  
  
## <a name="sqlclient-support-for-filestream"></a>SqlClient-Unterstützung für FILESTREAM  
 Die [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] -Datenanbieter für SQL Server, <xref:System.Data.SqlClient>, unterstützt das Lesen und Schreiben von FILESTREAM-Daten mithilfe der <xref:System.Data.SqlTypes.SqlFileStream> Klasse definiert die <xref:System.Data.SqlTypes> Namespace. `SqlFileStream` erbt von der <xref:System.IO.Stream>-Klasse, die Methoden zum Lesen und Schreiben der Datenströme bereitstellt. Beim Lesen aus einem Strom werden die Daten vom Strom in eine Datenstruktur übertragen, z. B. in ein Bytearray. Beim Schreiben werden die Daten von einer Datenstruktur in einen Strom übertragen.  
  
### <a name="creating-the-sql-server-table"></a>Erstellen der SQL Server-Tabelle  
 Mit den folgenden [!INCLUDE[tsql](../../../../../includes/tsql-md.md)]-Anweisungen wird eine Tabelle mit dem Namen "employees" erstellt und eine Datenzeile eingefügt. Wenn die FILESTREAM-Speicherung aktiviert wurde, kann diese Tabelle gemeinsam mit den folgenden Codebeispielen verwendet werden. Die Links zu Ressourcen in der Onlinedokumentation zu SQL Server befinden sich am Ende dieses Themas.  
  
```  
CREATE TABLE employees  
(  
  EmployeeId INT  NOT NULL  PRIMARY KEY,  
  Photo VARBINARY(MAX) FILESTREAM  NULL,  
  RowGuid UNIQUEIDENTIFIER  NOT NULL  ROWGUIDCOL  
  UNIQUE DEFAULT NEWID()  
)  
GO  
Insert into employees  
Values(1, 0x00, default)  
GO  
```  
  
### <a name="example-reading-overwriting-and-inserting-filestream-data"></a>Beispiel: Lesen, Überschreiben und Einfügen von FILESTREAM-Daten  
 Im folgenden Beispiel wird veranschaulicht, wie Daten aus einem FILESTREAM gelesen werden. Der Code ruft den logischen Pfad der Datei ab, wobei `FileAccess` auf `Read` und `FileOptions` auf `SequentialScan` gesetzt wird. Anschließend liest der Code die Bytes vom SqlFileStream in den Puffer. Die Bytes werden ins Konsolenfenster geschrieben.  
  
 Das Beispiel zeigt auch, wie Daten in einen FILESTREAM geschrieben werden, wobei alle vorhandenen Daten überschrieben werden. Der Code ruft den logischen Pfad der Datei ab und erstellt den `SqlFileStream`, wobei `FileAccess` auf `Write` und `FileOptions` auf `SequentialScan` gesetzt werden. Ein einzelnes Byte wird in den `SqlFileStream` geschrieben und ersetzt alle Daten in der Datei.  
  
 Das Beispiel veranschaulicht zusätzlich, wie Daten unter Verwendung der Seek-Methode in einen FILESTREAM geschrieben werden, wobei die Daten am Ende der Datei angefügt werden. Der Code ruft den logischen Pfad der Datei ab und erstellt den `SqlFileStream`, wobei `FileAccess` auf `ReadWrite` und `FileOptions` auf `SequentialScan` gesetzt werden. Der Code verwendet die "Seek"-Methode, um das Ende der Datei zu suchen und an die vorhandene Datei ein einzelnes Byte anzuhängen.  
  
```csharp  
using System;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using System.Data;  
using System.IO;  
  
namespace FileStreamTest  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            SqlConnectionStringBuilder builder = new SqlConnectionStringBuilder("server=(local);integrated security=true;database=myDB");  
            ReadFilestream(builder);  
            OverwriteFilestream(builder);  
            InsertFilestream(builder);  
  
            Console.WriteLine("Done");  
        }  
  
        private static void ReadFilestream(SqlConnectionStringBuilder connStringBuilder)  
        {  
            using (SqlConnection connection = new SqlConnection(connStringBuilder.ToString()))  
            {  
                connection.Open();  
                SqlCommand command = new SqlCommand("SELECT TOP(1) Photo.PathName(), GET_FILESTREAM_TRANSACTION_CONTEXT() FROM employees", connection);  
  
                SqlTransaction tran = connection.BeginTransaction(IsolationLevel.ReadCommitted);  
                command.Transaction = tran;  
  
                using (SqlDataReader reader = command.ExecuteReader())  
                {  
                    while (reader.Read())  
                    {  
                        // Get the pointer for the file  
                        string path = reader.GetString(0);  
                        byte[] transactionContext = reader.GetSqlBytes(1).Buffer;  
  
                        // Create the SqlFileStream  
                        using (Stream fileStream = new SqlFileStream(path, transactionContext, FileAccess.Read, FileOptions.SequentialScan, allocationSize: 0))  
                        {  
                            // Read the contents as bytes and write them to the console  
                            for (long index = 0; index < fileStream.Length; index++)  
                            {  
                                Console.WriteLine(fileStream.ReadByte());  
                            }  
                        }  
                    }  
                }  
                tran.Commit();  
            }  
        }  
  
        private static void OverwriteFilestream(SqlConnectionStringBuilder connStringBuilder)  
        {  
            using (SqlConnection connection = new SqlConnection(connStringBuilder.ToString()))  
            {  
                connection.Open();  
  
                SqlCommand command = new SqlCommand("SELECT TOP(1) Photo.PathName(), GET_FILESTREAM_TRANSACTION_CONTEXT() FROM employees", connection);  
  
                SqlTransaction tran = connection.BeginTransaction(IsolationLevel.ReadCommitted);  
                command.Transaction = tran;  
  
                using (SqlDataReader reader = command.ExecuteReader())  
                {  
                    while (reader.Read())  
                    {  
                        // Get the pointer for file   
                        string path = reader.GetString(0);  
                        byte[] transactionContext = reader.GetSqlBytes(1).Buffer;  
  
                        // Create the SqlFileStream  
                        using (Stream fileStream = new SqlFileStream(path, transactionContext, FileAccess.Write, FileOptions.SequentialScan, allocationSize: 0))  
                        {  
                            // Write a single byte to the file. This will  
                            // replace any data in the file.  
                            fileStream.WriteByte(0x01);  
                        }  
                    }  
                }  
                tran.Commit();  
            }  
        }  
  
        private static void InsertFilestream(SqlConnectionStringBuilder connStringBuilder)  
        {  
            using (SqlConnection connection = new SqlConnection(connStringBuilder.ToString()))  
            {  
                connection.Open();  
  
                SqlCommand command = new SqlCommand("SELECT TOP(1) Photo.PathName(), GET_FILESTREAM_TRANSACTION_CONTEXT() FROM employees", connection);  
  
                SqlTransaction tran = connection.BeginTransaction(IsolationLevel.ReadCommitted);  
                command.Transaction = tran;  
  
                using (SqlDataReader reader = command.ExecuteReader())  
                {  
                    while (reader.Read())  
                    {  
                        // Get the pointer for file  
                        string path = reader.GetString(0);  
                        byte[] transactionContext = reader.GetSqlBytes(1).Buffer;  
  
                        using (Stream fileStream = new SqlFileStream(path, transactionContext, FileAccess.ReadWrite, FileOptions.SequentialScan, allocationSize: 0))  
                        {  
                            // Seek to the end of the file  
                            fileStream.Seek(0, SeekOrigin.End);  
  
                            // Append a single byte   
                            fileStream.WriteByte(0x01);  
                        }  
                    }  
                }  
                tran.Commit();  
            }  
  
        }  
    }  
}
```  
  
 Ein weiteres Beispiel finden Sie unter [speichern und Abrufen von Binärdaten in einer FileStream-Spalte](http://www.codeproject.com/Articles/32216/How-to-store-and-fetch-binary-data-into-a-file-str).  
  
## <a name="resources-in-sql-server-books-online"></a>Ressourcen in der SQL Server-Onlinedokumentation.  
 Die vollständige Dokumentation für FILESTREAM befindet sich in den folgenden Abschnitten in SQL Server-Onlinedokumentation.  
  
|Thema|Beschreibung|  
|-----------|-----------------|  
|[Entwerfen und Implementieren der FILESTREAM-Speicherung](http://msdn2.microsoft.com/library/bb895234\(SQL.105\).aspx)|Stellt Links zur FILESTREAM-Dokumentation und verwandten Themen bereit.|  
|[Übersicht über FILESTREAM](http://msdn2.microsoft.com/library/bb933993\(SQL.105\).aspx)|Beschreibt, in welchen Fällen die FILESTREAM-Speicherung verwendet werden sollte und wie diese das SQL Server-Datenbankmodul mit einem NTFS-Dateisystem integriert.|  
|[Erste Schritte mit FILESTREAM-Speicherung](https://msdn.microsoft.com/library/bb933995\(SQL.105\).aspx)|Beschreibt, wie FILESTREAM für eine Instanz von SQL Server aktiviert wird, wie eine Datenbank und eine Tabelle zum Speichern von FILESTREAM-Daten erstellt werden und wie Zeilen mit FILESTREAM-Daten bearbeitet werden.|  
|[Verwenden von FILESTREAM-Speicherung in Clientanwendungen](https://msdn.microsoft.com/library/bb933877\(SQL.105\).aspx)|Beschreibt die Win32 API-Funktionen zum Arbeiten mit FILESTREAM-Daten.|  
|[FILESTREAM und andere SQL Server-Funktionen](/sql/relational-databases/blob/filestream-compatibility-with-other-sql-server-features)|Enthält Überlegungen, Richtlinien und Einschränkungen zur Verwendung von FILESTREAM-Daten mit anderen Funktionen von SQL Server.|  
  
## <a name="see-also"></a>Siehe auch  
 [SQL Server Data Types and ADO.NET (SQL Server-Datentypen und ADO.NET)](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 [Abrufen und Ändern von Daten in ADO.NET](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [Codezugriffssicherheit und ADO.NET](../../../../../docs/framework/data/adonet/code-access-security.md)  
 [SQL Server Binary and Large-Value Data (Binäre Daten und Daten mit umfangreichen Werten in SQL Server)](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
