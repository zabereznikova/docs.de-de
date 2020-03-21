---
title: Oracle-BFILEs
ms.date: 03/30/2017
ms.assetid: 341bbf84-4734-4d44-8723-ccedee954e21
ms.openlocfilehash: 40060a7ea8576e08140d972072d086606d640366
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149439"
---
# <a name="oracle-bfiles"></a><span data-ttu-id="c9968-102">Oracle-BFILEs</span><span class="sxs-lookup"><span data-stu-id="c9968-102">Oracle BFILEs</span></span>
<span data-ttu-id="c9968-103">Der .NET Framework-Datenanbieter für Oracle enthält die <xref:System.Data.OracleClient.OracleBFile>-Klasse, die für das Arbeiten mit dem Oracle-<xref:System.Data.OracleClient.OracleType.BFile>-Datentyp verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c9968-103">The .NET Framework Data Provider for Oracle includes the <xref:System.Data.OracleClient.OracleBFile> class, which is used to work with the Oracle <xref:System.Data.OracleClient.OracleType.BFile> data type.</span></span>  
  
 <span data-ttu-id="c9968-104">Der Oracle **BFILE-Datentyp** ist ein Oracle LOB-Datentyp, der einen Verweis auf Binärdaten mit einer maximalen Größe von 4 Gigabyte enthält. **LOB**</span><span class="sxs-lookup"><span data-stu-id="c9968-104">The Oracle **BFILE** data type is an Oracle **LOB** data type that contains a reference to binary data with a maximum size of 4 gigabytes.</span></span> <span data-ttu-id="c9968-105">Ein Oracle **BFILE** unterscheidet sich von anderen Oracle **LOB-Datentypen** dadurch, dass seine Daten in einer physischen Datei im Betriebssystem und nicht auf dem Server gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="c9968-105">An Oracle **BFILE** differs from other Oracle **LOB** data types in that its data is stored in a physical file in the operating system instead of on the server.</span></span> <span data-ttu-id="c9968-106">Beachten Sie, dass der **BFILE-Datentyp** schreibgeschützten Zugriff auf Daten bietet.</span><span class="sxs-lookup"><span data-stu-id="c9968-106">Note that the **BFILE** data type provides read-only access to data.</span></span>  
  
 <span data-ttu-id="c9968-107">Andere Merkmale eines BFILE-Datentyps, die ihn von einem **Branchendatentyp** unterscheiden, sind: **BFILE**</span><span class="sxs-lookup"><span data-stu-id="c9968-107">Other characteristics of a **BFILE** data type that distinguish it from a **LOB** data type are that it:</span></span>  
  
- <span data-ttu-id="c9968-108">Er enthält unstrukturierte Daten.</span><span class="sxs-lookup"><span data-stu-id="c9968-108">Contains unstructured data.</span></span>  
  
- <span data-ttu-id="c9968-109">Er unterstützt das serverseitige Aufteilen in kleine Blöcke.</span><span class="sxs-lookup"><span data-stu-id="c9968-109">Supports server-side chunking.</span></span>  
  
- <span data-ttu-id="c9968-110">Er verwendet die Semantik zum Kopieren von Verweisen.</span><span class="sxs-lookup"><span data-stu-id="c9968-110">Uses reference copy semantics.</span></span> <span data-ttu-id="c9968-111">Wenn Sie z. B. einen Kopiervorgang für eine **BFILE**ausführen, wird nur der **BFILE-Locator** (der ein Verweis auf die Datei ist) kopiert.</span><span class="sxs-lookup"><span data-stu-id="c9968-111">For example, if you perform a copy operation on a **BFILE**, only the **BFILE** locator (which is a reference to the file) is copied.</span></span> <span data-ttu-id="c9968-112">Die Daten in der Datei werden nicht kopiert.</span><span class="sxs-lookup"><span data-stu-id="c9968-112">The data in the file is not copied.</span></span>  
  
 <span data-ttu-id="c9968-113">Der **BFILE-Datentyp** sollte für den Verweis auf große LOBs verwendet werden, die daher nicht in der Datenbank gespeichert werden können.</span><span class="sxs-lookup"><span data-stu-id="c9968-113">The **BFILE** data type should be used for referencing LOBs that are large in size, and therefore, not practical to store in the database.</span></span> <span data-ttu-id="c9968-114">Bei der Verwendung eines **BFILE-Datentyps** im Vergleich zum **Branchendatentyp** ist ein mehr Client-, Server- und Kommunikationsaufwand erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c9968-114">More client, server, and communication overhead is involved when using a **BFILE** data type compared with the **LOB** data type.</span></span> <span data-ttu-id="c9968-115">Es ist effizienter, auf eine **BFILE** zuzugreifen, wenn Sie nur eine kleine Datenmenge abrufen müssen.</span><span class="sxs-lookup"><span data-stu-id="c9968-115">It is more efficient to access a **BFILE** if you only need to obtain a small amount of data.</span></span> <span data-ttu-id="c9968-116">Es ist effektiver, auf datenbankresidente LOBs zuzugreifen, wenn das ganze Objekt abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="c9968-116">It is more efficient to access database-resident LOBs if you need to obtain the entire object.</span></span>  
  
 <span data-ttu-id="c9968-117">Jedes **Nicht-NULL-OracleBFile-Objekt** ist zwei Entitäten zugeordnet, die den Speicherort der zugrunde liegenden physischen Datei definieren:</span><span class="sxs-lookup"><span data-stu-id="c9968-117">Each non-NULL **OracleBFile** object is associated with two entities that define the location of the underlying physical file:</span></span>  
  
