---
title: Oracle-BFILEs
ms.date: 03/30/2017
ms.assetid: 341bbf84-4734-4d44-8723-ccedee954e21
ms.openlocfilehash: 683b4a9be826e1d0d4ee354fada10168d833e3d7
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43398789"
---
# <a name="oracle-bfiles"></a><span data-ttu-id="a0b80-102">Oracle-BFILEs</span><span class="sxs-lookup"><span data-stu-id="a0b80-102">Oracle BFILEs</span></span>
<span data-ttu-id="a0b80-103">Der .NET Framework-Datenanbieter für Oracle enthält die <xref:System.Data.OracleClient.OracleBFile>-Klasse, die für das Arbeiten mit dem Oracle-<xref:System.Data.OracleClient.OracleType.BFile>-Datentyp verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a0b80-103">The .NET Framework Data Provider for Oracle includes the <xref:System.Data.OracleClient.OracleBFile> class, which is used to work with the Oracle <xref:System.Data.OracleClient.OracleType.BFile> data type.</span></span>  
  
 <span data-ttu-id="a0b80-104">Die Oracle **BFILE** -Datentyp ist ein Oracle **LOB** -Datentyp, der einen Verweis auf binäre Daten mit einer maximalen Größe von 4 Gigabyte enthält.</span><span class="sxs-lookup"><span data-stu-id="a0b80-104">The Oracle **BFILE** data type is an Oracle **LOB** data type that contains a reference to binary data with a maximum size of 4 gigabytes.</span></span> <span data-ttu-id="a0b80-105">Ein Oracle **BFILE** unterscheidet sich von anderen Oracle- **LOB** -Datentypen darin, dass ihre Daten in einer physischen Datei im Betriebssystem statt auf dem Server gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="a0b80-105">An Oracle **BFILE** differs from other Oracle **LOB** data types in that its data is stored in a physical file in the operating system instead of on the server.</span></span> <span data-ttu-id="a0b80-106">Beachten Sie, dass die **BFILE** Datentyp bietet schreibgeschützten Zugriff auf Daten.</span><span class="sxs-lookup"><span data-stu-id="a0b80-106">Note that the **BFILE** data type provides read-only access to data.</span></span>  
  
 <span data-ttu-id="a0b80-107">Andere Eigenschaften des eine **BFILE** -Datentyp, der Unterscheidung von einer **LOB** -Datentyp sind, dass die It:</span><span class="sxs-lookup"><span data-stu-id="a0b80-107">Other characteristics of a **BFILE** data type that distinguish it from a **LOB** data type are that it:</span></span>  
  
-   <span data-ttu-id="a0b80-108">Er enthält unstrukturierte Daten.</span><span class="sxs-lookup"><span data-stu-id="a0b80-108">Contains unstructured data.</span></span>  
  
-   <span data-ttu-id="a0b80-109">Er unterstützt das serverseitige Aufteilen in kleine Blöcke.</span><span class="sxs-lookup"><span data-stu-id="a0b80-109">Supports server-side chunking.</span></span>  
  
