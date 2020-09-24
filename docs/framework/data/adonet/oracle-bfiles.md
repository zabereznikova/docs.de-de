---
title: Oracle-BFILEs
ms.date: 03/30/2017
ms.assetid: 341bbf84-4734-4d44-8723-ccedee954e21
ms.openlocfilehash: d43dfccd9735ce1ab822d7b14de2abaa0940c77b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166598"
---
# <a name="oracle-bfiles"></a><span data-ttu-id="f53d0-102">Oracle-BFILEs</span><span class="sxs-lookup"><span data-stu-id="f53d0-102">Oracle BFILEs</span></span>

<span data-ttu-id="f53d0-103">Der .NET Framework-Datenanbieter für Oracle enthält die <xref:System.Data.OracleClient.OracleBFile>-Klasse, die für das Arbeiten mit dem Oracle-<xref:System.Data.OracleClient.OracleType.BFile>-Datentyp verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f53d0-103">The .NET Framework Data Provider for Oracle includes the <xref:System.Data.OracleClient.OracleBFile> class, which is used to work with the Oracle <xref:System.Data.OracleClient.OracleType.BFile> data type.</span></span>  
  
 <span data-ttu-id="f53d0-104">Der Oracle **BFILE** -Datentyp ist ein Oracle- **LOB** -Datentyp, der einen Verweis auf Binärdaten mit einer maximalen Größe von 4 Gigabyte enthält.</span><span class="sxs-lookup"><span data-stu-id="f53d0-104">The Oracle **BFILE** data type is an Oracle **LOB** data type that contains a reference to binary data with a maximum size of 4 gigabytes.</span></span> <span data-ttu-id="f53d0-105">Eine Oracle **BFILE** unterscheidet sich von anderen Oracle- **LOB** -Datentypen darin, dass die Daten in einer physischen Datei im Betriebssystem und nicht auf dem Server gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="f53d0-105">An Oracle **BFILE** differs from other Oracle **LOB** data types in that its data is stored in a physical file in the operating system instead of on the server.</span></span> <span data-ttu-id="f53d0-106">Beachten Sie, dass der **BFILE** -Datentyp schreibgeschützten Zugriff auf Daten bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="f53d0-106">Note that the **BFILE** data type provides read-only access to data.</span></span>  
  
 <span data-ttu-id="f53d0-107">Andere Merkmale eines **BFILE** -Datentyps, die ihn von einem **LOB** -Datentyp unterscheiden, sind folgende:</span><span class="sxs-lookup"><span data-stu-id="f53d0-107">Other characteristics of a **BFILE** data type that distinguish it from a **LOB** data type are that it:</span></span>  
  
- <span data-ttu-id="f53d0-108">Er enthält unstrukturierte Daten.</span><span class="sxs-lookup"><span data-stu-id="f53d0-108">Contains unstructured data.</span></span>  
  
- <span data-ttu-id="f53d0-109">Er unterstützt das serverseitige Aufteilen in kleine Blöcke.</span><span class="sxs-lookup"><span data-stu-id="f53d0-109">Supports server-side chunking.</span></span>  
  
