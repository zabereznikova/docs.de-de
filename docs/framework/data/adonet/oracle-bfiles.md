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
# <a name="oracle-bfiles"></a>Oracle-BFILEs
Der .NET Framework-Datenanbieter für Oracle enthält die <xref:System.Data.OracleClient.OracleBFile>-Klasse, die für das Arbeiten mit dem Oracle-<xref:System.Data.OracleClient.OracleType.BFile>-Datentyp verwendet wird.  
  
 Der Oracle **BFILE-Datentyp** ist ein Oracle LOB-Datentyp, der einen Verweis auf Binärdaten mit einer maximalen Größe von 4 Gigabyte enthält. **LOB** Ein Oracle **BFILE** unterscheidet sich von anderen Oracle **LOB-Datentypen** dadurch, dass seine Daten in einer physischen Datei im Betriebssystem und nicht auf dem Server gespeichert werden. Beachten Sie, dass der **BFILE-Datentyp** schreibgeschützten Zugriff auf Daten bietet.  
  
 Andere Merkmale eines BFILE-Datentyps, die ihn von einem **Branchendatentyp** unterscheiden, sind: **BFILE**  
  
- Er enthält unstrukturierte Daten.  
  
- Er unterstützt das serverseitige Aufteilen in kleine Blöcke.  
  
- Er verwendet die Semantik zum Kopieren von Verweisen. Wenn Sie z. B. einen Kopiervorgang für eine **BFILE**ausführen, wird nur der **BFILE-Locator** (der ein Verweis auf die Datei ist) kopiert. Die Daten in der Datei werden nicht kopiert.  
  
 Der **BFILE-Datentyp** sollte für den Verweis auf große LOBs verwendet werden, die daher nicht in der Datenbank gespeichert werden können. Bei der Verwendung eines **BFILE-Datentyps** im Vergleich zum **Branchendatentyp** ist ein mehr Client-, Server- und Kommunikationsaufwand erforderlich. Es ist effizienter, auf eine **BFILE** zuzugreifen, wenn Sie nur eine kleine Datenmenge abrufen müssen. Es ist effektiver, auf datenbankresidente LOBs zuzugreifen, wenn das ganze Objekt abgerufen werden soll.  
  
 Jedes **Nicht-NULL-OracleBFile-Objekt** ist zwei Entitäten zugeordnet, die den Speicherort der zugrunde liegenden physischen Datei definieren:  
  
1. Ein Oracle-DIRECTORY-Objekt, das als Datenbank-Alias für ein Verzeichnis im Dateisystem fungiert.  
  
2. Der Dateiname der zugrunde liegenden physischen Datei, die sich in dem dem DIRECTORY-Objekt zugeordneten Verzeichnis befindet.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie Sie eine **BFILE** in einer Oracle-Tabelle erstellen und sie dann in Form eines **OracleBFile-Objekts** abrufen können. Das Beispiel veranschaulicht <xref:System.Data.OracleClient.OracleDataReader> die Verwendung des Objekts und der **OracleBFile** **Seek** and **Read-Methoden.** Beachten Sie, dass Sie, um dieses Beispiel verwenden zu\\können, zunächst ein Verzeichnis mit dem Namen "c: 'bfiles" und die Datei mit dem Namen "MyFile.jpg' auf dem Oracle-Server erstellen müssen.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [Oracle und ADO.NET](oracle-and-adonet.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
