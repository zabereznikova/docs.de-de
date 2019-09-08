---
title: FILESTREAM-Daten
ms.date: 03/30/2017
ms.assetid: bd8b845c-0f09-4295-b466-97ef106eefa8
ms.openlocfilehash: 87bed5dd345c240cc00b2c36aa976ec53fe63b93
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794095"
---
# <a name="filestream-data"></a>FILESTREAM-Daten

Das FILESTREAM-Speicherattribut wird für Binärdaten (BLOBs) verwendet, die in einer varbinary(max)-Spalte gespeichert sind. Vor FILESTREAM erforderte das Speichern von Binärdaten besondere Maßnahmen. Unstrukturierte Daten wie z. B. Textdokumente, Bilder und Videos werden häufig außerhalb der Datenbank gespeichert und sind daher schwieriger zu verwalten.

> [!NOTE]
> Sie müssen .NET Framework 3.5 SP1 (oder höher) installieren, um mithilfe von SqlClient mit FILESTREAM-Daten zu arbeiten.

Wenn das FILESTREAM-Attribut für eine varbinary(max)-Spalte festgelegt ist, werden die Daten von SQL Server im lokalen NTFS-Dateisystem und nicht in der Datenbankdatei gespeichert. Obwohl die Speicherung separat erfolgt, können dieselben Transact-SQL-Anweisungen verwendet werden, die für das Arbeiten mit in der Datenbank gespeicherten varbinary(max)-Daten unterstützt werden.

## <a name="sqlclient-support-for-filestream"></a>SqlClient-Unterstützung für FILESTREAM

Die .NET Framework Datenanbieter für SQL Server, <xref:System.Data.SqlClient>, unterstützt das Lesen und Schreiben von FILESTREAM- <xref:System.Data.SqlTypes.SqlFileStream> Daten mithilfe der im <xref:System.Data.SqlTypes> -Namespace definierten-Klasse. `SqlFileStream` erbt von der <xref:System.IO.Stream>-Klasse, die Methoden zum Lesen und Schreiben der Datenströme bereitstellt. Beim Lesen aus einem Strom werden die Daten vom Strom in eine Datenstruktur übertragen, z. B. in ein Bytearray. Beim Schreiben werden die Daten von einer Datenstruktur in einen Strom übertragen.

### <a name="creating-the-sql-server-table"></a>Erstellen der SQL Server-Tabelle

Mit den folgenden Transact-SQL-Anweisungen wird eine Tabelle mit dem Namen "employees" erstellt und eine Datenzeile eingefügt. Wenn die FILESTREAM-Speicherung aktiviert wurde, kann diese Tabelle gemeinsam mit den folgenden Codebeispielen verwendet werden. Die Links zu Ressourcen in SQL Server-Onlinedokumentation befinden sich am Ende dieses Themas.

```sql
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

### <a name="example-reading-overwriting-and-inserting-filestream-data"></a>Beispiel: Lesen, überschreiben und Einfügen von FILESTREAM-Daten

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
            ReadFileStream(builder);
            OverwriteFileStream(builder);
            InsertFileStream(builder);

            Console.WriteLine("Done");
        }

        private static void ReadFileStream(SqlConnectionStringBuilder connStringBuilder)
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

        private static void OverwriteFileStream(SqlConnectionStringBuilder connStringBuilder)
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

        private static void InsertFileStream(SqlConnectionStringBuilder connStringBuilder)
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

Ein weiteres Beispiel finden Sie unter Gewusst [wie: Speichern und Abrufen von Binärdaten in einer Dateistream-Spalte](https://www.codeproject.com/Articles/32216/How-to-store-and-fetch-binary-data-into-a-file-str).

## <a name="resources-in-sql-server-books-online"></a>Ressourcen in der SQL Server-Onlinedokumentation.

Die komplette Dokumentation für FILESTREAM finden Sie in den folgenden Abschnitten SQL Server-Onlinedokumentation.

|Thema|Beschreibung|
|-----------|-----------------|
|[FileStream (SQL Server)](/sql/relational-databases/blob/filestream-sql-server)|Beschreibt, in welchen Fällen die FILESTREAM-Speicherung verwendet werden sollte und wie diese die SQL Server-Datenbank-Engine mit einem NTFS-Dateisystem integriert.|
|[Erstellen von Client Anwendungen für FILESTREAM-Daten](/sql/relational-databases/blob/create-client-applications-for-filestream-data)|Beschreibt die Funktionen der Windows-API zum Arbeiten mit FILESTREAM-Daten.|
|[FILESTREAM und andere SQL Server Features](/sql/relational-databases/blob/filestream-compatibility-with-other-sql-server-features)|Enthält Überlegungen, Richtlinien und Einschränkungen zur Verwendung von FILESTREAM-Daten mit anderen Funktionen von SQL Server.|

## <a name="see-also"></a>Siehe auch

- [SQL Server Data Types and ADO.NET (SQL Server-Datentypen und ADO.NET)](sql-server-data-types.md)
- [Abrufen und Ändern von Daten in ADO.NET](../retrieving-and-modifying-data.md)
- [Codezugriffssicherheit und ADO.NET](../code-access-security.md)
- [SQL Server Binary and Large-Value Data (Binäre Daten und Daten mit umfangreichen Werten in SQL Server)](sql-server-binary-and-large-value-data.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