- <span data-ttu-id="f53d0-110">Er verwendet die Semantik zum Kopieren von Verweisen.</span><span class="sxs-lookup"><span data-stu-id="f53d0-110">Uses reference copy semantics.</span></span> <span data-ttu-id="f53d0-111">Wenn Sie z. b. einen Kopiervorgang für eine **BFILE**ausführen, wird nur der **BFILE** -Serverlocatorpunkt (ein Verweis auf die Datei) kopiert.</span><span class="sxs-lookup"><span data-stu-id="f53d0-111">For example, if you perform a copy operation on a **BFILE**, only the **BFILE** locator (which is a reference to the file) is copied.</span></span> <span data-ttu-id="f53d0-112">Die Daten in der Datei werden nicht kopiert.</span><span class="sxs-lookup"><span data-stu-id="f53d0-112">The data in the file is not copied.</span></span>  
  
 <span data-ttu-id="f53d0-113">Der **BFILE** -Datentyp sollte verwendet werden, um auf Lob zu verweisen, die groß sind und daher nicht in der Datenbank gespeichert werden können.</span><span class="sxs-lookup"><span data-stu-id="f53d0-113">The **BFILE** data type should be used for referencing LOBs that are large in size, and therefore, not practical to store in the database.</span></span> <span data-ttu-id="f53d0-114">Bei Verwendung eines **BFILE** -Datentyps im Vergleich zum **LOB** -Datentyp ist mehr Client-, Server-und Kommunikationsaufwand betroffen.</span><span class="sxs-lookup"><span data-stu-id="f53d0-114">More client, server, and communication overhead is involved when using a **BFILE** data type compared with the **LOB** data type.</span></span> <span data-ttu-id="f53d0-115">Es ist effizienter, auf eine **BFILE** zuzugreifen, wenn Sie nur eine kleine Datenmenge abrufen müssen.</span><span class="sxs-lookup"><span data-stu-id="f53d0-115">It is more efficient to access a **BFILE** if you only need to obtain a small amount of data.</span></span> <span data-ttu-id="f53d0-116">Es ist effektiver, auf datenbankresidente LOBs zuzugreifen, wenn das ganze Objekt abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="f53d0-116">It is more efficient to access database-resident LOBs if you need to obtain the entire object.</span></span>  
  
 <span data-ttu-id="f53d0-117">Jedes **OracleBFile** -Objekt, das nicht NULL ist, ist zwei Entitäten zugeordnet, die den Speicherort der zugrunde liegenden physischen Datei definieren:</span><span class="sxs-lookup"><span data-stu-id="f53d0-117">Each non-NULL **OracleBFile** object is associated with two entities that define the location of the underlying physical file:</span></span>  
  
1. <span data-ttu-id="f53d0-118">Ein Oracle-DIRECTORY-Objekt, das als Datenbank-Alias für ein Verzeichnis im Dateisystem fungiert.</span><span class="sxs-lookup"><span data-stu-id="f53d0-118">An Oracle DIRECTORY object, which is a database alias for a directory in the file system, and</span></span>  
  
2. <span data-ttu-id="f53d0-119">Der Dateiname der zugrunde liegenden physischen Datei, die sich in dem dem DIRECTORY-Objekt zugeordneten Verzeichnis befindet.</span><span class="sxs-lookup"><span data-stu-id="f53d0-119">The file name of the underlying physical file, which is located in the directory associated with the DIRECTORY object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f53d0-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f53d0-120">Example</span></span>  

 <span data-ttu-id="f53d0-121">Im folgenden c#-Beispiel wird veranschaulicht, wie Sie eine **BFILE** in einer Oracle-Tabelle erstellen und dann in Form eines **OracleBFile** -Objekts abrufen können.</span><span class="sxs-lookup"><span data-stu-id="f53d0-121">The following C# example demonstrates how you can create a **BFILE** in an Oracle table and then retrieve it in the form of an **OracleBFile** object.</span></span> <span data-ttu-id="f53d0-122">Das Beispiel veranschaulicht die Verwendung des <xref:System.Data.OracleClient.OracleDataReader> -Objekts und der **OracleBFile** -Methode zum **Suchen** und **Lesen** .</span><span class="sxs-lookup"><span data-stu-id="f53d0-122">The example demonstrates using the <xref:System.Data.OracleClient.OracleDataReader> object and the **OracleBFile** **Seek** and **Read** methods.</span></span> <span data-ttu-id="f53d0-123">Beachten Sie Folgendes: um dieses Beispiel zu verwenden, müssen Sie zuerst ein Verzeichnis mit dem Namen "c: \\ \bfiles" und eine Datei mit dem Namen "MyFile.jpg" auf dem Oracle-Server erstellen.</span><span class="sxs-lookup"><span data-stu-id="f53d0-123">Note that in order to use this sample, you must first create a directory named "c:\\\bfiles" and file named "MyFile.jpg" on the Oracle server.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f53d0-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f53d0-124">See also</span></span>

- [<span data-ttu-id="f53d0-125">Oracle und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f53d0-125">Oracle and ADO.NET</span></span>](oracle-and-adonet.md)
- [<span data-ttu-id="f53d0-126">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f53d0-126">ADO.NET Overview</span></span>](ado-net-overview.md)
