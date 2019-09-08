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
# <a name="filestream-data"></a><span data-ttu-id="36177-102">FILESTREAM-Daten</span><span class="sxs-lookup"><span data-stu-id="36177-102">FILESTREAM Data</span></span>

<span data-ttu-id="36177-103">Das FILESTREAM-Speicherattribut wird für Binärdaten (BLOBs) verwendet, die in einer varbinary(max)-Spalte gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="36177-103">The FILESTREAM storage attribute is for binary (BLOB) data stored in a varbinary(max) column.</span></span> <span data-ttu-id="36177-104">Vor FILESTREAM erforderte das Speichern von Binärdaten besondere Maßnahmen.</span><span class="sxs-lookup"><span data-stu-id="36177-104">Before FILESTREAM, storing binary data required special handling.</span></span> <span data-ttu-id="36177-105">Unstrukturierte Daten wie z. B. Textdokumente, Bilder und Videos werden häufig außerhalb der Datenbank gespeichert und sind daher schwieriger zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="36177-105">Unstructured data, such as text documents, images and video, is often stored outside of the database, making it difficult to manage.</span></span>

> [!NOTE]
> <span data-ttu-id="36177-106">Sie müssen .NET Framework 3.5 SP1 (oder höher) installieren, um mithilfe von SqlClient mit FILESTREAM-Daten zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="36177-106">You must install the .NET Framework 3.5 SP1 (or later) to work with FILESTREAM data using SqlClient.</span></span>

<span data-ttu-id="36177-107">Wenn das FILESTREAM-Attribut für eine varbinary(max)-Spalte festgelegt ist, werden die Daten von SQL Server im lokalen NTFS-Dateisystem und nicht in der Datenbankdatei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="36177-107">Specifying the FILESTREAM attribute on a varbinary(max) column causes SQL Server to store the data on the local NTFS file system instead of in the database file.</span></span> <span data-ttu-id="36177-108">Obwohl die Speicherung separat erfolgt, können dieselben Transact-SQL-Anweisungen verwendet werden, die für das Arbeiten mit in der Datenbank gespeicherten varbinary(max)-Daten unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="36177-108">Although it is stored separately, you can use the same Transact-SQL statements that are supported for working with varbinary(max) data that is stored in the database.</span></span>

## <a name="sqlclient-support-for-filestream"></a><span data-ttu-id="36177-109">SqlClient-Unterstützung für FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="36177-109">SqlClient Support for FILESTREAM</span></span>

<span data-ttu-id="36177-110">Die .NET Framework Datenanbieter für SQL Server, <xref:System.Data.SqlClient>, unterstützt das Lesen und Schreiben von FILESTREAM- <xref:System.Data.SqlTypes.SqlFileStream> Daten mithilfe der im <xref:System.Data.SqlTypes> -Namespace definierten-Klasse.</span><span class="sxs-lookup"><span data-stu-id="36177-110">The .NET Framework Data Provider for SQL Server, <xref:System.Data.SqlClient>, supports reading and writing to FILESTREAM data using the <xref:System.Data.SqlTypes.SqlFileStream> class defined in the <xref:System.Data.SqlTypes> namespace.</span></span> <span data-ttu-id="36177-111">`SqlFileStream` erbt von der <xref:System.IO.Stream>-Klasse, die Methoden zum Lesen und Schreiben der Datenströme bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="36177-111">`SqlFileStream` inherits from the <xref:System.IO.Stream> class, which provides methods for reading and writing to streams of data.</span></span> <span data-ttu-id="36177-112">Beim Lesen aus einem Strom werden die Daten vom Strom in eine Datenstruktur übertragen, z. B. in ein Bytearray.</span><span class="sxs-lookup"><span data-stu-id="36177-112">Reading from a stream transfers data from the stream into a data structure, such as an array of bytes.</span></span> <span data-ttu-id="36177-113">Beim Schreiben werden die Daten von einer Datenstruktur in einen Strom übertragen.</span><span class="sxs-lookup"><span data-stu-id="36177-113">Writing transfers the data from the data structure into a stream.</span></span>

### <a name="creating-the-sql-server-table"></a><span data-ttu-id="36177-114">Erstellen der SQL Server-Tabelle</span><span class="sxs-lookup"><span data-stu-id="36177-114">Creating the SQL Server Table</span></span>