-   <span data-ttu-id="a0b80-110">Er verwendet die Semantik zum Kopieren von Verweisen.</span><span class="sxs-lookup"><span data-stu-id="a0b80-110">Uses reference copy semantics.</span></span> <span data-ttu-id="a0b80-111">Angenommen, Sie für einen Kopiervorgang Ausführen einer **BFILE**, wird nur die **BFILE** Locator (Dies ist ein Verweis auf die Datei ist) wird kopiert.</span><span class="sxs-lookup"><span data-stu-id="a0b80-111">For example, if you perform a copy operation on a **BFILE**, only the **BFILE** locator (which is a reference to the file) is copied.</span></span> <span data-ttu-id="a0b80-112">Die Daten in der Datei werden nicht kopiert.</span><span class="sxs-lookup"><span data-stu-id="a0b80-112">The data in the file is not copied.</span></span>  
  
 <span data-ttu-id="a0b80-113">Die **BFILE** Datentyp sollte verwendet werden, zum Verweisen auf LOBs, die in der Größe groß sind und daher nicht praktikabel ist, in der Datenbank gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a0b80-113">The **BFILE** data type should be used for referencing LOBs that are large in size, and therefore, not practical to store in the database.</span></span> <span data-ttu-id="a0b80-114">Mehr Aufwand für Clients, Servern und Kommunikation beteiligt ist, bei Verwendung einer **BFILE** Datentyp im Vergleich mit der **LOB** -Datentyp.</span><span class="sxs-lookup"><span data-stu-id="a0b80-114">More client, server, and communication overhead is involved when using a **BFILE** data type compared with the **LOB** data type.</span></span> <span data-ttu-id="a0b80-115">Es ist jedoch effizienter, den Zugriff auf eine **BFILE** Wenn Sie nur eine kleine Menge Daten zu erhalten müssen.</span><span class="sxs-lookup"><span data-stu-id="a0b80-115">It is more efficient to access a **BFILE** if you only need to obtain a small amount of data.</span></span> <span data-ttu-id="a0b80-116">Es ist effektiver, auf datenbankresidente LOBs zuzugreifen, wenn das ganze Objekt abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="a0b80-116">It is more efficient to access database-resident LOBs if you need to obtain the entire object.</span></span>  
  
 <span data-ttu-id="a0b80-117">Jedem von NULL **OracleBFile** Objekt bezieht sich auf zwei Entitäten, die den Speicherort der zugrunde liegenden physischen Datei definieren:</span><span class="sxs-lookup"><span data-stu-id="a0b80-117">Each non-NULL **OracleBFile** object is associated with two entities that define the location of the underlying physical file:</span></span>  
  
1.  <span data-ttu-id="a0b80-118">Ein Oracle-DIRECTORY-Objekt, das als Datenbank-Alias für ein Verzeichnis im Dateisystem fungiert.</span><span class="sxs-lookup"><span data-stu-id="a0b80-118">An Oracle DIRECTORY object, which is a database alias for a directory in the file system, and</span></span>  
  
2.  <span data-ttu-id="a0b80-119">Der Dateiname der zugrunde liegenden physischen Datei, die sich in dem dem DIRECTORY-Objekt zugeordneten Verzeichnis befindet.</span><span class="sxs-lookup"><span data-stu-id="a0b80-119">The file name of the underlying physical file, which is located in the directory associated with the DIRECTORY object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0b80-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a0b80-120">Example</span></span>  
 <span data-ttu-id="a0b80-121">Im folgende C#-Beispiel wird veranschaulicht, wie Sie erstellen eine **BFILE** in einer Oracle-Tabelle, und rufen Sie ihn in der Form einer **OracleBFile** Objekt.</span><span class="sxs-lookup"><span data-stu-id="a0b80-121">The following C# example demonstrates how you can create a **BFILE** in an Oracle table and then retrieve it in the form of an **OracleBFile** object.</span></span> <span data-ttu-id="a0b80-122">Das Beispiel veranschaulicht die Verwendung der <xref:System.Data.OracleClient.OracleDataReader> Objekt und die **OracleBFile** **Seek** und **lesen** Methoden.</span><span class="sxs-lookup"><span data-stu-id="a0b80-122">The example demonstrates using the <xref:System.Data.OracleClient.OracleDataReader> object and the **OracleBFile** **Seek** and **Read** methods.</span></span> <span data-ttu-id="a0b80-123">Beachten Sie, um die Verwendung dieses Beispiels Sie zunächst ein Verzeichnis namens erstellen müssen "c:\\\bfiles" und die Datei "MyFile.jpg" auf dem Oracle-Server.</span><span class="sxs-lookup"><span data-stu-id="a0b80-123">Note that in order to use this sample, you must first create a directory named "c:\\\bfiles" and file named "MyFile.jpg" on the Oracle server.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a0b80-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0b80-124">See Also</span></span>  
 [<span data-ttu-id="a0b80-125">Oracle und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a0b80-125">Oracle and ADO.NET</span></span>](../../../../docs/framework/data/adonet/oracle-and-adonet.md)  
 [<span data-ttu-id="a0b80-126">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="a0b80-126">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