1. <span data-ttu-id="c9968-118">Ein Oracle-DIRECTORY-Objekt, das als Datenbank-Alias für ein Verzeichnis im Dateisystem fungiert.</span><span class="sxs-lookup"><span data-stu-id="c9968-118">An Oracle DIRECTORY object, which is a database alias for a directory in the file system, and</span></span>  
  
2. <span data-ttu-id="c9968-119">Der Dateiname der zugrunde liegenden physischen Datei, die sich in dem dem DIRECTORY-Objekt zugeordneten Verzeichnis befindet.</span><span class="sxs-lookup"><span data-stu-id="c9968-119">The file name of the underlying physical file, which is located in the directory associated with the DIRECTORY object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c9968-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c9968-120">Example</span></span>  
 <span data-ttu-id="c9968-121">Im folgenden Beispiel wird veranschaulicht, wie Sie eine **BFILE** in einer Oracle-Tabelle erstellen und sie dann in Form eines **OracleBFile-Objekts** abrufen können.</span><span class="sxs-lookup"><span data-stu-id="c9968-121">The following C# example demonstrates how you can create a **BFILE** in an Oracle table and then retrieve it in the form of an **OracleBFile** object.</span></span> <span data-ttu-id="c9968-122">Das Beispiel veranschaulicht <xref:System.Data.OracleClient.OracleDataReader> die Verwendung des Objekts und der **OracleBFile** **Seek** and **Read-Methoden.**</span><span class="sxs-lookup"><span data-stu-id="c9968-122">The example demonstrates using the <xref:System.Data.OracleClient.OracleDataReader> object and the **OracleBFile** **Seek** and **Read** methods.</span></span> <span data-ttu-id="c9968-123">Beachten Sie, dass Sie, um dieses Beispiel verwenden zu\\können, zunächst ein Verzeichnis mit dem Namen "c: 'bfiles" und die Datei mit dem Namen "MyFile.jpg' auf dem Oracle-Server erstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="c9968-123">Note that in order to use this sample, you must first create a directory named "c:\\\bfiles" and file named "MyFile.jpg" on the Oracle server.</span></span>  
  
```csharp  
using System;  
using System.IO;  
using System.Data;  
using System.Data.OracleClient;  
  
public class Sample  
{  
   public static void Main(string[] args)  
   {  
      OracleConnection connection = new OracleConnection(  
        "Data Source=Oracle8i;Integrated Security=yes");  
      connection.Open();  
  
      OracleCommand command = connection.CreateCommand();  
      command.CommandText =
        "CREATE or REPLACE DIRECTORY MyDir as 'c:\\bfiles'";  
      command.ExecuteNonQuery();  
      command.CommandText =
        "DROP TABLE MyBFileTable";  
      try {  
        command.ExecuteNonQuery();  
      }  
      catch {  
      }  
      command.CommandText =
        "CREATE TABLE MyBFileTable(col1 number, col2 BFILE)";  
      command.ExecuteNonQuery();  
      command.CommandText =
        "INSERT INTO MyBFileTable values ('2', BFILENAME('MyDir', " +  
        "'MyFile.jpg'))";  
      command.ExecuteNonQuery();  
      command.CommandText = "SELECT * FROM MyBFileTable";  
  
        byte[] buffer = new byte[100];  
  
      OracleDataReader reader = command.ExecuteReader();  
      using (reader) {  
          if (reader.Read()) {  
                OracleBFile bFile = reader.GetOracleBFile(1);  
                using (bFile) {  
                  bFile.Seek(0, SeekOrigin.Begin);  
                  bFile.Read(buffer, 0, 100);  
              }  
          }  
      }  
  
      connection.Close();  
   }  
  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="c9968-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c9968-124">See also</span></span>

- [<span data-ttu-id="c9968-125">Oracle und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c9968-125">Oracle and ADO.NET</span></span>](oracle-and-adonet.md)
- [<span data-ttu-id="c9968-126">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c9968-126">ADO.NET Overview</span></span>](ado-net-overview.md)