<span data-ttu-id="36177-115">Mit den folgenden Transact-SQL-Anweisungen wird eine Tabelle mit dem Namen "employees" erstellt und eine Datenzeile eingefügt.</span><span class="sxs-lookup"><span data-stu-id="36177-115">The following Transact-SQL statements creates a table named employees and inserts a row of data.</span></span> <span data-ttu-id="36177-116">Wenn die FILESTREAM-Speicherung aktiviert wurde, kann diese Tabelle gemeinsam mit den folgenden Codebeispielen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="36177-116">Once you have enabled FILESTREAM storage, you can use this table in conjunction with the code examples that follow.</span></span> <span data-ttu-id="36177-117">Die Links zu Ressourcen in SQL Server-Onlinedokumentation befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="36177-117">The links to resources in SQL Server Books Online are located at the end of this topic.</span></span>

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

### <a name="example-reading-overwriting-and-inserting-filestream-data"></a><span data-ttu-id="36177-118">Beispiel: Lesen, überschreiben und Einfügen von FILESTREAM-Daten</span><span class="sxs-lookup"><span data-stu-id="36177-118">Example: Reading, Overwriting, and Inserting FILESTREAM Data</span></span>

<span data-ttu-id="36177-119">Im folgenden Beispiel wird veranschaulicht, wie Daten aus einem FILESTREAM gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="36177-119">The following sample demonstrates how to read data from a FILESTREAM.</span></span> <span data-ttu-id="36177-120">Der Code ruft den logischen Pfad der Datei ab, wobei `FileAccess` auf `Read` und `FileOptions` auf `SequentialScan` gesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="36177-120">The code gets the logical path to the file, setting the `FileAccess` to `Read` and the `FileOptions` to `SequentialScan`.</span></span> <span data-ttu-id="36177-121">Anschließend liest der Code die Bytes vom SqlFileStream in den Puffer.</span><span class="sxs-lookup"><span data-stu-id="36177-121">The code then reads the bytes from the SqlFileStream into the buffer.</span></span> <span data-ttu-id="36177-122">Die Bytes werden ins Konsolenfenster geschrieben.</span><span class="sxs-lookup"><span data-stu-id="36177-122">The bytes are then written to the console window.</span></span>

<span data-ttu-id="36177-123">Das Beispiel zeigt auch, wie Daten in einen FILESTREAM geschrieben werden, wobei alle vorhandenen Daten überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="36177-123">The sample also demonstrates how to write data to a FILESTREAM in which all existing data is overwritten.</span></span> <span data-ttu-id="36177-124">Der Code ruft den logischen Pfad der Datei ab und erstellt den `SqlFileStream`, wobei `FileAccess` auf `Write` und `FileOptions` auf `SequentialScan` gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="36177-124">The code gets the logical path to the file and creates the `SqlFileStream`, setting the `FileAccess` to `Write` and the `FileOptions` to `SequentialScan`.</span></span> <span data-ttu-id="36177-125">Ein einzelnes Byte wird in den `SqlFileStream` geschrieben und ersetzt alle Daten in der Datei.</span><span class="sxs-lookup"><span data-stu-id="36177-125">A single byte is written to the `SqlFileStream`, replacing any data in the file.</span></span>

<span data-ttu-id="36177-126">Das Beispiel veranschaulicht zusätzlich, wie Daten unter Verwendung der Seek-Methode in einen FILESTREAM geschrieben werden, wobei die Daten am Ende der Datei angefügt werden.</span><span class="sxs-lookup"><span data-stu-id="36177-126">The sample also demonstrates how to write data to a FILESTREAM by using the Seek method to append data to the end of the file.</span></span> <span data-ttu-id="36177-127">Der Code ruft den logischen Pfad der Datei ab und erstellt den `SqlFileStream`, wobei `FileAccess` auf `ReadWrite` und `FileOptions` auf `SequentialScan` gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="36177-127">The code gets the logical path to the file and creates the `SqlFileStream`, setting the `FileAccess` to `ReadWrite` and the `FileOptions` to `SequentialScan`.</span></span> <span data-ttu-id="36177-128">Der Code verwendet die "Seek"-Methode, um das Ende der Datei zu suchen und an die vorhandene Datei ein einzelnes Byte anzuhängen.</span><span class="sxs-lookup"><span data-stu-id="36177-128">The code uses the Seek method to seek to the end of the file, appending a single byte to the existing file.</span></span>

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

<span data-ttu-id="36177-129">Ein weiteres Beispiel finden Sie unter Gewusst [wie: Speichern und Abrufen von Binärdaten in einer Dateistream-Spalte](https://www.codeproject.com/Articles/32216/How-to-store-and-fetch-binary-data-into-a-file-str).</span><span class="sxs-lookup"><span data-stu-id="36177-129">For another sample, see [How to store and fetch binary data into a file stream column](https://www.codeproject.com/Articles/32216/How-to-store-and-fetch-binary-data-into-a-file-str).</span></span>

## <a name="resources-in-sql-server-books-online"></a><span data-ttu-id="36177-130">Ressourcen in der SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="36177-130">Resources in SQL Server Books Online</span></span>

<span data-ttu-id="36177-131">Die komplette Dokumentation für FILESTREAM finden Sie in den folgenden Abschnitten SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="36177-131">The complete documentation for FILESTREAM is located in the following sections in SQL Server Books Online.</span></span>

|<span data-ttu-id="36177-132">Thema</span><span class="sxs-lookup"><span data-stu-id="36177-132">Topic</span></span>|<span data-ttu-id="36177-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="36177-133">Description</span></span>|
|-----------|-----------------|
|[<span data-ttu-id="36177-134">FileStream (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="36177-134">FILESTREAM (SQL Server)</span></span>](/sql/relational-databases/blob/filestream-sql-server)|<span data-ttu-id="36177-135">Beschreibt, in welchen Fällen die FILESTREAM-Speicherung verwendet werden sollte und wie diese die SQL Server-Datenbank-Engine mit einem NTFS-Dateisystem integriert.</span><span class="sxs-lookup"><span data-stu-id="36177-135">Describes when to use FILESTREAM storage and how it integrates the SQL Server Database Engine with an NTFS file system.</span></span>|
|[<span data-ttu-id="36177-136">Erstellen von Client Anwendungen für FILESTREAM-Daten</span><span class="sxs-lookup"><span data-stu-id="36177-136">Create Client Applications for FILESTREAM Data</span></span>](/sql/relational-databases/blob/create-client-applications-for-filestream-data)|<span data-ttu-id="36177-137">Beschreibt die Funktionen der Windows-API zum Arbeiten mit FILESTREAM-Daten.</span><span class="sxs-lookup"><span data-stu-id="36177-137">Describes the Windows API functions for working with FILESTREAM data.</span></span>|
|[<span data-ttu-id="36177-138">FILESTREAM und andere SQL Server Features</span><span class="sxs-lookup"><span data-stu-id="36177-138">FILESTREAM and Other SQL Server Features</span></span>](/sql/relational-databases/blob/filestream-compatibility-with-other-sql-server-features)|<span data-ttu-id="36177-139">Enthält Überlegungen, Richtlinien und Einschränkungen zur Verwendung von FILESTREAM-Daten mit anderen Funktionen von SQL Server.</span><span class="sxs-lookup"><span data-stu-id="36177-139">Provides considerations, guidelines and limitations for using FILESTREAM data with other features of SQL Server.</span></span>|

## <a name="see-also"></a><span data-ttu-id="36177-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="36177-140">See also</span></span>

- [<span data-ttu-id="36177-141">SQL Server Data Types and ADO.NET (SQL Server-Datentypen und ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="36177-141">SQL Server Data Types and ADO.NET</span></span>](sql-server-data-types.md)
- [<span data-ttu-id="36177-142">Abrufen und Ändern von Daten in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="36177-142">Retrieving and Modifying Data in ADO.NET</span></span>](../retrieving-and-modifying-data.md)
- [<span data-ttu-id="36177-143">Codezugriffssicherheit und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="36177-143">Code Access Security and ADO.NET</span></span>](../code-access-security.md)
- [<span data-ttu-id="36177-144">SQL Server Binary and Large-Value Data (Binäre Daten und Daten mit umfangreichen Werten in SQL Server)</span><span class="sxs-lookup"><span data-stu-id="36177-144">SQL Server Binary and Large-Value Data</span></span>](sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="36177-145">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="36177-145">ADO.NET Overview</span></span>](../ado-net-overview.md)
